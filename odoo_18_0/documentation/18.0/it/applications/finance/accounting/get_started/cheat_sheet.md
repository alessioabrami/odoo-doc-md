# Promemoria contabile — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](chart_of_accounts.html "Piano dei conti") |
  * [precedente](../get_started.html "Per iniziare") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Per iniziare](../get_started.html) »
  * Promemoria contabile



# Promemoria contabile¶

Lo **stato patrimoniale** rappresenta un’istantanea della situazione finanziaria dell’azienda in una data specifica (al contrario del conto economico che riporta i dati di un periodo specifico).

  * Gli **asset** rappresentano la ricchezza dell’azienda e i beni che possiede. Le immobilizzazioni comprendono edifici e uffici, mentre le attività correnti comprendono conti bancari e contanti. Il denaro dovuto da un cliente è un asset. Un dipendente non è un asset.

  * Le **passività** sono obblighi derivanti da eventi passati che l’azienda dovrà pagare in futuro (bollette, debiti, fornitori non pagati). Le passività possono anche essere definite come una fonte di finanziamento fornita all’azienda, chiamata anche _leva finanziaria_.

  * Il **patrimonio netto** è l’ammontare dei fondi conferiti dai proprietari della società (fondatori o azionisti) più gli utili (o le perdite) precedentemente trattenuti. Ogni anno, gli utili (o le perdite) netti possono essere riportati come utili non distribuiti o distribuiti agli azionisti (come dividendo).




Ciò che è di proprietà (un asset) è stato finanziato attraverso debiti da rimborsare (passività) o capitale (profitti, capitale).

Tra gli **asset** e le **spese** c’è una differenza:
    

  * un **asset** è una risorsa con valore economico che un individuo, una società o un Paese possiede o controlla con l’aspettativa che fornisca un beneficio futuro. Gli asset sono riportati nello stato patrimoniale di un’azienda. Vengono acquistati o creati per aumentare il valore di un’azienda o per trarne beneficio.

  * Una **spesa** rappresenta il costo di operazioni messe a punto dall’azienda per generare profitto.




Il resoconto **profitti e perdite** mostra le prestazioni dell’azienda in un periodo di tempo specifico, di solito un trimestre o un anno fiscale.

>   * La parola **ricavi** fa riferimento al denaro guadagnato dall’azienda grazie alla vendita di beni e/o servizi.
> 
>   * Il **Costo dei beni venduti** (COGS o conosciuto anche come «Costo complessivo) fa riferimento al costo di vendita di beni (ad es. il costo dei materiali e della manodopera impiegata per creare i beni).
> 
>     * L”**utile lordo** equivale ai ricavi delle vendite meno il costo dei beni venduti.
> 
>     * Le **spese operative** (OPEX) includono gli stipendi dei dipartimenti amministrazione, delle vendite e R&D, gli affitti e le utenze, i costi vari, le assicurazioni e tutto ciò che va oltre i costi dei prodotti venduti o il costo di vendita.
> 
> 


> Asset = Passività + Patrimonio netto

## Piano dei conti¶

Il **piano dei conti** elenca tutti i conti dell’azienda: sia quelli dello stato patrimoniale che quelli del conto economico. Ogni transazione viene registrata addebitando e accreditando più conti in una registrazione contabile. In un certo senso, il piano dei conti è come il DNA di un’azienda!

Ogni conto elencato nel piano dei conti appartiene a una categoria specifica. In Odoo, ogni conto ha un codice unico e appartiene a una di queste categorie:

  * **Capitale e debiti subordinati**
    
    * Per **capitale** si intende l’importo di denaro investito dagli azionisti di un’azienda per finanziare le attività dell’azienda stessa.

    * I **debiti subordinati** rappresentano l’importo di denaro prestato da terze parti all’azienda per finanziare le proprie attività. In caso di fallimento, le terze parti vengono rimborsate prima degli azionisti.

  * Le **immobilizzazioni** sono elementi tangibili (ad es. fisici) oppure proprietà che l’azienda ha acquistato e utilizza per produrre i propri beni o fornire i propri servizi. Le immobilizzazioni sono asset a lungo termine. Questo significa che gli asset hanno un ciclo di vita utile di più di un anno. Includono anche immobili, impianti e macchinari («PP&E») e vengono registrati nello stato patrimoniale.

  * **Asset e immobilizzazioni correnti**
    
    * Il conto **asset correnti** è una voce dello stato patrimoniale elencata nella sezione Asset, che contabilizza tutti gli asset di proprietà dell’azienda che possono essere convertiti in denaro entro un anno. Gli asset correnti comprendono contanti, equivalenti, crediti, scorte di magazzino, titoli negoziabili, debiti prepagati e altri asset liquidi.

    * Le **passività correnti** sono le obbligazioni finanziarie a breve termine di un’azienda con scadenza entro un anno. Un esempio di passività corrente è il denaro dovuto ai fornitori sotto forma di debiti.

  * **Conti bancari e di cassa**
    
    * Un **conto bancario** è un conto finanziario gestito da una banca o da un altro istituto finanziario in cui vengono registrate le transazioni finanziarie tra la banca e un cliente.

    * Un **conto cassa** , o libro cassa, può riferirsi a un registro in cui vengono registrate tutte le transazioni di cassa. Il conto di cassa comprende sia le registrazioni degli incassi che quelle dei pagamenti.

  * **Spese e ricavi**
    
    * Una **spesa** è il costo delle operazioni che un’azienda sostiene per generare ricavi. È semplicemente definita come il costo che si deve sostenere per ottenere qualcosa. Le spese più comuni includono i pagamenti dei fornitori, gli stipendi dei dipendenti, i contratti di locazione degli stabilimenti e l’ammortamento delle attrezzature.

    * Il termine “**ricavi** ” si riferisce generalmente all’ammontare di denaro, proprietà e altri trasferimenti di valore ricevuti in un determinato periodo di tempo in cambio di servizi o prodotti.




