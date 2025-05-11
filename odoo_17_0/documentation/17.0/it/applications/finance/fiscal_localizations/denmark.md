# Danimarca — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](ecuador.html "Ecuador") |
  * [precedente](colombia.html "Colombia") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Danimarca



# Danimarca¶

## Compliance with Danish bookkeeping requirements: data retention and integrity¶

This page outlines how Odoo complies with the Danish Bookkeeping Act, specifically regarding the storage and integrity of financial transactions and receipts. Odoo recognizes the importance of adhering to Danish regulations and has implemented robust measures to ensure clients” data is secure and compliant.

### Key requirements of the Danish Bookkeeping Act¶

The Danish Bookkeeping Act (DBA) outlines the [requirements for digital bookkeping systems](https://danishbusinessauthority.dk/requirements-digital-bookkeeping-systems):

  * **Retain transactional data and receipts:** Store all recorded transactions and receipts covered by § 3 for a minimum of five years from the end of the financial year to which they pertain.

  * **Ensure data integrity:** Prevent the company from changing, backdating, or deleting recorded transactions.

  * **Maintain data accessibility:** Store all recorded transactions in a structured and machine-readable format for the required five-year period, regardless of customer relationship status, bankruptcy, or dissolution.

  * **Provide decryption capabilities:** Ensure that encrypted bookkeeping data and receipts can be decrypted into a structured and readable format.




### Odoo compliance measures¶

For companies using Odoo on Odoo Cloud hosting specifically, these requirements are met through the following features and processes:

### Immutable transaction records¶

  * Once transactions are recorded, they cannot be deleted through the user interface.

  * All modifications are logged, providing a complete audit trail.

  * While historically dated entries can be made, Odoo records the creation date and time of the entry.




### Secure document storage¶

  * Receipts and digital vouchers are stored as attachments and integrated into the database, ensuring they are included in backups.

  * Posted documents cannot be deleted.

  * We fully support the storage of mandatory digital vouchers as defined by Danish regulations.




### Continuous data availability¶

  * Clients with active subscriptions can access all transactions and digital vouchers through Odoo.

  * Regardless of customer relations, bankruptcy, or dissolution, Odoo can provide access to transaction and digital voucher details to former clients for six years (see Data lifecycle management).




### Automated data export and secure storage¶

  * Odoo Accounting implements no automatic deletion or archival of recorded transactions, so if a company has been recording transactions for six years, the six years of history are preserved in the Odoo Accounting database.

  * As described in the [Odoo SLA](https://www.odoo.com/cloud-sla) and [Odoo Privacy Policy](https://www.odoo.com/privacy), the Odoo Cloud relies on immutable daily snapshot backups, which cannot be individually altered or deleted, even at the customer’s request, ensuring their integrity.

  * All documents and receipts stored in a database backup are available as a standard ZIP archive accompanying the SQL dump.




### Data lifecycle management¶

  * Odoo database backups are available in standard SQL dump formats at all times and include all recorded transactions.

  * The default Odoo Cloud SLA guarantees three months of backup history to all active customers. As a special guarantee for Danish companies subject to the DBA and who opt for an Odoo Cloud solution, the backup retention gets increased to six years as soon as they decide to terminate their Odoo Cloud subscription, in order to comply with the requirements of Annex 1, 4 of Executive Order 97.

  * Companies who are using Odoo products outside of the Odoo Cloud are responsible for implementing their own compliance with the DBA.




### Decryption¶

Odoo Accounting customer data on the Odoo Cloud is always stored in encrypted form (encryption at rest at storage level). When backups are retrieved, they are automatically decrypted and provided in decrypted form in standard formats for the user: SQL dumps + ZIP archive of all attached documents (file store).

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/fiscal_localizations/denmark.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](ecuador.html "Ecuador") |
  * [precedente](colombia.html "Colombia") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Danimarca


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: in-app purchases
  *[RTL]: right-to-left
  *[RST]: reStructuredText
  *[GUI]: graphical user interface
  *[TOC]: Table Of Contents
  *[SEO]: Search Engine Optimization
  *[EDI]: Electronic Data Interchange
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
  *[API]: application programming interface
  *[IVA]: imposta sul valore aggiunto
  *[MRR]: Monthly Recurring Revenue
  *[ARR]: Annual Recurring Revenue
  *[USB]: Universal Serial Bus
  *[IoT]: Internet of Things
  *[OS]: Operating System
  *[SO]: Sales Order
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
  *[POS]: Point of Sale
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
  *[SOs]: Sales Order
  *[SRI]: servicio de rentas internas
  *[ATS]: Anexo Transaccional Simplificado
  *[FPS]: Service Public Federal Finances
  *[ADW]: Average Daily Wage
  *[SII]: Servicio de Impuestos Internos
  *[CAFs]: Folio Authorization Code
  *[DTE]: Documentos Tributarios Electrónicos
  *[RUT]: Rol Único Tributario
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
  *[OTP]: one-time password
  *[GAAP]: Generally Acceptable Accounting Practices
  *[AR]: Accounts Receivable
  *[AP]: Accounts Payable
  *[CoA]: Chart of Accounts
  *[SEC]: Securities and Exchange Commission
  *[CFS]: Cash Flow Statement
  *[ACH]: Automated Clearing House
  *[NACHA]: National Automated Clearing House Association
  *[DBA]: Danish Bookkeeping Act