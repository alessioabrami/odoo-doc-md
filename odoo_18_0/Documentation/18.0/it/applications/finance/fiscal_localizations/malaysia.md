# Malesia — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](mexico.html "Messico") |
  * [precedente](luxembourg.html "Lussemburgo") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Malesia



# Malesia¶

## Configurazione¶

### Modules installation¶

[Install](../../general/apps_modules.html#general-install) the following modules to get all the features of the Malaysian localization:

Nome | Nome tecnico | Descrizione  
---|---|---  
Malaysia - Accounting | `l10n_my` | This module includes the default [fiscal localization package](../fiscal_localizations.html#fiscal-localizations-packages).  
Malaysia - Accounting Reports | `l10n_my_reports` | This module includes the accounting reports for Malaysia.  
Malaysia - UBL PINT | `l10n_my_ubl_pint` | This module includes the features required to export invoices in PINT format.  
Malaysia - E-invoicing | `l10n_my_edi` | This module includes the features required for integration with MyInvois under IRBM.  
  
### Informazioni aziendali¶

To configure your company information, go to the Contacts app, search for your company, and select it. Then configure the following fields:

  * Nome

  * Address, including the City, State, Zip Code, and Country.

>     * In the Street field, enter the street name, number, and any additional address information.
> 
>     * In the Street 2 field, enter the neighborhood.

  * Tax ID: Tax identification number

  * SST: Malaysian Sales and Service Tax Number, if applicable

  * TTx: Malaysian Tourism Tax Number, if applicable

  * Phone




## E-invoicing integration with MyInvois¶

The MyInvois Portal is a platform provided by the IRBM that facilitates the implementation of e-invoices for Malaysian taxpayers. Odoo supports integration with MyInvois to submit the invoices generated in Odoo.

Nota

The Malaysia - E-invoicing module must be installed to submit invoices to MyInvois.

### Set-up¶

#### MyInvois registration¶

To send electronic invoices to MyInvois, you first need to register and log in to the MyInvois portal to grant Odoo the **right to invoice** as an intermediary for your company.

Nota

If this is the first time you log into the MyInvois portal, click User Manual on [MyTax](https://mytax.hasil.gov.my/) to learn more about the registration process. Both the **pre-production** (testing environment to try the functions before using the actual (production) environment) and **production** (actual environment to submit e-invoices with accurate information) environments are supported.

  1. Log into [MyTax](https://mytax.hasil.gov.my/). Choose the ID Type and the corresponding identification number used to register for the digital certificate.

  2. From the dashboard, click the __(angle-down) icon in the top-right corner and select View Taxpayer Profile.

  3. In the Representatives section, click Add Intermediary in the top-right corner.

  4. Add `ODOO S.A.` as an intermediary using the following information:

     * TIN: `C57800417080`

     * BRN: `BE0477472701`

     * Name:

       * Production: `ODOO S.A.`

       * Pre-production: `OXXX_XXXXO S.A.`

  5. Grant the following permissions by clicking the __(toggle-on) icon:

     * Representation From

     * Document - Submit

     * Document - Cancel

     * Document - Request Rejection

Nota

     * Access can be revoked in the future if needed.

     * Odoo, as an intermediary, does not store invoices sent on behalf of the client on the proxy server.

  6. Click Save. The status for `ODOO S.A.` is then Active.




#### Configuration in Odoo¶

##### Fatturazione elettronica¶

Go to Accounting ‣ Configuration ‣ Settings. In the Malaysian Electronic Invoicing section, choose the relevant MyInvois mode based on the environment you used to register on MyInvois.

Make sure to allow Odoo to process e-invoices by checking the box, then click Register.

Nota

To change the TIN reference, click Unregister, change the company’s information and make sure the number registered on MyInvois matches, then Register again.

##### Azienda¶

Open the Settings app, and in the Companies section, click Update Info. Then, in the E-invoicing section, fill in the following fields:

>   * Identification: The ID Type and associated Identification number used to register for the digital certificate.
> 
>   * Ind. Classification: The 5-digit numeric code that represents the nature and activity of the business.
> 
> 


##### Contatti¶

Access the contact’s form and fill in the following fields:

>   * Country
> 
>   * State
> 
>   * Phone
> 
>   * Tax ID
> 
>   * Identification: the ID Type and the corresponding Identification number of the contact registered on MyTax.
> 
> 


##### Prodotti¶

All products to be included in e-invoices require a Malaysian classification code. To add it, access the Product form and in the General Information tab, fill in the Malaysian classification code field.

### Flusso di lavoro¶

#### Send invoices to MyInvois¶

Invoices can be sent to MyInvois once they have been confirmed. To do so, follow the [invoice sending](../accounting/customer_invoices.html#accounting-invoice-sending) steps, and in the Send window, enable the Send to MyInvois option and click Print & Send.

##### MyInvois status¶

In the MyInvois tab of the invoice, the MyInvois State is updated to Valid when the submission to MyInvois is successful. The Submission UID, MyInvois and Validation Time are also updated. The same information is available on MyInvois.

Nota

If no information is received from the MyInvois portal, the MyInvois State is In Progress. In this case, Odoo automatically checks and updates the status.

#### Invoice cancellation¶

Sent invoices can be canceled within 72 hours from Validation time. In this case, open the invoice and click Request Cancel. In the Cancel document window, include the cancellation Reason, then click Update Invoice. The MyInvois State is updated to cancelled.

## Employment Hero payroll¶

If your business is already up and running with [Employment Hero](employment_hero.html), you can use our connector as an alternative payroll solution.

Importante

To [configure the Employment Hero API](employment_hero.html#employment-hero-configuration) for **Malaysia** , use the following value as Payroll URL: `https://apimy.yourpayroll.io/`.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/finance/fiscal_localizations/malaysia.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](mexico.html "Messico") |
  * [precedente](luxembourg.html "Lussemburgo") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Malesia


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