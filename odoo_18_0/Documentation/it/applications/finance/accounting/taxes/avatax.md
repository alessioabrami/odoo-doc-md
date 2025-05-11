# Integrazione AvaTax — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](avatax/avatax_use.html "Utilizzare AvaTax") |
  * [precedente](fiscal_positions.html "Posizioni di bilancio \(mappatura fiscale e contabile\)") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Imposte](../taxes.html) »
  * Integrazione AvaTax



# Integrazione AvaTax¶

_AvaTax_ di Avalara è un software fiscale basato su cloud. L’integrazione di _AvaTax_ con Odoo consente di calcolare le imposte in tempo reale e in base alla regione quando gli utenti vendono, acquistano e fatturano articoli in Odoo. Il calcolo delle imposte di _AvaTax_ è supportato da tutti i Paesi classificati dalle Nazioni Unite, comprese le transazioni transfrontaliere.

Importante

 _AvaTax_ è disponibile solo per l’integrazione con database/aziende situate negli Stati Uniti, Canada e Brasile. Questo significa che la posizione di bilancio/Paese di un database può essere solamente uno dei Paesi elencati in precedenza. Per maggiori informazioni, consulta la documentazione Paese fiscale.

_AvaTax_ tiene conto delle aliquote fiscali basate sulla posizione per ogni Stato, contea e città. Migliora l’accuratezza delle rimesse prestando molta attenzione alle leggi, alle regole, ai confini delle giurisdizioni e alle circostanze speciali (come le festività fiscali e le esenzioni dai prodotti). Le aziende che integrano _AvaTax_ possono mantenere il controllo dei calcoli fiscali internamente con questa semplice integrazione API.

Importante

Tuttavia, in Odoo ci sono alcuni limiti relativi al calcolo delle imposte con AvaTax:

  * AvaTax utilizza l’indirizzo dell’azienda per impostazione predefinita. Per utilizzare l’indirizzo del magazzino, attiva l’opzione [Spedisci in seguito](../../../sales/point_of_sale/shop/ship_later.html) nelle impostazioni del modulo **POS**.

  * Le accise **non** sono supportate. Questo include le tasse sul tabacco/sigarette elettroniche, le tasse sul carburante e altri settori specifici.




Vedi anche

