# Brasile — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](canada.html "Canada") |
  * [precedente](belgium.html "Belgio") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Brasile



# Brasile¶

## Introduzione¶

With the Brazilian localization, sales taxes can be automatically computed and electronic invoices for goods (NF-e) and services (NFS-e) can be sent using AvaTax (Avalara) through API calls. Moreover, taxes for services can be configured.

For the goods and services tax computation and electronic invoicing process, you need to configure the contacts, company, products, and create an account in AvaTax which needs to be configured in the general settings.

For the services taxes, you can create and configure them from Odoo directly without computing them with AvaTax.

The localization also includes taxes and a chart of accounts template that can be modified if needed.

Vedi anche

Links to helpful resources for the Brazilian localization, including onboarding materials and videos:

  * [Onboarding checklist for new users](https://docs.google.com/document/d/e/2PACX-1vSNYTYVnR_BzvQKL3kn5YdVzPjjHc-WHw_U3udk5tz_dJXo69woj9QrTMinH_siyOX2rLGjvspvc8AF/pub).

  * [YouTube playlist - Brazil (Localization)](https://youtube.com/playlist?list=PL1-aSABtP6ADqexw4YNCbKPmpFggajxlX&si=RgmZR3Jco3223Np4).

  * [YouTube playlist - Tutoriais Odoo em Português](https://youtube.com/playlist?list=PL1-aSABtP6ACGOW2UREePGjHQ2Bgdy-UZ&si=j6tiI36eB7BoKVQB).

  * [Documentation on e-invoicing’s legality and compliance in Brazil](../accounting/customer_invoices/electronic_invoicing/brazil.html)




## Configurazione¶

### Modules installation¶

[Install](../../general/apps_modules.html#general-install) the following modules to get all the features of the Brazilian localization:

Nome | Nome tecnico | Descrizione  
---|---|---  
Brazilian - Accounting | `l10n_br` | Default [fiscal localization package](../fiscal_localizations.html#fiscal-localizations-packages), which represents having the Generic Brazilian chart of accounts and Taxes, together with document types and identification types.  
Brazil - Accounting Reports | `l10n_br_reports` | Accounting reports for Brazil.  
AvaTax Brazil & AvaTax Brazil for Services | `l10n_br_avatax` & `l10n_br_avatax_services` | Goods and Services tax computation through Avalara.  
Brazilian Accounting EDI & Brazilian Accounting EDI for services | `l10n_br_edi` & `l10n_br_edi_services` | Provides electronic invoicing for goods and services for Brazil through AvaTax.  
Brazil Pix QR codes | `l10n_br_pix` | Implements Pix QR codes for Brazil.  
  
### Configure your company¶

To configure your company information, go to the Contacts app and search the name given to your company.

  1. Select the Company option at the top of the page. Then, configure the following fields:

     * Nome

     * Address: add City, State, Zip Code, Country

       * In the Street field, enter the street name, number, and any additional address information.

       * In the Street 2 field, enter the neighborhood.

     * Identification Number: CNPJ or CPF

     * Tax ID: associated with the identification type

     * IE: State registration

     * IM: Municipal registration

     * SUFRAMA code: Superintendence of the Manaus Free Trade Zone - add if applicable

     * Phone

     * E-mail

  2. Configure the Fiscal Information within the Sales and Purchase tab:

     * Add the Fiscal Position for AvaTax Brazil.

     * Tax Regime: Federal Tax Regime

     * ICMS Taxpayer Type: indicates ICMS regime, Exempt status, or Non-Taxpayer

     * Main Activity Sector

  3. Configure the following extra Fiscal Information if you are going to issue NFS-e:

     * Add the Fiscal Position for AvaTax Brazil.

     * COFINS Details: Taxable, Not Taxable, Taxable with rate 0%, Exempt, Suspended

     * PIS Details Taxable, Not Taxable, Taxable with rate 0%, Exempt, Suspended

     * CSLL Taxable If the company is subject to CSLL or not

  4. Finally, upload a company logo and save the contact.




Nota

If you are a simplified regime, you need to configure the ICMS rate under Accounting ‣ Configuration ‣ Settings ‣ Taxes ‣ AvaTax Brazil.

### Configure AvaTax integration¶

Avalara AvaTax is a tax calculation and electronic invoicing provider that can be integrated in Odoo to automatically compute taxes by taking into account the company, contact (customer), product, and transaction information to retrieve the correct tax to be used and process the e-invoice afterward with the government.

Using this integration requires [In-App-Purchases (IAPs)](../../essentials/in_app_purchase.html) to compute the taxes and to send the electronic invoices. Whenever you compute taxes, send an electronic document (NF-e, NFS-e, etc), or perform any electronic flow (NF-e Cancellation, Correction letter, Invalidate invoice number range), an API call is made using credits from your [IAP credits balance](https://iap.odoo.com/iap/in-app-services/819).

Nota

  * Odoo is a certified partner of Avalara Brazil.

  * You can [buy IAP credit on odoo.com](https://iap.odoo.com/iap/in-app-services/819).

  * On creation, new databases receive 500 free credits.




#### Credential configuration¶

To activate AvaTax in Odoo, you need to create an account. To do so, go to Accounting ‣ Configuration ‣ Settings ‣ Taxes, and in the AvaTax Brazil section, add the administration email address to be used for the AvaTax portal in the AvaTax Portal Email, and then click on Create account.

Avvertimento

When **testing** or **creating a production** AvaTax Portal Email integration in a sandbox or production database, use a real email address, as it is needed to log in to the Avalara Portal and set up the certificates, whether you want to test or use it on production.

There are two different Avalara Portals, one for testing and one for production:

  * Sandbox: <https://portal.sandbox.avalarabrasil.com.br/>

  * Production: <https://portal.avalarabrasil.com.br/>




When you create the account from Odoo, be sure to select the right environment. Moreover, the email used to open the account cannot be used to open another account. Save your API ID and API Key when you create the account from Odoo.

After you create the account from Odoo, you need to go to the Avalara Portal to set up your password:

  1. Access the [Avalara portal](https://portal.avalarabrasil.com.br/Login).

  2. Click on Meu primeiro acesso.

  3. Add the email address you used in Odoo to create the Avalara/AvaTax account, and then click Solicitar Senha.

  4. You will receive an email with a token and a link to create your password. Click on this link and copy-paste the token to allocate your desired password.




Suggerimento

You can start using AvaTax in Odoo for tax computation **only** without creating a password and accessing the Avalara portal in the Odoo database. However, in order to use the electronic invoice service, you **must** access the AvaTax portal and upload your certificate there.

Nota

You can transfer API credentials. Use this only when you have already created an account in another Odoo instance and wish to reuse it.

#### A1 certificate upload¶

In order to issue electronic invoices, a certificate needs to be uploaded to the [AvaTax portal](https://portal.avalarabrasil.com.br/Login).

The certificate will be synchronized with Odoo, as long as the external identifier number in the AvaTax portal matches - without special characters - with the CNPJ number, and the identification number (CNPJ) in Odoo matches with the CNPJ in AvaTax.

Importante

To issue NFS-e, some cities require that you link the certificate within the City Portal system before issuing NFS-e from Odoo.

If you receive an error message from the city that says Your certificate is not linked to the user, that means this process needs to be done in the city portal.

### Configure master data¶

#### Piano dei conti¶

The [chart of accounts](../accounting/get_started/chart_of_accounts.html) is installed by default as part of the data set included in the localization module. The accounts are mapped automatically in their corresponding taxes, and the default account payable and account receivable fields.

Nota

The chart of accounts for Brazil is based on the SPED CoA, which gives a baseline of the accounts needed in Brazil.

You can add or delete accounts according to the company’s needs.

#### Registri¶

In Brazil, a _series_ number is linked to a sequence number range for electronic invoices. The series number can be configured in Odoo on a sales journal from the Series field. If more than one series is needed, then a new sales journal will need to be created and a new series number assigned to it for each series needed.

The Use Documents field needs to be selected. When issuing electronic and non-electronic invoices, the Type field selects the document type used when creating the invoice. The Type field will only be displayed if the Use Documents field is selected on the journal.

Nota

When creating the journal, ensure the field Dedicated Credit Note Sequence is unchecked, as in Brazil, sequences between invoices, credit notes, and debit notes are shared per series number, which means per journal.

#### Imposte¶

Taxes are automatically created when installing the Brazilian localization. Taxes are already configured, and some of them are used by Avalara when computing taxes on the sales order or invoice.

Taxes can be edited, or more taxes can be added. For example, some taxes used for services need to be manually added and configured, as the rate may differ depending on the city where you are offering the service.

Importante

If you decide to do service taxes manually, you won’t be able to issue an NFS-e. To electronically send an NFS-e, you need to compute taxes using Avalara.

Avvertimento

Do not delete taxes, as they are used for the AvaTax tax computation. If deleted, Odoo creates them again when used in an SO or invoice and computing taxes with AvaTax, but the account used to register the tax needs to be re-configured in the tax’s Definition tab, under the Distribution for invoices and Distribution for refunds sections.

Vedi anche

[Taxes functional documentation](../accounting/taxes.html)

#### Prodotti¶

To use the AvaTax integration on sale orders and invoices, first specify the following information on the product depending on its intended use:

##### E-Invoice for goods (NF-e)¶

  * CEST Code: Code for products subject to ICMS tax substitution

  * Mercosul NCM Code: Mercosur Common Nomenclature Product Code

  * Source of Origin: Indicates the origin of the product, which can be foreign or domestic, among other possible options depending on the specific use case

  * SPED Fiscal Product Type: Fiscal product type according to SPED list table

  * Purpose of Use: Specify the intended purpose of use for this product




Nota

Odoo automatically creates three products to be used for transportation costs associated with sales. These are named `Freight`, `Insurance`, and `Other Costs`. They are already configured, if more need to be created, duplicate and use the same configuration (configuration needed: Product Type `Service`, Transportation Cost Type `Insurance`, `Freight`, or `Other Costs`).

##### E-Invoice for services (NFS-e)¶

  * Mercosul NCM Code: Mercosur Common Nomenclature Product Code

  * Purpose of Use: Specify the intended purpose of use for this product

  * Service Code Origin: City Service Code where the provider is registered

  * Service Codes: City Service Code where the service will be provided, if no code is added, the Origin City Code will be used

  * Labor Assignment: Defines if your services includes labor




#### Contatti¶

Before using the integration, specify the following information on the contact:

  1. General information about the contact:

     * Select the Company option for a contact with a tax ID (CNPJ), or check Individual for a contact with a CPF.

     * Nome

     * Address: add City, State, Zip Code, Country

       * In the Street field, enter the street, number, and any extra address information.

       * In the Street 2 field, enter the neighborhood.

     * Identification Number: CNPJ or CPF

     * Tax ID: associated with the identification type

     * IE: state tax identification number

     * IM: municipal tax identification number

     * SUFRAMA code: SUFRAMA registration number

     * Phone

     * E-mail

Nota

The CPF, IE, IM, and SUFRAMA code fields are are hidden until the Country is set to `Brazil`.

  2. Fiscal information about the contact under the Sales & Purchase tab:

     * Fiscal Position: add the AvaTax fiscal position to automatically compute taxes on sale orders and invoices automatically

     * Tax Regime: federal tax regime

     * ICMS Taxpayer Type: taxpayer type determines if the contact is within the ICMS regime, Exempt status, or Non-taxpayer

     * Main Activity Sector: list of main activity sectors of the contact

  3. Configure the following extra Fiscal Information if you are going to issue NFS-e:

     * Add the Fiscal Position for AvaTax Brazil

     * COFINS Details: Taxable, Not Taxable, Taxable with rate 0%, Exempt, Suspended

     * PIS Details: Taxable, Not Taxable, Taxable with rate 0%, Exempt, Suspended

     * CSLL Taxable: If the company is subject to CSLL or not




#### Fiscal positions¶

To compute taxes and send electronic invoices on sale orders and invoices, both the Detect Automatically and the Use AvaTax API options need to be enabled in the Fiscal Position.

The Fiscal Position can be configured on the contact or selected when creating a sales order or an invoice.

## Workflow¶

This section provides an overview of the actions that trigger [API calls](https://en.wikipedia.org/wiki/API) for tax computation, along with instructions on how to send electronic invoices for goods (NF-e) and services (NFS-e) for government validation.

Avvertimento

Please note that each API call incurs a cost. Be mindful of the actions that trigger these calls to manage costs effectively.

### Calcolare le imposte¶

#### Tax calculations on quotations and sales orders¶

Trigger an API call to calculate taxes on a quotation or sales order automatically with AvaTax in any of the following ways:

  * **Quotation confirmation**
    

Confirm a quotation into a sales order.

  * **Manual trigger**
    

Click on Compute Taxes Using AvaTax.

  * **Preview**
    

Click on the Preview button.

  * **Email a quotation / sales order**
    

Send a quotation or sales order to a customer via email.

  * **Online quotation access**
    

When a customer accesses the quotation online (via the portal view), the API call is triggered.




#### Tax calculations on invoices¶

Trigger an API call to calculate taxes on a customer invoice automatically with AvaTax in any of the following ways:

  * **Manual trigger**
    

Click on Compute Taxes Using AvaTax.

  * **Preview**
    

Click on the Preview button.

  * **Online invoice access**
    

When a customer accesses the invoice online (via the portal view), the API call is triggered.




Nota

The Fiscal Position must be set to `Automatic Tax Mapping (Avalara Brazil)` for any of these actions to compute taxes automatically.

Vedi anche

[Fiscal positions (tax and account mapping)](../accounting/taxes/fiscal_positions.html)

### Electronic documents¶

#### Fatture cliente¶

To process an electronic invoice for goods (NF-e) or services (NFS-e), the invoice needs to be confirmed and taxes need to be computed by Avalara. Once that step is done, click on the Send & Print button in the upper left corner. In the pop-up that appears, click on Process e-invoice and any of the other options - Download or Email. Finally, click on Send & Print to process the invoice with the government.

Before sending the electronic invoice for goods (NF-e) or services (NFS-e), some fields need to be filled out on the invoice:

  * Customer, with all the customer information

  * Payment Method: Brazil: how the invoice is planned to be paid

  * Fiscal Position set as the Automatic Tax Mapping (Avalara Brazil)

  * Document Type set as (55) Electronic Invoice (NF-e) or (SE) Electronic Service Invoice (NFS-e)




There are some other optional fields that depend on the nature of the transaction. These fields are not required, so no errors will appear from the government if these optional fields are not populated for most cases:

  * Freight Model determines how the goods are planned to be transported - domestic

  * Transporter Brazil determines who is doing the transportation




Nota

All of the fields available on the invoice used to issue an electronic invoice are also available on the sales order, if needed. When creating the first invoice, the field Document Number is displayed, allocated as the first number to be used sequentially for subsequent invoices.

#### Credit notes¶

If a sales return needs to be registered, then a credit note can be created in Odoo to be sent to the government for validation.

Nota

Credit notes are only available for electronic invoices for goods (NF-e).

Vedi anche

[Issue a credit note](../accounting/customer_invoices/credit_notes.html#accounting-credit-notes-issue-credit-note)

#### Note di debito¶

If additional information needs to be included, or values need to be corrected that were not accurately provided in the original invoice, a debit note can be issued.

Nota

Debit notes are only available for electronic invoices for goods (NF-e).

Only the products included in the original invoice can be part of the debit note. While changes can be made to the product’s unit price or quantity, products **cannot** be added to the debit note. The purpose of this document is only to declare the amount that you want to add to the original invoice for the same or fewer products.

Vedi anche

[Issue a debit note](../accounting/customer_invoices/credit_notes.html#accounting-credit-notes-issue-debit-note)

#### Invoice cancellation¶

It is possible to cancel an electronic invoice that was validated by the government.

Nota

Check whether the electronic invoice is still within the cancellation deadline, which may vary according to the legislation of each state.

##### E-invoices for goods (NF-e)¶

Cancel an e-invoice for goods (NF-e) in Odoo by clicking Request Cancel and adding a cancellation Reason on the pop-up that appears. If you want to send this cancellation reason to the customer via email, activate the E-mail checkbox.

Nota

This is an electronic cancellation, which means that Odoo will send a request to the government to cancel the NF-e, and it will then consume one IAP credit, as an API call occurs.

##### E-invoices for services (NFS-e)¶

Cancel an e-invoice for services (NFS-e) in Odoo by clicking Request Cancel. In this case, there is no electronic cancellation process, as not every city has this service available. The user needs to manually cancel this NFS-e on the city portal. Once that step is completed, they can request the cancellation in Odoo, which will cancel the invoice.

#### Correction letter¶

A correction letter can be created and linked to an electronic invoice for goods (NF-e) that was validated by the government.

This can be done in Odoo by clicking Correction Letter and adding a correction Reason on the pop-up that appears. To send this correction reason to a customer via email, activate the E-mail checkbox.

Nota

Correction letters are only available for electronic invoices for goods (NF-e).

#### Invalidate invoice number range¶

A range of sequences that are assigned to sales journals can be invalidated with the government if they are not currently used, **and** will not be used in the future. To do so, navigate to the journal, and click the ⚙️ (gear) icon ‣ Invalidate Number Range (BR). On the Invalidate Number Range (BR) wizard, add the Initial Number and End Number of the range that should be cancelled, and enter an invalidation Reason.

Nota

Invalidate invoice number range documents are only available for electronic invoices for goods (NF-e).

Nota

The log of the cancelled numbers along with the XML file are recorded in the chatter of the journal.

### Fatture fornitore¶

On the vendor bills side, when receiving an invoice from a supplier, you can encode the bill in Odoo by adding all the commercial information together with the same Brazilian specific information that is recorded on the customer invoices.

These Brazilian specific fields are:

  * Payment Method: Brazil: how the invoice is planned to be paid

  * Document Type: used by your vendor

  * Document Number: the invoice number from your supplier

  * Freight Model: **NF-e specific** how goods are planned to be transported - domestic

  * Transporter Brazil: **NF-e specific** who is doing the transportation.




[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/finance/fiscal_localizations/brazil.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](canada.html "Canada") |
  * [precedente](belgium.html "Belgio") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Brasile


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-app-purchase
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
  *[API]: Application programming interface
  *[IVA]: imposta sul valore aggiunto
  *[MRR]: Monthly Recurring Revenue
  *[ARR]: Annual Recurring Revenue
  *[USB]: Universal Serial Bus
  *[IoT]: Internet of Things
  *[OS]: Operating System
  *[SO]: Sales order
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
  *[OTP]: One-time Password
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
  *[PAC]: Proveedor Autorizado de Certificación / Authorized Certification Provider
  *[PUE]: Pago en una Sola Exhibición/Payment in a Single Exhibition
  *[PPD]: Pago en Parcialidades o Diferido/Payment in Installements or Deferred
  *[CFDI]: Comprobante Fiscal Digital por Internet
  *[OSCU]: Online Sales Control Unit
  *[BOM]: Bill of Materials
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
  *[SLSP]: Summary List of Sales and Purchases
  *[QAP]: Quarterly Alphalist of Payees
  *[SAWT]: Summary Alphalist of Withholding Tax
  *[PCHC]: Philippine Clearing House Corporation
  *[GSTIN]: Goods and Services Tax Identification Number
  *[TDS]: tax deducted at source
  *[TCS]: tax collected at source