# Egitto — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](france.html "Francia") |
  * [precedente](ecuador.html "Ecuador") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Egitto



# Egitto¶

## Installazione¶

[Install](../../general/apps_modules.html#general-install) the following modules to get all the features of the Egyptian localization:

Nome | Nome tecnico | Descrizione  
---|---|---  
Egypt - Accounting | `l10n_eg` | [Pacchetto localizzazione fiscale predefinito](../fiscal_localizations.html#fiscal-localizations-packages)  
Egyptian E-invoice Integration | `l10n_eg_edi_eta` | Egyptian Tax Authority (ETA) e-invoicing integration  
  
## Egyptian e-invoicing¶

Odoo is compliant with the **Egyptian Tax Authority (ETA) e-invoicing** requirements.

Importante

Egyptian e-invoicing is available from Odoo 15.0. If needed, [upgrade](../../../administration/upgrade.html) your database.

Vedi anche

  * [Video: Egypt E-invoicing](https://www.youtube.com/watch?v=NXuBPLR4pVw)

  * [Aggiorna](../../../administration/upgrade.html)




### Register Odoo on your ETA portal¶

You must register your Odoo ERP system on your ETA portal to get your API credentials. You need these codes to configure your Odoo Accounting app.

Access your company profile on the ETA portal by clicking on View Taxpayer Profile.

Next, go to the Representatives section and then click on Register ERP. Fill out the ERP Name (e.g., `Odoo`) and leave the other fields empty.

Once successfully registered, the website displays your API credentials:

  * ID cliente

  * Client Secret 1

  * Client Secret 2




Nota

  * ETA should give you a username and a password to access their online portal.

  * Ask ETA to provide you with preproduction portal access as well.

  * These codes are confidential and should be stored safely.




### Configuration on Odoo¶

To connect your Odoo database to your ETA portal account, go to Accounting ‣ Configuration ‣ Settings ‣ ETA E-Invoicing Settings, and set the ETA Client ID and ETA Secret that you retrieved when you registered Odoo on your ETA portal. Set an invoicing threshold if needed.

Importante

  * **Test on your preproduction portal** before starting to issue real invoices on the production ETA portal.

  * **Credentials** for preproduction and production environments are different. Make sure to update them on Odoo when you move from one environment to another.

  * If not done yet, fill out your company details with your company’s full address, country, and Tax ID.




#### ETA codes¶

E-invoicing works with a set of codes provided by the ETA. You can use the [ETA documentation](https://sdk.preprod.invoicing.eta.gov.eg/codes/) to code your business attributes.

Most of these codes are handled automatically by Odoo, provided that your branches, customers, and products are correctly configured.

  * Company Information:

    * Company Tax ID

    * Branch ID

If you have only one branch, use `0` as the branch code.

    * Activity type Code

  * Altre informazioni:

    * Product Codes

Your company’s products should be coded and matched with their **GS1** or **EGS** codes.

    * Tax Codes

Most of the taxes codes are already configured on Odoo in the ETA Code (Egypt) field. We advise you to make sure these codes match your company’s taxes.




Vedi anche

  * [Egyptian eInvoicing & eReceipt SDK - Code Tables](https://sdk.preprod.invoicing.eta.gov.eg/codes/)

  * [Imposte](../accounting/taxes.html)




#### Filiali¶

Create a contact and a journal for each branch of your company and configure its ETA settings.

To do so, go to Accounting ‣ Configuration ‣ Journals, then click on Create.

Name the journal according to your company’s branch and set the Type as Sales. Next, open the Advanced Settings tab and fill out the Egyptian ETA settings section:

  * In the Branch field, select the branch’s contact or create it.

  * Set the ETA Activity Code.

  * Set the ETA Branch ID (use `0` if you have one branch only).




Importante

The contact selected in the Branch field must be set as a Company (**not** as an Individual), and the Address and Tax ID fields must be filled out.

#### Clienti¶

Make sure your customers” contact forms are correctly filled out so your e-invoices are valid:

  * contact type: Individual: or Company:

  * Country:

  * Tax ID: Tax ID or Company registry for companies. National ID for individuals.




Nota

You can edit your customers” contact forms by going to Accounting ‣ Customers ‣ Customers.

#### Prodotti¶

Make sure your products are correctly configured so your e-invoices are valid:

  * Product Type: storable products, consumables, or services.

  * Unit of Measure: if you also use Odoo Inventory and have enabled [Units of Measure](../../inventory_and_mrp/inventory/product_management/configure/uom.html).

  * Barcode: **GS1** or **EGS** barcode

  * ETA Item code (under the Accounting tab): if the barcode doesn’t match your ETA item code.




Nota

You can edit your products by going to Accounting ‣ Customers ‣ Products.

### USB authentication¶

Each person who needs to electronically sign invoices needs a specific USB key to authenticate and send invoices to the ETA portal through an ERP.

Nota

You can contact the ETA or [Egypt Trust](https://www.egypttrust.com/) to get these USB keys.

#### Install Odoo as a local proxy on your computer¶

An Odoo local server works as a bridge between your computer and your Odoo database hosted online.

Download the Odoo Community installer from the page <https://www.odoo.com/page/download> and start the installation on your computer.

Select Odoo IoT as the type of install.

Nota

This installation of Odoo only works as a server and does not install any Odoo apps on your computer.

Once the installation is complete, the installer displays your **access token** for the Odoo Local Proxy. Copy the token and save it in a safe place for later use.

Vedi anche

  * [Odoo: Download Odoo](https://www.odoo.com/page/download)

  * [On-premise](../../../administration/on_premise.html)




#### Configure the USB key¶

Once the local proxy server is installed on your computer, you can link it with your Odoo database.

  1. Go to Accounting ‣ Configurations ‣ Thumb Drive and click on Create.

  2. Input a Company name, the ETA USB Pin given to you by your USB key provider, and the Access Token provided at the end of the local proxy installation, then click on Save.

  3. Click on Get certificate.




[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/finance/fiscal_localizations/egypt.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](france.html "Francia") |
  * [precedente](ecuador.html "Ecuador") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Egitto


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