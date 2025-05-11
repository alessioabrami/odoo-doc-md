# Colombia — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](denmark.html "Danimarca") |
  * [precedente](chile.html "Cile") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Colombia



# Colombia¶

Odoo’s Colombian localization package provides accounting, fiscal, and legal features for databases in Colombia - such as chart of accounts, taxes, and electronic invoicing. The localization has the following [prerequisites](https://micrositios.dian.gov.co/sistema-de-facturacion-electronica/que-requieres-para-factura-electronicamente/) when using the [DIAN Own Software](https://micrositios.dian.gov.co/sistema-de-facturacion-electronica/como-puedes-facturar-electronicamente/) solution with Odoo:

  * Be registered in the [RUT](https://www.dian.gov.co/tramitesservicios/tramites-y-servicios/tributarios/Paginas/RUT.aspx) (Registro Único Tributario) with a valid NIT.

  * Have a valid digital signature certificate [approved by the ONAC](https://onac.org.co/directorio-de-acreditados/).

  * [Register and get enabled](https://micrositios.dian.gov.co/sistema-de-facturacion-electronica/proceso-de-registro-y-habilitacion-como-facturador-electronico/) by completing the certification process required by the DIAN.




Vedi anche

  * For more information on how to complete the certification process for the DIAN module, review the following [webinar](https://www.youtube.com/watch?v=l0G6iDc7NQA)

  * [Smart Tutorial - Colombian Localization](https://www.odoo.com/slides/smart-tutorial-localizacion-de-colombia-132)

  * [Documentation on e-invoicing’s legality and compliance in Colombia](../accounting/customer_invoices/electronic_invoicing/colombia.html)




## Configurazione¶

### Modules installation¶

[Install](../../general/apps_modules.html#general-install) the following modules to get all the features of the Colombian localization:

Nome | Nome tecnico | Descrizione  
---|---|---  
Colombia - Accounting | `l10n_co` | Default [fiscal localization package](../fiscal_localizations.html#fiscal-localizations-packages). This module adds the base accounting features for the Colombian localization: chart of accounts, taxes, withholdings, and identification document type.  
Electronic invoicing for Colombia with DIAN | `l10n_co_dian` | This module includes the features required for integration with the DIAN as its own software, and adds the ability to generate electronic invoices and support documents based on DIAN regulations.  
Colombian - Accounting Reports | `l10n_co_reports` | This module includes accounting reports for sending certifications to suppliers for withholdings applied.  
Electronic invoicing for Colombia with Carvajal | `l10n_co_edi` | This module includes the features required for integration with Carvajal. Adds the ability to generate the electronic invoices and support documents, based on DIAN regulations.  
Colombian - Point of Sale | `l10n_co_pos` | This module includes **Point of Sale** receipts for Colombian localization.  
  
### Informazioni aziendali¶

To configure your company information:

  1. Access your company’s contact form:

     * Go to the Contacts app and search for your company or;

     * Go to the Settings app, activate the [developer mode](../../general/developer_mode.html#developer-mode), and in the Companies section, click Update Info. Then, in the Contact field, click on the company name.

  2. Configure the following information:

     * Company Name.

     * Address: Including City, Department, and ZIP code.

     * Identification Number: Select the Identification Type (NIT, Cédula de Ciudadanía, Registro Civil, etc.). When the Identification Type is NIT, the Identification Number **must** have the _verification digit_ at the end of the ID prefixed by a hyphen (`-`).

  3. Go to the Sales & Purchase tab and configure the Fiscal Information:

     * Obligaciones y Responsabilidades: Select the fiscal responsibility for the company. (O-13 Gran Contribuyente, O-15 Autorretenedor, O-23 Agente de retención IVA, O-47 Regimen de tributación simple, R-99-PN No Aplica).

     * Gran Contribuyente: If the company is _Gran Contribuyente_ , enable this option.

     * Fiscal Regimen: Select the Tribute Name for the company (IVA, INC, IVA e INC, or No Aplica)

     * Commercial Name: If the company uses a specific commercial name and it needs to be displayed in the invoice.




Suggerimento

The data configured in the Fiscal Information section is printed in the valid fiscal PDF reports.

### Electronic invoicing credentials and DIAN environment¶

To configure the user credentials to be used to connect with the DIAN’s web service and the DIAN environment, navigate to Accounting ‣ Configuration ‣ Settings and scroll to the Colombian Electronic Invoicing section. Then, follow these steps:

  1. Select DIAN: Free Service as the Electronic Invoicing Provider.

  2. Configure the Operation Modes for the respective types of documents (_electronic invoices_ or _support documents_) to be generated from Odoo. Click Add a line, then fill in the fields:

     * Software Mode: the type of document to be generated with the operation mode.

     * Software ID: the ID generated by DIAN for the specific operation mode.

     * Software PIN: the PIN selected in the operation mode configuration in the DIAN portal.

     * Testing ID: the testing ID generated by DIAN and obtained after testing the operation mode.

  3. Configure the available Certificates to sign the electronic documents. Click Add a line, then fill in the fields:

     * Name: the name of the certificate.

     * Certificate: upload the certificate file in PEM format. In the Private Key field that appears on the screen, select an existing private key or create a new one. To do so, enter a key name and select Create and edit. Then, in the Create Private Key wizard, upload a valid Key file and click Save & Close.

  4. Configure the DIAN environment; the DIAN electronic invoicing module offers three different DIAN environments to connect with:

     * **Certification environment** : This environment is useful to pass the DIAN certification process and obtain the _Enabled_ status to invoice from Odoo. To activate it, enable both the Test environment and the Activate the certification process checkboxes.

     * **Testing environment** : This environment allows reproducing electronic invoicing flows and validations in the DIAN testing portal. To activate it, enable only the Test Environment checkbox.

     * **Production environment** : Activate production databases to generate valid electronic documents. To activate it, disable both the Test environment and the Activate the certification process checkboxes.




Nota

In a multi-company database, each company can have its own certificate.

Vedi anche

For electronic invoicing configurations using the Carvajal solution, review the following video: [Configuración de Facturación Electrónica - Localización de Colombia](https://www.youtube.com/watch?v=bzweMwTEbfY&list=PL1-aSABtP6ABxZshems3snMjx7bj_7ZsZ&index=3).

### Master data¶

#### Contatti¶

Configure the following fields on the [contact form](../../essentials/contacts.html):

  * Identification Number (VAT): Select the identification number type and enter the identification number. If the identification number type is NIT, the identification number must include the verification digit at the end, prefixed by a hyphen (`-`).

  * Fiscal Information fields in the Sales & Purchase tab.




#### Prodotti¶

Access the product’s form via Accounting ‣ Customers ‣ Products and ensure that either the UNSPSC Category field (found in the Accounting tab) or the Internal Reference field (in the General Information tab) is configured.

#### Imposte¶

To create or modify taxes, go to Accounting ‣ Configuration ‣ Taxes, and select the related tax.

If sales transactions include products with taxes, configure the Value Type field in the Advanced Options tab. Retention tax types (ICA, IVA, Fuente) are also included. This configuration is used to display taxes correctly on the invoice.

#### Sales journals¶

Once the DIAN has assigned the official sequence and prefix for the electronic invoice resolution, the sales journals related to the invoices **must** be updated in Odoo. To do so, navigate to Accounting ‣ Configuration ‣ Journals and select an existing sales journal or create a new one with the Create button.

On the sales journal form, enter the Journal Name and Type, then set a unique Short Code in the Journals Entries tab. Then, configure the following data in the Advanced Settings tab:

  * Electronic invoicing: enable UBL 2.1 (Colombia).

  * Invoicing Resolution: resolution number issued by DIAN to the company via their test set.

  * Resolution Date: initial effective date of the resolution.

  * Resolution End Date: end date of the resolution’s validity.

  * Range of Numbering (minimum): first authorized invoice number.

  * Range of Numbering (maximum): last authorized invoice number.

  * Technical Key: control key received from the DIAN portal test set or from their web service in case of the production environment.




When the database is configured for the production environment, instead of configuring these fields manually, click the Reload DIAN configuration button to obtain the DIAN resolution information from the DIAN web service.

Importante

  * The short code and resolution of the journal **must** match the ones received in the DIAN portal test set or from the MUISCA portal.

  * The invoice sequence and prefix **must** be correctly configured when the first invoice is created. Odoo automatically assigns a prefix and sequence to the following invoices.




#### Purchase journals¶

Once the DIAN has assigned the official sequence and prefix for the _support document_ related to vendor bills, the purchase journals related to their supporting documents need to be updated in Odoo. The process is similar to the configuration of the sales journals.

Vedi anche

For more information on support document journals using the Carvajal solution, review the [Documento Soporte - Localización de Colombia video](https://www.youtube.com/watch?v=UmYsFcD7xzE&list=PL1-aSABtP6ABxZshems3snMjx7bj_7ZsZ&index=8).

#### Piano dei conti¶

The [chart of accounts](../accounting/get_started/chart_of_accounts.html) is installed by default as part of the localization module. The accounts are mapped automatically in taxes, default account payable, and default account receivable. The chart of accounts for Colombia is based on the PUC (Plan Unico de Cuentas).

## Main workflows¶

### Electronic invoices¶

The following is a breakdown of the main workflow for electronic invoices with the Colombian localization:

  1. The user creates an invoice.

  2. Odoo generates the legal XML file.

  3. Odoo generates the CUFE (Invoice Electronic Code) with the electronic signature.

  4. Odoo sends a notification to DIAN.

  5. DIAN validates the invoice.

  6. DIAN accepts or rejects the invoice.

  7. Odoo generates the PDF invoice with a QR code.

  8. Odoo compresses the attached document (containing the sent XML file and the DIAN validation response) and the fiscal valid PDF into a `.zip` file.

  9. The user sends the invoice (`.zip` file) via Odoo to the acquirer.




#### Creazione fattura¶

Nota

The functional workflow taking place before an invoice validation does **not** alter the main changes introduced with the electronic invoice.

Electronic invoices are generated and sent to both the DIAN and the customer. These documents can be created from the sales order or manually generated. To create a new invoice, go to Accounting ‣ Costumers ‣ Invoices, and select Create. On the invoice form, configure the following fields:

  * Customer: customer’s information.

  * Journal: journal used for electronic invoices.

  * Electronic Invoice Type: Select the type of document. By default, Factura de Venta is selected.

  * Invoice Lines: Specify the products with the correct taxes.




Importante

When creating the first invoice related to an electronic invoicing journal, it is required to manually change the _sequence_ of the invoice to the DIAN format: `Prefix + Sequence`.

For example, format the sequence from `SETP/2024/00001` to `SETP1`.

When done, click Confirm.

#### Electronic invoice sending¶

After the invoice confirmation, click Print & Send. In the wizard that appears, make sure to enable the DIAN and Email checkboxes to send an XML to the DIAN web service and the validated invoice to the client fiscal email and click Print & Send. Then:

  * The XML document is created.

  * The CUFE is generated.

  * The XML is processed synchronously by the DIAN.

  * If accepted, the file is displayed in the chatter and the email to the client with the corresponding `.zip` file.




The DIAN tab then displays the following:

  * Signed Date: timestamp recorded of the XML creation.

  * Status: Status result obtained in the DIAN response. If the invoice was rejected, the error messages can be seen here.

  * Testing Environment: To know if the document sent was delivered to the DIAN testing environment.

  * Certification Process: To know if the document was sent as part of the certification process with the DIAN.

  * Download: To download the sent XML file, even if the DIAN result was rejected.

  * Fetch Attached Document: To download the generated attached document file included in the delivered `.zip` file to the client.




### Credit notes¶

The process for credit notes is the same as for invoices. To create a credit note with reference to an invoice, go to Accounting ‣ Customers ‣ Invoices. On the invoice, click Add Credit Note, and complete the following information:

  * Credit Method: Select the type of credit method.

    * Partial Refund: Use this option when it is a partial amount.

    * Full Refund: Use this option if the credit note is for the full amount.

    * Full refund and new draft invoice: Use this option if the credit note is auto-validated and reconciled with the invoice. The original invoice is duplicated as a new draft.

  * Reason: Enter the reason for the credit note.

  * Reversal Date: Select if you want a specific date for the credit note or if it is the journal entry date.

  * Use Specific Journal: Select the journal for your credit note or leave it empty if you want to use the same journal as the original invoice.

  * Refund Date: If you chose a specific date, select the date for the refund.




Once reviewed, click the Reverse button.

### Debit notes¶

The process for debit notes is similar to credit notes. To create a debit note with reference to an invoice, go to Accounting ‣ Customers ‣ Invoices. On the invoice, click the Add Debit Note button, and enter the following information:

  * Reason: Type the reason for the debit note.

  * Debit note date: Select the specific options.

  * Copy lines: Select this option if you need to register a debit note with the same lines of invoice.

  * Use Specific Journal: Select the printer point for your debit note, or leave it empty if you want to use the same journal as the original invoice.




When done, click Create Debit Note.

### Support document for vendor bills¶

With master data, credentials, and the purchase journal configured for support documents related to vendor bills, you can start using _support documents_.

Support documents for vendor bills can be created from your purchase order or manually. Go to Accounting ‣ Vendors ‣ Bills and fill in the following data:

  * Vendor: Enter the vendor’s information.

  * Bill Date: Select the date of the bill.

  * Journal: Select the journal for support documents related to the vendor bills.

  * Invoiced Lines: Specify the products with the correct taxes.




Once reviewed, click the Confirm button. Upon confirmation, an XML file is created and automatically sent to Carvajal.

### Common errors¶

During the XML validation, the most common errors are related to missing master data. In such cases, a validation error message is displayed and sending is blocked.

If the invoice was sent and set as _Rejected_ by the DIAN, the error messages are visible by clicking the __(info circle) icon next to the Status field in the DIAN tab. Using the reported error codes, it is possible to review solutions to apply before re-sending.

After the master data or other issues are corrected, it is possible to reprocess the XML again. Do so by following the electronic invoice sending flow.

## Rapporti finanziari¶

### Certificado de Retención en ICA¶

This report is a certification to vendors for withholdings made for the Colombian Industry and Commerce (ICA) tax. The report can be found under Accounting ‣ Reporting ‣ Colombian Statements ‣ Certificado de Retención en ICA.

Click the __(gear) icon to display options to Download Excel and Copy to Documents.

### Certificado de Retención en IVA¶

This report issues a certificate on the amount withheld from vendors for VAT withholding. The report can be found under Accounting ‣ Reporting ‣ Colombian Statements ‣ Certificado de Retención en IVA.

Click the __(gear) icon to display options to Download Excel and Copy to Documents.

### Certificado de Retención en la Fuente¶

This certificate is issued to partners for the withholding tax that they have made. The report can be found under Accounting ‣ Reporting ‣ Colombian Statements ‣ Certificado de Retención en Fuente.

Click the __(gear) icon to display options to Download Excel and Copy to Documents.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/finance/fiscal_localizations/colombia.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](denmark.html "Danimarca") |
  * [precedente](chile.html "Cile") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Colombia


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
  *[NIT]: El Número de Identificación Tributaria