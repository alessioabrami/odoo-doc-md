# Romania — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](saudi_arabia.html "Arabia Saudita") |
  * [precedente](philippines.html "Filippine") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Romania



# Romania¶

## Configurazione¶

[Install](../../general/apps_modules.html#general-install) the following modules to get all the features of the Romanian localization.

Nome | Nome tecnico | Descrizione  
---|---|---  
Romania - Accounting | `l10n_ro` | Default [fiscal localization package](../fiscal_localizations.html#fiscal-localizations-packages).  
Romanian SAF-T Export | `l10n_ro_saft` | Module to generate the **D.406 declaration** in the SAF-T format.  
  
Vedi anche

[Documentation on e-invoicing’s legality and compliance in Romania](../accounting/customer_invoices/electronic_invoicing/romania.html)

## D.406 declaration¶

Starting January 1, 2023, companies registered for tax purposes in Romania must report their accounting data to the Romanian Tax Agency monthly or quarterly in the D.406 declaration.

Odoo provides all you need to export the data of this declaration in the SAF-T XML format, which you can validate and sign using the software provided by the Romanian Tax Agency.

Nota

Currently, Odoo only supports the generation of the monthly/quarterly D.406 declaration (containing journal entries, invoices, vendor bills, and payments). The yearly declaration (including assets) and the on-demand declaration (including inventory) are not yet supported.

### Configurazione¶

#### Azienda¶

  * Under Settings –> General Settings, in the **Companies** section, click Update Info and fill in the company’s Country, City, and Telephone Number.

  * Provide your company’s CUI number or CIF number (for foreign companies) in the Company ID field, without the `RO` prefix (e.g., `18547290`).

  * If your company is **registered** for VAT in Romania, fill in the Tax ID field number, including the `RO` prefix (e.g., `RO18547290`). If the company is **not** registered for VAT in Romania, you **must not** fill in the Tax ID field.

  * Open the **Contacts** app and search for your company. Open your company’s profile, and in the Accounting tab, click Add a line and add your **bank account number** if not informed already. Make sure the profile is set as Company above the **name**.

    * You must have at least one **contact person** linked to your company in the **Contacts** app. If no **contact person** is linked, create a new one by clicking New, set it as Individual, and select your company in the Company name field.




#### Piano dei conti¶

To generate a file receivable by the Romanian Tax Agency, the chart of accounts must not deviate from an official chart of accounts, such as:

  * the chart of accounts for commercial companies (_PlanConturiBalSocCom_), which is installed by default when creating a company with the Romanian localization or;

  * the chart of accounts for companies following [IFRS](https://www.ifrs.org/) (_PlanConturiIFRS_).




Under Settings –> Accounting, in the **Romanian localization** section, set the Tax Accounting Basis to reflect the accounting regulations and Chart of Accounts used by the company.

Vedi anche

[Piano dei conti](../accounting/get_started/chart_of_accounts.html)

#### Customer and supplier¶

Fill in the Country, City, and Zip Code of each partner that appears in your invoices, vendor bills, or payments through the **Contacts** app.

For partners that are companies, you must fill in the VAT number (including the country prefix) in the Tax ID field. If the partner is a company based in Romania, you may instead fill in the CUI number (without the “RO” prefix) in the Company ID field.

#### Imposta¶

You must indicate the Romanian SAF-T Tax Type (3-digit number) and Romanian SAF-T Tax Code (6-digit number) on each of the taxes you use. This is already done for the taxes that exist by default in Odoo. To do so, go to Accounting ‣ Configuration ‣ Taxes, select the tax you wish to modify, click the Advanced Options tab, and fill in the **tax type** and **tax code** fields.

Nota

The **tax type** and **tax code** are codes defined by the Romanian Tax Agency for the **D.406 declaration**. These can be found in the Excel spreadsheet published as guidance for completing the declaration, which you can find on the [website of the Romanian Tax Agency](https://www.anaf.ro/anaf/internet/ANAF/despre_anaf/strategii_anaf/proiecte_digitalizare/saf_t/).

Vedi anche

[Imposte](../accounting/taxes.html)

#### Prodotto¶

For some types of goods transactions, the Intrastat Code (Cod NC) must be configured on the product, as it is required by Romanian law:

  * import / export transactions;

  * acquisitions / supplies of food products subjected to reduced VAT rate;

  * intra-community movements subjected to intrastat reporting;

  * acquisitions / supplies subjected to local reversed VAT charge (depending on Cod NC); and

  * transactions with excisable products for which excise duties are determined based on the Cod NC.




If the Intrastat Code is not specified on a non-service product, the default code “0” will be used.

To configure the Intrastat Codes, go to Accounting ‣ Customers ‣ Products, select a product, and in the Accounting tab, set a Commodity Code.

Vedi anche

[Intrastat](../accounting/reporting/intrastat.html)

#### Fattura fornitore¶

You must check the Is self-invoice (RO)? checkbox in the Other Info tab for any vendor bill that is a self-invoice (i.e. a vendor bill that you issued yourself in the absence of an invoice document received from a supplier).

### Generating the declaration¶

#### Exporting your data¶

To export the XML for the D.406 declaration, go to Accounting ‣ Reports ‣ General Ledger and click on SAF-T.

You can then validate and sign the XML file using the Romanian Tax Agency’s validation software, _DUKIntegrator_.

#### Signing the report¶

Download and install the _DUKIntegrator_ validation software found on the [website of the Romanian Tax Agency](https://www.anaf.ro/anaf/internet/ANAF/despre_anaf/strategii_anaf/proiecte_digitalizare/saf_t/).

Once you have generated the XML, open “DUKIntegrator” and select the file you have just generated.

Click on Validare + creare PDF to create an **unsigned** PDF containing your report, or Validare + creare PDF semnat to create a **signed** PDF containing your report.

If the _DUKIntegrator_ validator detects errors or inconsistencies in your data, it generates a file that explains the errors. In this case, you need to correct those inconsistencies in your data before you can submit the report to the Romanian Tax Agency.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/finance/fiscal_localizations/romania.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](saudi_arabia.html "Arabia Saudita") |
  * [precedente](philippines.html "Filippine") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Romania


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