Documentazione di supporto di Avalara: [About AvaTax](https://community.avalara.com/support/s/document-item?language=en_US)

## Eseguire la configurazione su AvaTax¶

Per utilizzare _AvaTax_ , è richiesto un account con Avalara. Se non ne hai uno, puoi collegarti con Avalara per acquistare una licenza: [Avalara: Let’s Talk](https://www.avalara.com/us/en/get-started.html).

Suggerimento

Dopo aver configurato l’account, prendi nota dello Account ID di _AvaTax_ perché ne avrai bisogno durante la configurazione di Odoo. In Odoo, il numero corrisponde allo API ID.

In seguito, [crea un profilo per un’azienda](https://www.odoo.com/r/2k0).

### Creare un profilo aziendale di base¶

Raccogli i dettagli essenziali dell’azienda per la fase successiva: sedi in cui si riscuotono le imposte, prodotti/servizi venduti (e relative sedi di vendita) ed esenzioni fiscali per i clienti, se applicabili. Segui la documentazione di Avalara per creare di un profilo aziendale di base:

  1. [aggiungi le informazioni sull’azienda](https://www.odoo.com/r/XZDW)

  2. [indica dove l’azienda riscuote e paga le tasse](https://www.odoo.com/r/E6g)

  3. [verifica le giurisdizioni e attiva l’azienda](https://www.odoo.com/r/NIy)

  4. [aggiungi altre sedi dell’azienda per completare i dati in base alla posizione](https://www.odoo.com/r/GF4)

  5. [aggiungi un marketplace al profilo aziendale](https://www.odoo.com/r/QA5).




### Collegarsi ad AvaTax¶

Dopo aver creato il profilo aziendale di base in Avalara, collegati ad _AvaTax_. Questo passaggio collega Odoo e _AvaTax_ in modo bidirezionale.

Accedi alla `sandbox <https://sandbox.admin.avalara.com/>` di Avalara _ oppure all’ambiente di [produzione](https://admin.avalara.com/). La scelta dipende dal tipo di account Avalara che l’azienda vuole integrare.

Vedi anche

[Sandbox vs ambienti di produzione in Avalara](https://knowledge.avalara.com/bundle/fzc1692293626742/page/sandbox-vs-production.html).

Accedi per creare un Codice di licenza. Accedi alle Impostazioni ‣ Licenza e chiavi API. Fai clic su Genera codice di licenza.

Importante

Apparirà un avviso che recita: `Se l'applicazione aziendale è collegata alle soluzioni Avalara, la connessione sarà interrotta finché non si aggiorna l'applicazione con il nuovo codice di licenza. L'azione non può essere annullata.`

La generazione di un nuovo codice di licenza interrompe la connessione con le applicazioni aziendali esistenti che utilizzano l’integrazione _AvaTax_. Assicurati di aggiornare queste applicazioni con il nuovo codice di licenza.

Se si tratta della prima integrazione API realizzata tra _AvaTax_ e Odoo, fai clic su Genera codice di licenza.

Se si tratta di un codice di licenza aggiuntivo, assicurati che la connessione precedente possa essere interrotta. A ciascuno degli account Avalara sandbox e produzione è associata **una sola** chiave di licenza.

Avvertimento

Copia il codice in un luogo sicuro. Ti consigliamo vivamente di eseguire un backup del codice di licenza per averlo in futuro. Il codice non può essere recuperato dopo aver abbandonato la schermata.

## Configurazione Odoo¶

Prima di utilizzare _AvaTax_ , sono necessarie alcune configurazioni aggiuntive in Odoo per garantire che i calcoli delle imposte vengano effettuati con precisione.

Verifica che il database Odoo contenga i dati necessari. Il Paese inizialmente impostato nel database determina la posizione di bilancio e aiuta _AvaTax_ a calcolare aliquote fiscali accurate.

### Paese fiscale¶

Per configurare il Paese fiscale, accedi all’app Contabilità ‣ Configurazione ‣ Impostazioni.

Vedi anche

[Fiscal localizations](../../fiscal_localizations.html)

Nella sezione Imposte, imposta il campo Nazione fiscale su Stati Uniti, Canada o Brasile. In seguito, fai clic su Salva.

### Impostazioni azienda¶

Tutte le aziende che operano nel database Odoo devono avere un indirizzo completo nelle impostazioni. Accedi al modulo Impostazioni e nella sezione Aziende, assicurati che ci sia solo un’azienda che opera nel database Odoo. Fai clic su Aggiorna informazioni per aprire una pagina separata e aggiornare i dettagli dell’azienda.

Se nel database sono presenti più aziende, fai clic su Gestione aziende per caricare un elenco di aziende da selezionare. Aggiorna le informazioni sull’azienda facendo clic sull’azienda specifica.

Gli amministratori del database devono garantire che i campi Indirizzo…, Indirizzo 2…, Città, Stato, CAP e Paese siano aggiornati per tutte le aziende.

Ciò garantisce calcoli fiscali accurati e operazioni contabili di fine anno senza intoppi.

Vedi anche

  * [Aziende](../../../general/companies.html)

  * [Per iniziare](../get_started.html)




### Installazione del modulo¶

In seguito, assicurati di aver installato il modulo Odoo _AvaTax_. Per farlo, accedi al modulo Applicazioni e nella barra Cerca… scrivi `avatax` e premi `INVIO`. Appariranno i seguenti risultati:

Nome | Nome tecnico | Descrizione  
---|---|---  
Avatax | `account_avatax` | Modulo _AvaTax_ predefinito. Il modulo aggiunge le funzionalità di base di _AvaTax_ per il calcolo delle imposte.  
Avatax per la geolocalizzazione | `account_avatax_geolocalize` | Questo modulo include le funzioni necessarie per l’integrazione di _AvaTax_ nella geo-localizzazione in Odoo.  
Avatax per OdV | `account_avatax_sale` | Comprende le informazioni necessarie per il calcolo delle imposte sugli ordini di vendita in Odoo.  
Avatax per Magazzino | `account_avatax_stock` | Include il calcolo delle imposte in ODoo Magazzino.  
Ponte Amazon/Avatax | `sale_amazon_avatax` | Include le funzionalità per il calcolo delle imposte tra il _Connettore Amazon_ e Odoo.  
Avatax Brasile | `l10n_br_avatax` | Include informazioni per il calcolo delle imposte nella localizzazione brasiliana.  
Avatax Brasile per servizi | `l10n_br_avatax_services` | Questo modulo include le funzioni necessarie per il calcolo delle imposte sui servizi nella localizzazione Brasile.  
Avatax Brasile Vendite per servizi | `l10n_br_edi_sale_services` | Questo modulo include le funzioni necessarie per il calcolo delle imposte per la vendita di servizi nella localizzazione brasiliana. Include l’interscambio elettronico di dati (EDI).  
Test ordini di vendita Avatax Brasile | `l10n_br_test_avatax_sale` | Questo modulo include le funzioni necessarie per testare gli ordini di vendita nella localizzazione brasiliana.  
  
Fai clic sul pulsante Installa sul modulo chiamato Avatax: `account_avatax`. Verranno installati i seguenti moduli:

  * Avatax: `account_avatax`

  * Avatax per ordini di vendita: `account_avatax_sale`

  * Avatax per Magazzino: `account_avatax_stock`




Se _AvaTax_ è necessario per la geolocalizzazione o con il _Connettore Amazon_ , installa i moduli individualmente facendo clic sul pulsante Installa dei moduli Avatax per la geolocalizzazione e Ponte Amazon/Avatax.

Vedi anche

Per avere istruzioni specifiche su _AvaTax_ e la localizzazione, consulta la documentazione relativa alla [localizzazione fiscale](../../fiscal_localizations.html):

  * [Brasile](../../fiscal_localizations/brazil.html)

  * [Stati Uniti](../../fiscal_localizations/united_states.html)




### Impostazioni AvaTax Odoo¶

Per integrare la API _AvaTax_ con Odoo, accedi all’app Contabilità ‣ Configurazione ‣ Impostazioni. I campi AvaTax nella sezione Imposte permettono di configurare tutte le impostazioni _AvaTax_ di cui hai bisogno una volta inserite le credenziali.

Per prima cosa, seleziona la casella di controllo a sinistra delle impostazioni AvaTax, per attivare _AvaTax_ sul database. Questo è un modo rapido e comodo per attivare e disattivare il calcolo delle imposte di _AvaTax_ sul database di Odoo.

#### Prerequisiti¶

Per prima cosa, seleziona un Ambiente in cui l’azienda desidera utilizzare _AvaTax_. Può essere Sandbox o Produzione.

Vedi anche

Per capire quale ambiente _AvaTax_ utilizzare (Produzione o Sandbox), visita la pagina: [Sandbox vs Production environments](https://knowledge.avalara.com/bundle/fzc1692293626742/page/sandbox-vs-production.html).

#### Credenziali¶

Ora puoi inserire le credenziali. Inserisci l” ID account _AvaTax_ nel campo ID API e il Codice di licenza deve essere inserito nel campo Chiave API.

Importante

Puoi trovare l” ID account accedendo al portale _AvaTax_ ([sandbox](https://sandbox.admin.avalara.com/) o [produzione](https://admin.avalara.com/)). Fai clic sulle inziali e sull” Account dell’utente nell’angolo in alto a destra. L” ID account è il primo nell’elenco.

Per accedere al Codice di licenza consulta la documentazione: Collegarsi ad AvaTax.

Per il campo Codice azienda, inserisci il codice azienda Avalara dell’azienda che stai configurando. Avalara interpreta questo come `DEFAULT`, se non configurato. Il Codice azienda è accessibile dal portale di gestione Avalara.

Per prima cosa, accedi al portale _AvaTax_ ([sandbox](https://sandbox.admin.avalara.com/) o [produzione](https://admin.avalara.com/)). Successivamente, accedi alle Impostazioni ‣ Gestisci aziende. Il valore Codice azienda si trova nella riga dell” Azienda nella colonna Codice azienda.

#### Opzioni transazioni¶

Esistono due tipi di impostazioni per le transazioni in Odoo _AvaTax_ che possono essere configurate: Usa UPC e Delega operazioni.

Se la casella di controllo accanto a Usa UPC è selezionata, le transazioni utilizzeranno i codici universali dei prodotti (UPC), invece dei codici personalizzati definiti in Avalara. Per indicazioni specifiche, consulta un dottore commercialista.

Se la casella di controllo Delega operazioni è selezionata, le transazioni nel database di Odoo saranno impegnate per la rendicontazione in _AvaTax_.

#### Convalida indirizzo¶

La funzione _Convalida indirizzo_ assicura la selezione dell’indirizzo più aggiornato secondo gli standard postali su un contatto in Odoo. Questo è importante per fornire calcoli fiscali accurati ai clienti.

Importante

La funzionalità di Convalida dell’indirizzo funziona solo con partner/clienti in Nord America.

Inoltre, seleziona la casella di controllo accanto al campo Convalida indirizzo.

Importante

Per un calcolo accurato delle imposte, è consigliabile inserire un indirizzo completo per i contatti salvati nel database. Tuttavia, _AvaTax_ può ancora funzionare implementando un tentativo di massima precisione utilizzando solo i campi Paese, Stato e Codice postale. Questi sono i tre campi minimi richiesti.

Salva le impostazioni per implementare la configurazione.

Suggerimento

Convalida manualmente l’indirizzo accedendo all’app Contatti per poi selezionare un contatto specifico. Ora che hai configurato il modulo _AvaTax_ sul database, il pulsante Convalida apparirà direttamente sotto il campo Indirizzo.

Fai clic sul pulsante Convalida per far apparire una finestra pop-up con le voci Indirizzo convalidato e Indirizzo originale. Se l” Indirizzo convalidato è l’indirizzo e-mail corretto per le comunicazioni relative alle imposte, fai clic su Salva convalidato.

Avvertimento

Tutti gli indirizzi inseriti in precedenza per i contatti nel database di Odoo dovranno essere convalidati utilizzando il processo di convalida manuale descritto sopra. Gli indirizzi non vengono convalidati automaticamente se sono stati inseriti in precedenza. Questo avviene solo al momento del calcolo delle imposte.

#### Testare la connessione¶

Dopo aver inserito tutte le informazioni di cui sopra nella configurazione di _AvaTax_ su Odoo, fai clic su Prova connessione. Questo garantisce che l” ID API e la CHIAVE API siano corretti e che venga stabilita una connessione tra Odoo e l’interfaccia di programmazione dell’applicazione (API) di _AvaTax_.

#### Parametri di sincronizzazione¶

Dopo aver terminato la configurazione di _AvaTax_ , fai clic sul pulsante Sincronizza parametri. L’azione sincronizza i codici esenzione presi da _AvaTax_.

### Posizione di bilancio¶

Successivamente, apri l’app Contabilità ‣ Configurazione ‣ Contabilità: Posizioni di bilancio. Apparirà una Posizione di bilancio dal nome Mappatura automatica imposta (AvaTax). Fai clic su di essa per aprire la pagina di configurazione della posizione di bilancio _AvaTax_.

Assicurati che la casella di controllo Usa API AvaTax sia selezionata.

In via facoltativa, spunta la casella accanto al campo: Rileva automaticamente. Una volta attivata l’opzione, Odoo applicherà automaticamente la Posizione di bilancio per le transazioni in Odoo.

L’attivazione della funzione Rileva automaticamente comporta l’attivazione di altri parametri come IVA richiesta, Partita IVA estera, Gruppo nazione, Paese, Stati federali oppure Intervallo CAP. Il completamento dei parametri permette di filtrare l’utilizzo della Posizione di bilancio. Se non li completi, tutti i calcoli verranno eseguiti utilizzando questa Posizione di bilancio.

Avvertimento

Se la casella Rileva automaticamente non viene spuntata, ogni cliente dovrà configurare la Posizione di bilancio nella scheda Vendite e acquisti del record del contatto. Per farlo, apri l’app Vendite ‣ Ordini ‣ Clienti, oppure app Contatti ‣ Contatti. In seguito, seleziona un cliente o un contatto per configurare la posizione di bilancio.

Apri la scheda Vendite e acquisti, scorri fino alla sezione denominata Posizione di bilancio e imposta la posizione di bilancio per il cliente nel campo Posizione di bilancio.

Vedi anche

[Posizioni di bilancio (mappatura fiscale e contabile)](fiscal_positions.html)

#### Conti AvaTax¶

Dopo aver selezionato l’opzione Usa API AvaTax, apparirà una nuova scheda AvaTax. Fai clic sulla scheda per accedere a due impostazioni diverse.

La prima impostazione è Conto fattura AvaTax, mentre la seconda è Conto rimborso AvaTax. Assicurati che entrambi i conti siano impostati per una corretta registrazione di fine anno. Per indicazioni specifiche sulla configurazione di entrambi i conti, consulta un dottore commercialista.

Fai clic su Salva per salvare le modifiche.

### Mappatura imposte¶

L’integrazione _AvaTax_ è disponibile sugli ordini di vendita e sulle fatture con la posizione di bilancio _AvaTax_ inclusa.

Suggerimento

In aggiunta, è possibile configurare la mappatura dei prodotti nella posizione di bilancio Mappatura automatica imposta (AvaTax) tramite le schede Mappatura imposte e Mappatura conto. Per accedere alle Posizioni di bilancio, apri l’applicazione Contabilità ‣ Configurazione ‣ Contabilità: posizioni di bilancio.

#### Mappatura categorie prodotto¶

Prima di iniziare a utilizzare l’integrazione, specifica la Categoria Avatax sulle categorie del prodotto. Apri l’applicazione Magazzino ‣ Configurazione ‣ Categorie prodotto. Seleziona la categoria prodotto alla quale aggiungere la Categoria AvaTax. Seleziona una categoria dal menu a tendina per il campo Categoria AvaTax oppure Cerca ancora… per aprire l’elenco completo di opzioni.

#### Mappatura dei prodotti¶

È possibile configurare categorie _AvaTax_ anche su singoli prodotti. Per configurare una Categoria AvaTax apri l’applicazione Magazzino ‣ Prodotti ‣ Prodotti. Seleziona il prodotto a cui aggiungere la Categoria AvaTax. Nella scheda Informazioni generali, a destra, troverai un campo di selezione denominato: Categoria AvaTax. Infine, fai clic sul menu a tendina e seleziona una categoria oppure Cerca ancora… per trovare una categoria che non appare nell’elenco.

Nota

Se entrambi i prodotti e le rispettive categorie hanno una Categoria AvaTax configurata, la Categoria AvaTax del prodotto avrà la precedenza.

Importante

La mappatura di una Categoria AvaTax sul _Prodotto_ o sulla _Categoria prodotto_ dovrebbe essere completata per ogni _Prodotto_ o _Categoria prodotto_ , in base al percorso scelto.

Vedi anche

  * [Posizioni di bilancio (mappatura fiscale e contabile)](fiscal_positions.html)

  * [Utilizzare AvaTax](avatax/avatax_use.html)

  * [Portale Avalara (Avatax)](avatax/avalara_portal.html)

  * [Conformità imposte USA: video e-learning Avatax](https://www.odoo.com/slides/slide/us-tax-compliance-avatax-2858?fullscreen=1)




  * [Utilizzare AvaTax](avatax/avatax_use.html)
  * [Portale Avalara (Avatax)](avatax/avalara_portal.html)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/finance/accounting/taxes/avatax.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](avatax/avatax_use.html "Utilizzare AvaTax") |
  * [precedente](fiscal_positions.html "Posizioni di bilancio \(mappatura fiscale e contabile\)") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Imposte](../taxes.html) »
  * Integrazione AvaTax


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-App Purchase
  *[RTL]: right-to-left
  *[RST]: reStructuredText
  *[GUI]: graphical user interface
  *[TOC]: Table Of Contents
  *[SEO]: Search Engine Optimization
  *[EDI]: electronic data interchange
  *[SDD]: SEPA Direct Debit
  *[PLE]: Programa de Libros Electrónico
  *[BoM]: Bill of Materials
  *[MO]: Manufacturing Order
  *[MPS]: Master Production Schedules
  *[OEE]: overall equipment effectiveness
  *[RFQ]: Request for Quotation
  *[RfQ]: Request for Quotation
  *[RfQs]: Requests for Quotation
  *[IU]: Interfaccia Utente
  *[UoM]: Unit of Measure
  *[PoS]: Point of Sale
  *[FBM]: Fulfilled by Merchant
  *[FBA]: Fulfilled by Amazon
  *[API]: application programming interface
  *[IVA]: imposta sul valore aggiunto
  *[MRR]: Monthly Recurring Revenue
  *[ARR]: Annual Recurring Revenue
  *[USB]: Universal Serial Bus
  *[IoT]: Internet of Things
  *[OS]: Operating System
  *[SO]: sales order
  *[MRP]: Material Requirement Planning
  *[DNS]: Domain Name System
  *[SMTP]: Simple Mail Transfer Protocol
  *[SSL]: Secure Sockets Layer
  *[TLS]: Transport Layer Security
  *[SPF]: Sender Policy Framework
  *[DKIM]: DomainKeys Identified Mail
  *[DMARC]: Domain-based Message Authentication, Reporting, & Conformance
  *[CNAME]: nome canonico
  *[Cc]: Copia carbone
  *[LAN]: Local Area Network
  *[SSH]: secure shell protocol
  *[HTTPS]: Hypertext Transfer Protocol Secure
  *[UUID]: Universal Unique Identifier
  *[POS]: point of sale
  *[URL]: Uniform Resource Locator
  *[2FA]: two-factor authentication
  *[QR]: Quick Response
  *[LDAP]: Lightweight Directory Access Protocol
  *[KPI]: Indicatori di Prestazione Chiave
  *[ICP]: Indicatori Chiave di Prestazione
  *[CV]: curriculum vitae
  *[IAP’s]: in-app purchases
  *[DMFA]: De Multifunctionele Aangifte
  *[VIN]: Vehicle Identification Number
  *[MSRP]: Manufacturer's Suggested Retail Price
  *[SMS]: Short Message Service
  *[CTOR]: click-to-open rate
  *[CTR]: Click through rate
  *[LIFO]: Last-In, First-Out
  *[SAQ]: Self-Assessment Questionnaire
  *[VAT]: Value Added Tax
  *[SMP]: Service Metadata Publisher
  *[AVCO]: Average Cost Valuation
  *[OdA]: Ordine di acquisto
  *[sportello unico OSS]: One-Stop Shop
  *[IAPs]: in-app purchases
  *[SOs]: Sales Orders
  *[SRI]: Servicio de Rentas Internas
  *[ATS]: Anexo Transaccional Simplificado
  *[FPS]: Service Public Federal Finances
  *[ADW]: Average Daily Wage
  *[SII]: Fornitura Immediata di Informazioni
  *[CAFs]: Folio Authorization Code
  *[DTE]: Documentos Tributarios Electrónicos
  *[RUT]: Registro único tributario
  *[CAF]: Folio Authorization Code
  *[SII’s]: Servicio de Impuestos Internos
  *[PPM]: Provisional Monthly Payments rate
  *[IFRS]: International Financial Reporting Standards
  *[PCMN]: Plan Comptable Minimum Normalisé
  *[FDM]: Fiscal Data Module
  *[VSC]: VAT signing card
  *[TSS]: Technical Security System
  *[DSFinV-K]: Digitale Schnittstelle der Finanzverwaltung für Kassensysteme
  *[PCGE]: Plan Contable General Empresarial
  *[SUNAT]: Superintendencia Nacional de Aduanas y de Administración Tributaria
  *[GRE]: Guía de Remisión Electrónica
  *[OTP]: One-time Password
  *[GAAP]: Generally Acceptable Accounting Practices
  *[AR]: Accounts Receivable
  *[AP]: Accounts Payable
  *[CoA]: chart of accounts
  *[SEC]: Securities and Exchange Commission
  *[CFS]: Cash Flow Statement
  *[ACH]: automated clearing house
  *[NACHA]: National Automated Clearing House Association
  *[DBA]: Danish Bookkeeping Act
  *[IRBM]: Inland Revenue Board of Malaysia
  *[ETA]: Egyptian Tax Authority
  *[FACe]: General Entrance for Electronic Invoices
  *[DIAN]: Dirección de Impuestos y Aduanas Nacionales
  *[UID-Nummer]: Umsatzsteueridentifikationsnummer
  *[AFIP]: Administración Federal de Ingresos Públicos
  *[DGI]: Dirección General Impositiva
  *[CAEs]: Constancia de Autorización de Emisión
  *[CUI]: Codul Unic de Inregistrare
  *[CIF]: *Codul de identificare fiscală*
  *[SLS]: Summary List of Sales
  *[SLP]: Summary List of Purchases
  *[TPAR]: Taxable Payments Annual Report
  *[AdE]: Agenzia Delle Entrate
  *[SdI]: Sistema di Interscambio
  *[PA]: Public Administration
  *[CUU]: Codice Univoco Ufficio
  *[CIG]: Codice Identificativo Gara
  *[CUP]: Codice Unico di Progetto
  *[HSM]: Hardware Security Module
  *[Ri.Ba.]: Ricevuta Bancaria
  *[NIC]: National Informatics Centre
  *[IRN]: Invoice Reference Number
  *[CGST]: Central Goods and Services Tax
  *[SGST]: State Goods and Service Tax
  *[IGST]: Integrated Goods and Services Tax
  *[ITC]: Income Tax Credit
  *[SAT]: Servicio de Administración Tributaria
  *[DIOT]: Declaración Informativa de Operaciones con Terceros
  *[RFC]: Registro Federal de Contribuyentes
  *[PAC]: fornitori autorizzati
  *[PUE]: Pago en una Sola Exhibición/Payment in a Single Exhibition
  *[PPD]: Pago en Parcialidades o Diferido/Payment in Installements or Deferred
  *[CFDI]: Comprobante Fiscal Digital por Internet
  *[OSCU]: Online Sales Control Unit
  *[BOM]: bill of materials
  *[Bacs]: Bankers' Automated Clearing Services
  *[RCM]: Reverse Charge Mechanism
  *[PDT]: Payment Data Transfer
  *[ECO]: Engineering Change Order
  *[ECOs]: Engineering Change Orders
  *[BoMs]: Bills of Materials
  *[MOs]: Manufacturing Orders
  *[QCP]: Quality Control Point
  *[QCPs]: Quality Control Points
  *[RO]: Repair Order
  *[POs]: Purchase Orders
  *[PLM]: Product Lifecycle Management
  *[PO]: Purchase Order
  *[MTO]: Make to Order
  *[SVLs]: stock valuation layers
  *[SP]: Scrap Order
  *[DO]: Delivery Order
  *[RFQs]: Requests for Quotation
  *[EORI]: Economic Operators' Registration and Identification
  *[ZPL]: Zebra Programming Language
  *[DOs]: Delivery Orders
  *[FIFO]: First In, First Out
  *[FEFO]: First Expiry, First Out
  *[UoMs]: Units of Measure
  *[MTBF]: Mean Time Between Failure
  *[MTTR]: Mean Time To Repair
  *[EAN]: European Article Number
  *[UPC]: Universal Product Code
  *[GTIN]: Global Trade Item Number
  *[GTINs]: Global Trade Item Numbers
  *[A.I.]: Application Identifier
  *[CSV]: comma separated value
  *[SLAs]: Service Level Agreements
  *[SLA]: Service Level Agreement
  *[UTM]: Urchin Tracking Module
  *[GTM]: Google Tag Manager
  *[CDN]: Content Delivery Network
  *[CORS]: Cross-Origin Resource Sharing
  *[HTML]: HyperText Markup Language
  *[UI]: user interface
  *[ToS]: Terms of Service
  *[NRR]: non-recurring revenue
  *[VoIP]: Voice over Internet Protocol
  *[SIP]: Session Initiation Protocol
  *[US]: United States
  *[MP3]: MPEG Audio Layer 3
  *[WAV]: Waveform Audio File Format
  *[NSSL]: Non-Shopee Supported Logistics
  *[MID]: Merchant ID
  *[TID]: Terminal ID
  *[ISBN]: International Standard Book Number
  *[IP]: intellectual property
  *[SSC]: Jordanian Social Security Corporation
  *[UAE]: United Arab Emirates
  *[GCC]: Gulf Cooperation Council
  *[DEWS]: Daman Investments End of Service Programme
  *[WPS]: Wages Protection System
  *[EOS]: End Of Service
  *[EDR]: Employee Detail Record
  *[SCR]: Salary Control Record
  *[B2G]: business-to-government
  *[UBL]: Universal Business Language
  *[ZRE]: Zentraler Rechnungseingang
  *[OZG-RE]: Onlinezugangsgesetz-Rechnungseingang
  *[IGV]: Impuesto General a las Ventas) e di altre imposte applicabili, garantendo accuratezza e conformità con gli standard di rendicontazione fiscale del :abbr:`SUNAT (Superintendencia Nacional de Aduanas y de Administración Tributaria
  *[CUFE]: Código Único de Factura Electrónica
  *[CIUS-PT]: Customizable Invoice User Specification for Portugal
  *[USP]: Unternehmensserviceportal
  *[CIS]: Central Invoice System
  *[CAE]: Código de Autorización Electrónico
  *[FE]: Factura Electrónica
  *[CFE]: Comprobante Fiscal Electrónico
  *[ANAF]: Agenzia nazionale rumena per l'amministrazione fiscale
  *[Sdi]: Sistema di Interscambio
  *[NF-e]: Nota Fiscal Eletrônica
  *[NFS-e]: Nota Fiscal de Serviços Eletrônica
  *[NFC-e]: Nota Fiscal de Consumidor Eletrônica
  *[SEFAZ]: Secretaria da Fazenda