### Esempio¶

*: le caselle Rimborso cliente e Pagamento cliente non possono essere selezionate insieme in quanto indicano l’una il contrario dell’altra.

> Saldo = Debito - Credito

## Registrazioni contabili¶

Ogni documento finanziario dell’azienda (ad es. una fattura, un estratto conto bancario, una busta paga, un contratto di aumento di capitale) viene registrato come registrazione contabile, con un impatto su diversi conti.

Affinché una registrazione contabile sia bilanciata, la somma di tutti gli addebiti deve essere uguale alla somma di tutti gli accrediti.

esempi di scritture contabili per varie transazioni. (vedere entries.js)

## Riconciliazione¶

La riconciliazione è il processo di collegamento delle voci del giornale di un conto specifico e di corrispondenza tra crediti e debiti.

Il suo scopo principale è quello di collegare i pagamenti alle relative fatture per contrassegnarle come pagate. Ciò avviene effettuando una riconciliazione sul conto dei crediti e/o sul conto dei debiti.

La riconciliazione viene eseguita automaticamente dal sistema quando:

  * il pagamento viene registrato direttamente sulla fattura

  * i collegamenti tra i pagamenti e le fatture vengono rilevati durante il processo di riscontro bancario




Esempio di dichiarazione del cliente

Conti di credito | Dare | Avere  
---|---|---  
Fattura 1 | 100 |   
Pagamento parziale 1/2 |  | 70  
Fattura 2 | 65 |   
Pagamento parziale 2/2 |  | 30  
Pagamento 2 |  | 65  
Fattura 3 | 50 |   
|  |   
Totale da pagare | 50 |   
  
## Riconciliazione bancaria¶

La riconciliazione bancaria è la corrispondenza tra le righe dell’estratto conto (fornito dalla banca) e le transazioni registrate internamente (pagamenti a fornitori o clienti). Per ogni riga di un estratto conto bancario, può essere:

  * **corrispondenza con un pagamento registrato in precedenza** : un pagamento viene registrato quando si riceve un assegno da un cliente, quindi viene confrontato quando si controlla l’estratto conto bancario.

  * **registrato come nuovo pagamento** : la registrazione del pagamento viene creata e riconciliata con la relativa fattura durante l’elaborazione dell’estratto conto.

  * **registrata come un’altra transazione** : bonifico bancario, addebito diretto, ecc.




Odoo dovrebbe riconciliare automaticamente la maggior parte delle transazioni; solo alcune dovrebbero richiedere una revisione manuale. Al termine del processo di riconciliazione bancaria, il saldo del conto bancario in Odoo dovrebbe corrispondere al saldo dell’estratto conto.

## Gestione degli assegni¶

Esistono due approcci alla gestione degli assegni e dei bonifici interni:

  * Due scritture contabili e una riconciliazione

  * Una scrittura contabile e una riconciliazione bancaria




La prima voce del giornale viene creata registrando il pagamento sulla fattura. La seconda viene creata quando si registra l’estratto conto.

Account | Dare | Avere | Riconciliazione  
---|---|---|---  
Conto di credito |  | 100 | Fattura ABC  
Fondi non depositati | 100 |  | Assegno 0123  
Account | Dare | Avere | Riconciliazione  
---|---|---|---  
Fondi non depositati |  | 100 | Assegno 0123  
Banca | 100 |  |   
  
Registrando il pagamento sulla fattura si crea una voce di giornale. Quando si riconcilia l’estratto conto bancario, la riga dell’estratto conto viene collegata alla voce del giornale esistente.

Account | Dare | Avere | Riconciliazione | Estratto conto bancario  
---|---|---|---|---  
Conto di credito |  | 100 | Fattura ABC |   
Banca | 100 |  |  | Dichiarazione XYZ  
  
[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/finance/accounting/get_started/cheat_sheet.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](chart_of_accounts.html "Piano dei conti") |
  * [precedente](../get_started.html "Per iniziare") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Per iniziare](../get_started.html) »
  * Promemoria contabile


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
  *[API]: application programming interfaces
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
  *[AVCO]: Average Costing
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