# Spagna — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](switzerland.html "Svizzera") |
  * [precedente](singapore.html "Singapore") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Spagna



# Spagna¶

## Configurazione¶

Install the 🇪🇸 **Spanish** [fiscal localization package](../fiscal_localizations.html) to get all the default accounting features of the Spanish localization.

Three **Spanish** localizations exist, each with its own pre-configured **PGCE** charts of accounts:

  * Spain - SMEs (2008);

  * Spain - Complete (2008);

  * Spain - Non-profit entities (2008).




To select the one to use, go to Accounting ‣ Configuration ‣ Settings and select a package in the Fiscal Localization section.

Avvertimento

You can only change the accounting package as long as you have not created any accounting entry.

Vedi anche

  * [Documentation on e-invoicing’s legality and compliance in Spain](../accounting/customer_invoices/electronic_invoicing/spain.html)

  * [Documentation on e-invoicing’s legality and compliance in the Basque Country](../accounting/customer_invoices/electronic_invoicing/basque_country.html)




## Piano dei conti¶

You can reach the **Chart of Accounts** by going to Accounting ‣ Configuration ‣ Accounting: Chart of Accounts.

Suggerimento

When you create a new Odoo Online database, **Spain - SMEs (2008)** is installed by default.

## Imposte¶

Default Spain-specific taxes are created automatically when the Spanish - Accounting (PGCE 2008) (l10n_es) module is installed, and tax reports are available when installing the module Spain - Accounting (PGCE 2008) (l10n_es_reports). Each tax impacts the Spain-specific **tax reports (Modelo)** , available by going to Accounting ‣ Reporting ‣ Statements Reports: Tax Report.

## Report¶

Here is the list of Spanish-specific statement reports available:

  * Balance Sheet;

  * Profit & Loss;

  * EC Sales List;

  * Tax Report (Modelo 111);

  * Tax Report (Modelo 115);

  * Tax Report (Modelo 130);

  * Tax Report (Modelo 303);

  * Tax Report (Modelo 347);

  * Tax Report (Modelo 349);

  * Tax Report (Modelo 390).




You can access Spain-specific tax reports by clicking on the **book** icon when on a report and selecting its Spain-specific version: (ES).

### Modelo 130¶

#### Change the percentage¶

If you wish to change the percentage computation of the box [04] under the I section and/or of the box [09] under the II section:

  1. Activate the [developer mode](../../general/developer_mode.html#developer-mode), go to Accounting ‣ Reporting ‣ Tax Report, and select the report Tax report (Modelo 130).

  2. Click the __( cogs) icon to the right of Report: Tax Report (Mod 130) (ES).

  3. Click the box you wish to change, and in the pop-up window, click on the percentage line. In the new pop-up window, change the value in the Formula field to the percentage you wish to apply. Repeat this action if you wish to modify the other box as well.




#### Report agriculture activity¶

If you wish to have any amount input in the II section (from boxes [08] to [11]), you must change the **industry** of the corresponding contact to Agriculture:

  1. Go to the contact form (Accounting ‣ Customers ‣ Customers or Accounting ‣ Vendors ‣ Vendors, for example), and select a contact.

  2. In the Sales & Purchase tab, set the Industry field to Agriculture.




Repeat this operation for all contacts related to the **agriculture** industry.

## TicketBAI¶

[Ticket BAI](https://www.gipuzkoa.eus/es/web/ogasuna/ticketbai) or **TBAI** is an e-Invoicing system used by the Basque government and its three provincial councils (Álava, Biscay, and Gipuzkoa).

Odoo supports the **TicketBAI (TBAI)** electronic invoicing format for all three regions of the **Basque Country**. To enable **TicketBAI** , set your company’s Country and Tax ID under Settings ‣ General Settings in the Companies section.

Then, [install](../../general/apps_modules.html#general-install) the module Spain -TicketBAI (l10n_es_edi_TBAI), go to Accounting ‣ Configuration ‣ Settings, and select a **region** in the Spain Localization section’s Tax Agency for TBAI field.

Once a region is selected, click Manage certificates (SII/TicketBAI), then click New, upload the certificate, and enter the password provided by the tax agency.

Avvertimento

If you are testing certificates, enable Test Mode in the Spain Localization section, which can be found under Accounting in the **Settings** app.

### Caso d’uso¶

Once an invoice has been [created](../accounting/customer_invoices.html) and confirmed, a TicketBAI **banner** appears at the top.

Odoo sends invoices through TicketBAI automatically every **24 hours**. However, you can click Process now to send the invoice immediately.

When the invoice is **sent** , the status of the field Electronic Invoice changes to Sent, and the XML file can be found in the **chatter**. Under the EDI Documents tab, you can see the traceability of other generated documents related to the invoice (e.g., if the invoice should also be sent through the **SII** , it will appear here).

Nota

The TBAI **QR code** is displayed on the invoice PDF.

## FACe¶

[FACe](https://face.gob.es/en) is the e-Invoicing platform used by the public administrations in Spain to send electronic invoices.

Before configuring the FACe system, [install](../../general/apps_modules.html#general-install) the Spain - Facturae EDI (l10n_es_edi_facturae) module and other **Facturae EDI** -related modules.

To configure FACe, follow these steps:

  1. Go to Accounting ‣ Configuration ‣ Certificates.

  2. Click New to create a new certificate.

  3. Complete the fields, including uploading the file of the Certificate provided by the tax agency and the provided Certificate Password.




Nota

If using the Invoicing app instead of Accounting, go to Invoicing ‣ Configuration ‣ Certificates.

### Caso d’uso¶

Once you have [created](../accounting/customer_invoices.html) an invoice and confirmed it, click Send & Print. Make sure Generate Facturae edi file is enabled, and click Send & Print again. Once the invoice is sent, the generated XML file is available in the **chatter**.

Avvertimento

The file is **NOT** automatically sent. You have to send it yourself manually.

Suggerimento

You can send **FACe** XML files in batch through [the governmental portal](https://www.facturae.gob.es/formato/Paginas/descarga-aplicacion-escritorio.aspx).

### Administrative centers¶

In order for **FACe** to work with **administrative centers** , the invoice _must_ include specific data about the centers.

Nota

Make sure to have the Spain - Facturae EDI - Administrative Centers Patch (l10n_es_edi_facturae_adm_centers) module [installed](../../general/apps_modules.html#general-install).

To add **administrative centers** , create a new **contact** to add to the **partner** company. Select FACe Center as the **type** , assign one or more **role(s)** to that contact, and Save. The **three** roles usually required are:

  * Órgano gestor: Receptor (Receiver);

  * Unidad tramitadora: Pagador (Payer);

  * Oficina contable: Fiscal (Fiscal).




Suggerimento

  * If administrative centers need different Codes per role, you _must_ create different centers for each role.

  * When an electronic invoice is created using a partner with **administrative centers** , _all_ administrative centers are included in the invoice.

  * You can add one contact with multiple roles or multiple contacts with a different role each.




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/finance/fiscal_localizations/spain.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](switzerland.html "Svizzera") |
  * [precedente](singapore.html "Singapore") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Spagna


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
  *[FBM]: Fulfilled by Merchant
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
  *[SIREN]: Système d'identification du répertoire des entreprises, Business Directory Identification System
  *[MICR]: Magnetic Ink Character Recognition