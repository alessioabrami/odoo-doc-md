# Imposte — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](taxes/cash_basis.html "Imposte per cassa") |
  * [precedente](get_started/tax_units.html "Unità fiscali") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Contabilità e fatturazione](../accounting.html) »
  * Imposte



# Imposte¶

Esistono numerosi tipi di **imposte** e la loro applicazione varia notevolmente, soprattutto a seconda della localizzazione dell’azienda. Per assicurarsi che vengano registrate con precisione, il sistema fiscale di Odoo supporta tutti i tipi di utilizzo e di calcolo.

## Imposte predefinite¶

Le **imposte predefinite** indicano quali imposte vengono selezionate automaticamente al momento della creazione di un nuovo prodotto. Inoltre, vengono utilizzate per precompilare il campo Imposte quando si aggiunge una nuova riga a una fattura in modalità [Società di contabilità](../accounting.html#fiduciaries).

Per modificare le **imposte predefinite** , apri l’app Contabilità ‣ Configurazione ‣ Impostazioni ‣ Imposte ‣ Imposte predefinite, seleziona le imposte appropriate per le imposte di vendita e acquisto predefinite e poi fai clic su Salva.

Nota

Le **imposte predefinite** vengono configurate automaticamente in base al Paese selezionato al momento della creazione del database oppure quando configuri un [pacchetto di localizzazione fiscale](../fiscal_localizations.html#fiscal-localizations-packages) per la tua azienda.

## Attivare imposte di vendita dalla vista elenco¶

La maggior parte delle imposte di vendita del Paese selezionato sono già preconfigurate nel database perché fanno parte del [pacchetto di localizzazione fiscale](../fiscal_localizations.html#fiscal-localizations-packages). Tuttavia, solo alcune imposte vengono attivate per impostazione predefinita. Per attivare imposte rilevanti per il tuo business, apri l’app Contabilità ‣ Configurazione ‣ Imposte e fai clic sul pulsante sotto la colonna Attiva.

## Configurazione¶

Per modificare o creare una **imposta** , apri l’app Contabilità ‣ Configurazione ‣ Imposte e apri un’imposta o fai clic su Nuova.

### Opzioni di base¶

#### Nome imposta¶

Il **nome dell’imposta** viene mostrato agli utenti nel backend nel campo Imposte negli [ordini di vendita](../../sales/sales.html), nelle [fatture](customer_invoices.html), moduli prodotto, ecc.

#### Calcolare le imposte¶

  * **Gruppo di imposte**

Un’imposta rappresenta una combinazione di più sotto imposte. È possibile aggiungere tutte le imposte che desideri, nell’ordine in cui vuoi vengano applicate.

Importante

Assicurati che la sequenza delle imposte sia corretta, in quanto l’ordine in cui si trovano potrebbe avere un impatto sul calcolo degli importi delle imposte stesse, specialmente se una delle imposte ha un impatto sulla base di quelle successive.

  * **Fisse**

L’imposta ha un importo fisso nella valuta predefinita. L’importo rimane invariato, indipendentemente dal prezzo di vendita.




Example

Un prodotto ha un prezzo di vendita di 1.000 $ e si applica un’imposta _fissa_ di 10 $. Abbiamo quindi:

Prezzo vendita prodotto | Prezzo imposte escluse | Imposta | Totale  
---|---|---|---  
1.000 | 1.000 | 10 | 1.010,00  
  
  * **Percentuale del prezzo**

Il _prezzo di vendita_ è la base imponibile: l’importo dell’imposta viene calcolato moltiplicando il prezzo di vendita per la percentuale d’imposta.




Example

Un prodotto ha un prezzo di vendita di 1.000 $ e si applica un’imposta del _10% sul prezzo_. Abbiamo quindi:

Prezzo vendita prodotto | Prezzo imposte escluse | Imposta | Totale  
---|---|---|---  
1.000 | 1.000 | 100 | 1.100,00  
  
  * **Percentuale sul prezzo imposta inclusa**

Il **totale** è la base imponibile: l’importo dell’imposta è una percentuale del totale.




Example

Un prodotto ha un prezzo di vendita di 1.000 $ e si applica un’imposta del _10% sul prezzo imposte incluse_. Abbiamo quindi:

Prezzo vendita prodotto | Prezzo imposte escluse | Imposta | Totale  
---|---|---|---  
1.000 | 1.000 | 111,11 | 1.111,11  
  
  * **Codice Python**

Un’imposta definita come **Codice Python** è composta da due frammenti di codice python eseguiti in un ambiente locale che contiene dati come il prezzo unitario, il prodotto o il partner. Il Codice Python definisce l’importo dell’imposta e il Codice applicabile se l’imposta deve essere applicata. La formula si trova in fondo alla scheda Definizione.




Example

Codice Python: `result = price_unit * 0.10` Codice applicabile: `result = true`

#### Attivo¶

Solo le imposte **attive** possono essere aggiunte a nuovi documenti.

Importante

Non è possibile eliminare le imposte già utilizzate. È invece possibile disattivarle per impedirne l’uso futuro.

Nota

Questo campo può essere modificato dalla vista elenco.

#### Tipo di imposta¶

Il Tipo di imposta determina l’applicazione dell’imposta che ne limita anche la visualizzazione.

  * **Vendite** : fatture cliente, imposte cliente prodotto, ecc.

  * **Acquisti** : fatture fornitore, imposte fornitore prodotto, ecc.

  * **Nessuno**




Suggerimento

Puoi utilizzare Nessuno per le imposte che vuoi includere in un Gruppo di imposte ma che non vuoi elencare con le altre imposte per vendite e acquisti.

#### Ambito imposte¶

La funzione Ambito imposte limita l’utilizzo delle imposte a un tipo di prodotto, che si tratti di **beni** o **servizi**.

### Scheda Definizione¶

Assegna con precisione l’importo della base imponibile o le percentuali dell’imposta calcolata a più conti e griglie fiscali.

  * **Basata su** :

    * Base: il prezzo sulla riga della fattura

    * % imposta: percentuale dell’imposta calcolata.

  * **Conto** : se indicato, viene registrato un movimento contabile aggiuntivo.

  * **Griglie imposte** : usate per generare automaticamente [resoconti fiscali](reporting/tax_returns.html), secondo la normativa del Paese.




### Scheda Opzioni avanzate¶

#### Etichetta su fatture¶

L’etichetta dell’imposta viene mostrata su ogni riga di fattura nella colonna Imposte. È visibile agli utenti del _front-end_ su fatture esportate, nei portali clienti, ecc.

#### Gruppo imposte¶

Seleziona il **gruppo imposta** a cui appartiene l’imposta. Il nome del gruppo viene visualizzato sopra la riga **totale** sulle fatture esportate e nei portali dei clienti.

I gruppi imposte includono varie iterazioni della stessa imposta. Può essere utile quando devi registrare la stessa imposta in modo diverso a seconda delle [posizioni di bilancio](taxes/fiscal_positions.html).

Example

Nell’esempio precedente, l’imposta 0% EU S per i clienti intracomunitari in Europa registra l’importo su conti e griglie imposte specifici. Tuttavia, per il cliente rimane un’imposta dello 0%. Per questo motivo l’etichetta indica 0% EU S, mentre il nome del gruppo fiscale sopra la riga Totale indica IVA 0%.

Importante

Le imposte hanno tre diverse etichette, ognuna delle quali ha un uso specifico. Per vedere dove vengono visualizzate, consulta la tabella che segue.

Nome imposta | Etichetta su fattura | Gruppo imposte  
---|---|---  
Backend | Imposte, colonna su fatture esportate | Sopra la riga Totale sulle fatture esportate  
  
#### Includere nel costo analitico¶

Con questa opzione attivata, l’importo dell’imposta viene assegnato allo stesso **conto analitico** della riga della fattura.

#### Includere nel prezzo¶

Con questa opzione attivata, il totale (tasse incluse) equivale al **prezzo di vendita**.

`Totale = Prezzo di vendita = Imposta calcolata-Prezzo escluso + Imposta`

Example

Un prodotto ha un prezzo di vendita di 1.000 $ e applichiamo un’imposta del _10% sul prezzo_ , che è _inclusa nel prezzo_. Abbiamo quindi:

Prezzo vendita prodotto | Prezzo imposte escluse | Imposta | Totale  
---|---|---|---  
1.000 | 900,10 | 90,9 | 1.000,00  
  
Nota

Se hai bisogno di definire con precisione i prezzi, sia quelli con tasse incluse che quelli con tasse escluse, fai riferimento alla seguente documentazione: [Tariffe B2B (imposte escluse) e B2C (imposte incluse)](taxes/B2B_B2C.html).

Nota

Per impostazione predefinita, sulle fatture viene visualizzata solo la colonna Imposte escluse. Per mostrare la colonna Imposte incluse, fai clic sul pulsante **menu a tendina** e spunta Imposte incl..

#### Determinare imponibile imposte successive¶

Con questa opzione, l’imposta totale inclusa diventa la base imponibile per le altre imposte applicate allo stesso prodotto.

Puoi configurare un nuovo gruppo imposte per includere la nuova imposta o aggiungerla direttamente alla riga di prodotto.

Avvertimento

L’ordine in cui si aggiungono le imposte a una riga di prodotto non ha alcun effetto sul calcolo degli importi. Se si aggiungono le imposte direttamente su una riga di prodotto, solo la sequenza delle imposte determina l’ordine di applicazione.

Per riordinare la sequenza, apri l’app Contabilità ‣ Configurazione ‣ Imposte e trascina e rilascia le righe accanto ai nomi delle imposte.

## Imposte aggiuntive¶

Con “Tasse aggiuntive” ci si riferisce a tasse extra rispetto a quelle standard o di base imposte dai governi. Queste tasse aggiuntive possono essere tasse di **lusso** , tasse **ambientali** , tasse di **importazione** o **dazi di esportazione** , ecc.

Nota

Il metodo di calcolo di queste imposte varia da Paese a Paese. Ti consigliamo di consultare le normative del tuo Paese per capire come calcolarle per la tua attività.

Per calcolare un’imposta aggiuntiva in Odoo, crea un’imposta, aggiungi un nome, seleziona un metodo di calcolo, stabilisci un importo e nella scheda Opzioni avanzate, spunta l’opzione Determinare imponibile imposte successive. Successivamente, trascina e rilascia le imposte in quello che è l’ordine di calcolo.

Example

  * In Belgio, la formula per calcolare una tassa ambientale è: `(prezzo del prodotto + imposta ambientale) x imposta sulle vendite`. Pertanto, la nostra imposta ambientale deve venire _prima_ dell’imposta sulle vendite nella sequenza di calcolo.

  * Nel nostro caso, abbiamo creato una tassa ambientale del 5% (Tassa ambientale) e l’abbiamo anteposta all’imposta base belga del 21%.




Vedi anche

  * [Posizioni di bilancio (mappatura fiscale e contabile)](taxes/fiscal_positions.html)

  * [Tariffe B2B (imposte escluse) e B2C (imposte incluse)](taxes/B2B_B2C.html)

  * [TaxCloud integration](taxes/taxcloud.html)

  * [Tax return (VAT declaration)](reporting/tax_returns.html)




  * [Imposte per cassa](taxes/cash_basis.html)
  * [Imposte alla fonte](taxes/retention.html)
  * [Verifica numero partita IVA (VIES)](taxes/vat_verification.html)
  * [Posizioni di bilancio (mappatura fiscale e contabile)](taxes/fiscal_positions.html)
  * [Integrazione AvaTax](taxes/avatax.html)
    * [Utilizzare AvaTax](taxes/avatax/avatax_use.html)
    * [Portale Avalara (Avatax)](taxes/avatax/avalara_portal.html)
  * [TaxCloud integration](taxes/taxcloud.html)
  * [Vendite a distanza intracomunitarie nell’UE](taxes/eu_distance_selling.html)
  * [Tariffe B2B (imposte escluse) e B2C (imposte incluse)](taxes/B2B_B2C.html)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/accounting/taxes.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](taxes/cash_basis.html "Imposte per cassa") |
  * [precedente](get_started/tax_units.html "Unità fiscali") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Contabilità e fatturazione](../accounting.html) »
  * Imposte


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
  *[FBM]: Fulfilled By Merchant
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
  *[POS]: Point Of Sale
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