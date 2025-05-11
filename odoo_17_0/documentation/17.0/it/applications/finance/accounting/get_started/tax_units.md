# Unità fiscali — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../taxes.html "Imposte") |
  * [precedente](avg_price_valuation.html "Prezzo medio sulla merce resa") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Esordiente](../get_started.html) »
  * Unità fiscali



# Unità fiscali¶

Importante

Applicabile solo se lavori in un ambiente con più aziende.

Una **unità fiscale** è un gruppo di imprese soggette a IVA che sono legalmente indipendenti l’una dall’altra, ma che sono strettamente collegate dal punto di vista finanziario, organizzativo ed economico e quindi considerate la stessa impresa soggetta all’imposta sul valore aggiunto. Le **unità fiscali** non sono obbligatorie, ma se vengono create, le società che le compongono devono appartenere allo stesso **Paese** , utilizzare la stessa **valuta** ed è necessario designare una società come società **rappresentativa** della **unità fiscale**. Le **unità fiscali** ricevono una specifica **Partita IVA** destinata esclusivamente alle **dichiarazioni fiscali**. Le aziende **costituenti** mantengono la propria **Partita IVA** utilizzata per **fini commerciali**.

Example

L’azienda **A** deve 300.000,00 € di imposte IVA e l’impresa **B** può recuperare 280.000,00 € di imposte IVA. Insieme formano una **unità fiscale** in modo da bilanciare i due importi e devono pagare congiuntamente solo 20.000,00 € di imposte IVA.

## Configurazione¶

Per creare una **unità fiscale** , apri l’app Contabilità ‣ Configurazione ‣ Unità fiscali e fai clic su Nuova. Inserisci un **nome** per l’unità, seleziona un Paese, le Aziende da incorporare nell’unità, la Azienda principale e la Partita IVA dell’azienda **costituente** di quell’unità fiscale.

### Posizione di bilancio¶

Poiché le transazioni tra costituenti della stessa **unità fiscale** non sono soggette all’IVA, è possibile creare una mappatura fiscale (posizione fiscale) per evitare l’applicazione dell’IVA sulle transazioni tra costituenti.

Assicurarsi che sia stata selezionata una società costituente, quindi andare in Contabilità ‣ Configurazione ‣ Posizioni fiscali e Creare una nuova **posizione fiscale**. Fare clic sulla scheda Mappatura fiscale, selezionare la Imposta sul prodotto solitamente applicata alle transazioni **non costituenti** e in Imposta da applicare, selezionare l’imposta dello 0% da applicare alle transazioni **costituenti**.

Fare lo stesso per la scheda Account Mapping, se necessario, e ripetere questa procedura per **ogni** azienda costituente del database.

Example

A seconda del vostro localization package 1, le tasse possono variare rispetto alla schermata visualizzata.

Quindi, assegnare la posizione fiscale aprendo l’applicazione **Contatti**. Cercare un’azienda **costituente** e aprire la **scheda** del contatto. Fare clic sulla scheda Vendite e acquisti e nel campo Posizione fiscale inserire la **posizione fiscale** creata per la **tax unit**. Ripetere la procedura per ogni modulo della scheda aziendale del **costituente** , su ogni database aziendale.

Vedi anche

../tasse/posizioni_fiscali.

## Resoconto FISCALE¶

L’azienda **rappresentativa** può accedere al rapporto fiscale aggregato della **unità fiscale** andando in Accounting ‣ Reporting ‣ Tax Report, e selezionando la **unità fiscale** in Tax Unit. Questo rapporto contiene le transazioni aggregate di tutti i **costituenti** e l’esportazione .XML contiene il nome e il numero di IVA della **società principale**.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/accounting/get_started/tax_units.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../taxes.html "Imposte") |
  * [precedente](avg_price_valuation.html "Prezzo medio sulla merce resa") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Esordiente](../get_started.html) »
  * Unità fiscali


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
  *[VAT]: Value Added Tax
  *[SMP]: Service Metadata Publisher