# Uruguay — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](vietnam.html "Vietnam") |
  * [precedente](united_states.html "Stati Uniti") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Uruguay



# Uruguay¶

## Introduzione¶

With the Uruguayan localization, you can generate electronic documents with its XML, fiscal folio, electronic signature and connection to tax authority Dirección General Impositiva (DGI) through Uruware.

The supported documents are:

  * e-Invoice, e-Invoice Credit Note, e-Invoice Debit Note;

  * e-Ticket, e-Ticket Credit Note, e-Ticket Debit Note;

  * Export e-Invoice, Export e-Invoice Credit Note, Export e-Invoice Debit Note.




The localization requires an Uruware account, which enables users to generate electronic documents within Odoo.

Vedi anche

[Documentation on e-invoicing’s legality and compliance in Uruguay](../accounting/customer_invoices/electronic_invoicing/uruguay.html)

### Glossary¶

The following terms are used throughout the Uruguayan localization:

  * **DGI** : _Dirección General Impositiva_ is the government entity responsible for enforcing tax payments in Uruguay.

  * **EDI** : _Electronic Data Interchange_ refers to the sending of electronic documents.

  * **Uruware** : is the third-party organization that facilitates the interchange of electronic documents between companies and the Uruguayan government.

  * **CAE** : _Constancia de Autorización de Emisión_ is a document requested from the tax authority’s website to enable electronic invoice issuance.




## Configurazione¶

### Modules installation¶

