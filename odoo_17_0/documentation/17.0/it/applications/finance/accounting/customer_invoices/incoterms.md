# Termini di resa — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../vendor_bills.html "Fatture fornitore") |
  * [precedente](epc_qr_code.html "Codici QR EPC") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Fatture cliente](../customer_invoices.html) »
  * Termini di resa



# Termini di resa¶

I termini di resa sono termini commerciali standardizzati utilizzati nelle transazioni internazionali per definire i diritti e le responsabilità di acquirenti e venditori. Stabiliscono gli obblighi relativi alla consegna delle merci, al trasferimento dei rischi e alla distribuzione dei costi tra le parti coinvolte. I termini di resa specificano dettagli importanti, come il momento in cui il rischio e i costi vengono trasferiti dal venditore all’acquirente, la responsabilità per il trasporto, l’assicurazione, lo sdoganamento e altri aspetti rilevanti della transazione.

Nota

Per impostazione predefinita, su Odoo sono disponibili tutti gli 11 termini di resa:

  * **EXW** : franco fabbrica

  * **FCA** : franco vettore

  * **FAS** : franco sottobordo

  * **FOB** : franco a bordo

  * **CFR** : costo e nolo

  * **CIF** : costo, assicurazione, nolo

  * **CPT** : porto pagato fino a

  * **CIP** : trasporto e assicurazione pagati fino a

  * **DPU** : reso al luogo di destinazione scaricato

  * **DAP** : reso al luogo di destinazione

  * **DDP** : reso sdoganato




Vedi anche

  * [Intrastat](../reporting/intrastat.html)

  * [Fatture cliente](../customer_invoices.html)

  * [Fatture fornitore](../vendor_bills.html)




## Stabilire un termine di resa¶

Per stabilire manualmente un termine di resa, crea una fattura cliente o fornitore, fai clic sulla scheda Altre informazioni e seleziona il Termine di resa.

### Posizione termine di resa¶

Nella fattura cliente o fornitore è possibile aggiungere una posizione rilevante per il termine di resa scelto nella scheda Altre informazioni nel campo Ubicazione termine di resa.

Example

Se il codice del termine di resa scelto è `CIF` (costo, assicurazione, nolo), l’ubicazione associata deve essere il porto di destinazione dove verranno consegnati i beni.

## Configurazione termini di resa predefinita¶

È possibile impostare una regola predefinita per popolare **automaticamente** il campo Termini di resa su tutte le nuove fatture cliente e fornitore create. Sotto Contabilità/Fatturazione ‣ Configurazione ‣ Impostazioni, scorri in basso fino alla sezione Fatture cliente e seleziona un termine di resa nel campo Termine di resa predefinito.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/accounting/customer_invoices/incoterms.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../vendor_bills.html "Fatture fornitore") |
  * [precedente](epc_qr_code.html "Codici QR EPC") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Fatture cliente](../customer_invoices.html) »
  * Termini di resa


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