[Install](../../general/apps_modules.html#general-install) the following modules to get all the features of the Uruguayan localization:

Nome | Nome tecnico | Descrizione  
---|---|---  
Uruguay - Accounting | `l10n_uy` | The default [fiscal localization package](../fiscal_localizations.html). It adds accounting characteristics for the Uruguayan localization, which represent the minimum configuration required for a company to operate in Uruguay according to the guidelines set by the DGI. The module’s installation automatically loads: chart of accounts, taxes, documents types, and tax supported types.  
Uruguay Accounting EDI | `l10n_uy_edi` | Includes all the technical and functional requirements to generate and validate [Electronics Documents](../accounting/customer_invoices/electronic_invoicing.html), based on the technical documentation published by the DGI. The authorized documents are listed above.  
  
Nota

Odoo automatically installs the base module **Uruguay - Accounting** when a database is installed with `Uruguay` selected as the country. However, to enable electronic invoicing, the **Uruguay Accounting EDI** (`l10n_uy_edi`) module needs to be manually [installed](../../general/apps_modules.html#general-install).

### Azienda¶

To configure your company information, open the **Settings** app, scroll down to the Companies section, click Update Info, and configure the following:

  * Company Name

  * Address, including the Street, City, State, ZIP, and Country

  * Tax ID: enter the identification number for the selected taxpayer type.

  * DGI Main Branch Code: this is part of the XML when creating an electronic document. If this field is not set, all electronic documents will be rejected.

To find the DGI Main Branch Code, follow these steps:

    1. From your [DGI account](https://servicios.dgi.gub.uy/serviciosenlinea), go to Servicios en línea DGI ‣ Registro único tributario ‣ Consulta de datos.

    2. Select Consulta de Datos Registrales ‣ Consulta de Datos de Entidades.

    3. Open the generated PDF to get the _DGI Main Branch Code_ from the Domicilio Fiscal Número de Local section.




After configuring the company in the database settings, navigate to Contacts and search for your company to verify the following:

  * the company type is set to Company.

  * the Identification Number Type is RUT / RUC.




### Set up a Uruware account¶

To set up a Uruware account, follow these steps:

  1. Verify that you have a valid Odoo subscription.

  2. Locate the Uruware credentials settings by navigating to the Accounting ‣ Configuration ‣ Settings.

  3. Scroll down to the Uruguayan Localization section and select the environment (Production or Testing).

  4. Click on Create Uruware Account.




Upon doing so, an email is sent to the address associated with your Odoo subscription with the password to enter Uruware’s portal and set up your account.

Suggerimento

  * The email with the credentials is not immediate; it might take up to 48 hours for the account to be created.

  * The company’s Tax ID needs to be set up to be able to create an Uruware account.

  * The password sent expires after 24 hours. In this case, reset it by using the _Forgot Password_ link in Uruware’s portal.




Nota

This action will create an account with Uruware with the following information:

  * Legal name (razón social)

  * RUT from the company

  * Username (the Odoo subscription email or `RUT`.odoo. For example: `213344556677.odoo`)

  * Odoo database link




To ensure your account is created correctly, please add any missing information from above.

Once the account is created and you have received the email containing the credentials, configure your accounts directly in the Uruware [testing portal](https://odootest.ucfe.com.uy/Gestion/) or [production portal](https://prod6109.ucfe.com.uy/Gestion/):

Use the account credentials in the email to log in to the to the corresponding ([test](https://odootest.ucfe.com.uy/Gestion/) or [production](https://prod6109.ucfe.com.uy/Gestion/)) portal.

In Uruware’s portal, the following steps are needed to be able to issue invoices from Odoo:

  1. Complete and correct the company’s information.

  2. Add your digital certificate.

  3. Add your CAEs for each document-type you plan to issue.

  4. Configure the format of the PDF to be printed and sent to your customers.




Importante

Be sure to configure two accounts, one for testing and one for production. The certificate is needed in both environments, but CAEs are only needed in production.

Vedi anche

  * [Odoo Tutorials: Uruguay Localization](https://www.odoo.com/slides/smart-tutorial-localizacion-de-uruguay-432)

  * [Odoo Help Forum: Uruguay](https://www.odoo.com/forum/help-1?search=l10n_uy)




### Electronic invoice data¶

To configure the electronic invoice data, an environment and credentials need to be configured. To do so, navigate to Accounting ‣ Configuration ‣ Settings and scroll down to the Uruguayan Localization section.

First, select the UCFE Web Services environment:

  * Production: for production databases. In this mode, electronic documents are sent to DGI through Uruware for their validation.

  * Testing: for test databases. In this mode, the direct connection flows can be tested, with the files sent to the DGI testing environment through Uruware.

  * Demo: files are created and accepted automatically in demo mode but are **not** sent to the DGI. For this reason, rejection errors will not appear in this mode. Every internal validation can be tested in demo mode. Avoid selecting this option in a production database.




Nota

Using Demo mode does not require a Uruware account.

Then, enter the Uruware Data:

  * Uruware WS Password

  * Commerce Code

  * Terminal Code




Nota

This data can be obtained from the Uruware portal after configuring the Uruware account.

To get the Uruware WS Password, go to Configuration ‣ Company ‣ Edit and look for the Validators and Additional Information tab to find WS Password.

To get the Commerce Code, go to Configuration ‣ Branches.

To get the Terminal Code, go to Configuration ‣ Issuing Points.

### Master data¶

#### Piano dei conti¶

The [chart of accounts](../accounting/get_started/chart_of_accounts.html) is installed by default as part of the set of data included in the localization module, the accounts are mapped automatically in taxes, default accounts payable, and default accounts receivable.

Accounts can be added or deleted according to the company’s needs.

Vedi anche

[Piano dei conti](../accounting/get_started/chart_of_accounts.html)

#### Contatti¶

To create a contact, navigate to Contacts app and select New. Then enter the following information:

  * Company Name

  * Address:

    * Street: required to confirm an electronic invoice.

    * City

    * State

    * ZIP

    * Country: required to confirm an electronic invoice.

  * Identification Number:

    * Type: select a identification type.

    * Number: required to confirm an electronic invoice.




#### Imposte¶

As part of the Uruguay localization module, taxes are automatically created with its configuration and related financial accounts.

#### Document types¶

Some accounting transactions, like _customer invoices_ and _vendor bills_ are classified by document types. These are defined by the government fiscal authorities, in this case by the DGI.

Each document type can have a unique sequence per journal where it is assigned. The data is created automatically when the localization module is installed, and the information required for the document types is included by default.

To review the document types included in the localization, navigate to Accounting ‣ Configuration ‣ Document Types.

Nota

In Uruguay, CAEs **must** be uploaded in Uruware. Sequences (and PDFs) are received in Odoo from Uruware, based on their CAEs. CAEs are **only** used in production. When testing, only a range of sequences used in Uruware need to be set.

#### Sales journals¶

To generate and confirm an electronic document that will be validated by DGI, the sales journal needs to be configured with the following:

  * Invoicing Type: by default Electronic option is set. This is necessary to send electronic documents via web service to the Uruguayan government through Uruware. The other option, Manual, is for open invoices previously stamped in another system, for example, in the DGI.

  * Use Documents?: Activate this option if this journal will use documents from the list of document types in Odoo.




## Workflow¶

Once you have configured your database, you can create your documents.

### Sales documents¶

#### Fatture cliente¶

[Customer invoices](../accounting/customer_invoices.html) are electronic documents that, when validated, are sent to DGI via Uruware. These documents can be created from your sales order or manually. They must contain the following data:

  * Customer: type the customer’s information.

  * Due date: to compute if the invoice is due now or later (_contado_ or _crédito_ , respectively).

  * Journal: select the electronic sales journal.

  * Document Type: document type in this format, for example, `(111) e-Invoice`.

  * Products: specify the product(s) with the correct taxes.




Nota

Every document type has a specific credit note and debit note (e.g., the document type (111) e-Invoice has an (112) e-Invoice Credit Note).

#### Customer credit note¶

The [Customer credit note](../accounting/customer_invoices/credit_notes.html) is an electronic document that, when validated, is sent to DGI via Uruware. It is necessary to have a validated (posted) invoice to register a credit note. On the invoice, click the Credit note button to access the Create credit note form, then complete the following information:

  * Reason: type the reason for the credit note.

  * Journal: select the journal that has to be electronic and has the Use Documents? option active.

  * Document Type: select the credit note document type.

  * Reversal Date: type the date.




#### Customer debit note¶

The [Customer debit note](../accounting/customer_invoices/credit_notes.html) is an electronic document that, when validated, is sent to DGI via Uruware. It is necessary to have a validated (posted) invoice to register a debit note. On the invoice, click the __( action menu) icon, select the Debit note option to access the Create credit note form, then complete the following information:

  * Reason: Type the reason for the debit note.

  * Journal: Select the journal that has to be electronic and has the Use Documents? option active.

  * Copy lines: Tick the checkbox to copy the invoice lines to the debit note.

  * Debit note date: Type the date.




Nota

Confirm the invoice to create it with an internal reference. To send the document to DGI via Uruware, click on Send and Print and select the checkbox Create CFE. The legal document sequence (number) is brought from Uruware once the document has been processed. Make sure you have CAEs available in Uruware.

Nota

The PDF of the validated document is pulled from Uruware following the specification by the Uruguayan government (DGI).

## Addendas and disclosures¶

_Addendas_ and _disclosures_ are additional notes and comments added to an electronic document that can be mandatory or optional. To create a new addenda, go to Accounting ‣ Configuration ‣ Addendas and disclosures and click New.

Enter the following information:

  * Name: name of the addenda or mandatory disclosure.

  * Type: Select the type of remark, this will add it to the specific section in the XML.

  * Is legend: Select this box if the text is a mandatory disclosure, leave it blank if it is additional information.

  * Content: Add the complete text of the addenda or disclosure.




### Leyenda and additional information in product¶

To add a _leyenda_ or additional information to the product and XML, it is necessary to add the preconfigured addenda and disclosure to the product in the invoice line. Add the _leyenda_ in the Disclosure field of the product specified in the line.

### Leyenda and additional information¶

To add a _leyenda_ or additional information to the electronic invoice and XML, access the invoice, go to the Other Info tab, and select the desired addenda in the Addenda and Disclosure field. The addenda and disclosures added here will appear in the XML and visibly in the PDF document.

This applies to the following types of _addendas_ :

  * Documento

  * Emittente

  * Receiver

  * Addendas




Nota

To add a temporary note to the electronic document, use the Terms and Conditions field. This information will be sent in the addenda of the invoice, but it won’t be saved for future documents.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/finance/fiscal_localizations/uruguay.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](vietnam.html "Vietnam") |
  * [precedente](united_states.html "Stati Uniti") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Uruguay


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