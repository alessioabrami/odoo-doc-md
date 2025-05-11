# Pulizia dati — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](whatsapp.html "WhatsApp") |
  * [precedente](discuss/canned_responses.html "Risposte predefinite") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
  * [Produttività](../productivity.html) »
  * Pulizia dati



# Pulizia dati¶

The Odoo **Data Cleaning** app maintains data integrity and consistency with the following features:

  * Deduplicates: merges or removes duplicate entries to ensure data is unique.

  * Recycles: identifies outdated records to either archive or delete them.

  * Formats: standardizes text data by finding and replacing it according to specified needs.




Customizable rules ensure text data stays up-to-date, streamlined, consistently formatted, and aligned with company-specific formatting requirements.

## Install modules¶

The **Data Cleaning** application consists of several modules. [Install](../general/apps_modules.html#general-install) the following to access all available features:

Nome `Technical name` | Descrizione  
---|---  
Data Recycle `data_recycle` | Base module to enable the recycle feature, available on [Odoo Community edition](../../administration.html#install-editions).  
Data Cleaning `data_cleaning` | Enables field cleaning feature to format text data across multiple records, available **only** on [Odoo Enterprise edition](../../administration.html#install-editions).  
Data Cleaning (merge) `data_merge` | Enables the deduplication feature to find similar (or duplicate) records, and merge them, available **only** on [Odoo Enterprise edition](../../administration.html#install-editions).  
  
Additionally, several app-specific modules are available

CRM Deduplication `data_merge_crm` | Enables the deduplication feature on the **CRM** app, and uses the [CRM default merging feature](../sales/crm/pipeline/merge_similar.html).  
---|---  
Helpdesk Merge action `data_merge_helpdesk` | Enables the merge feature for the **Helpdesk** app.  
Project Merge action `data_merge_project` | Enables the merge feature for the **Projects** app.  
UTM Deduplication `data_merge_utm` | Enables the merge feature for the **UTM Tracker** app.  
WMS Accounting Merge `data_merge_stock_account` | Creates a warning in cases of products merging that may affect inventory valuation, if the **Inventory** app is installed.  
  
## Deduplicazione¶

The _Duplicates_ dashboard groups similar records to be merged by matching conditions within the records set by the deduplication rules.

Navigate to this dashboard by going to Data Cleaning app ‣ Deduplication.

The RULE sidebar lists each of the active deduplication rules, and displays the total number of duplicates detected beside each rule.

By default, the All rule is selected. Records are grouped by their rule, with a Similarity rating (out of 100%), with the following columns:

  * Created On: the date and time the original record was created.

  * Name: the name or title of the original record.

  * Field Values: the original record’s values for the fields used to detect duplicates.

  * Used In: lists other models referencing the original record.

  * ID: the original record’s unique ID.

  * Is Master: the duplicates are merged into the _master_ record. There can only be **one** master record in a grouping of similar records.




Select a specific rule in the RULE sidebar to filter the duplicate records.

### Merge duplicate records¶

To merge records, first choose a _master_ record within the grouping of similar records. The master record acts as the base, at which any additional information from similar records are merged into.

Optionally, no master record can be set, leaving Odoo to choose a record at random to merge into.

Next, click the Merge button at the top of the similar records grouping. Then, click Ok to confirm the merge.

Once a record is merged, a message is logged in the chatter of the master record, describing the merge. Certain records, like **Project** tasks, are logged in the chatter with a link to the old record as a convenient reference of the merge.

Suggerimento

Discard groupings by clicking the DISCARD button. Upon doing so, the grouping is hidden from the list and archived.

View discarded groupings by selecting the Discarded filter from the [search bar](../essentials/search.html#search-filters).

### Deduplication rules¶

The _Deduplication Rules_ set the conditions for how records are detected as duplicates.

These rules can be configured for each model in the database, and with varying levels of specificity. To get started, navigate to Data Cleaning app ‣ Configuration ‣ Deduplication.

Suggerimento

The deduplication rules run once every day, by default, as part of a scheduled action cron (_Data Merge: Find Duplicate Records_). However, each rule can be ran manually anytime.

#### Modify a deduplication rule¶

Select a default rule to edit, or create a new rule by clicking on the New button.

First, choose a Model for this rule to target. Selecting a model updates the rule title to the chosen model.

Optionally, configure a Domain to specify the records eligible for this rule. The number of eligible records is shown in the __ # record(s) link.

Depending on the selected Model, the Duplicate Removal field appears. Choose whether to Archive or Delete merged records.

Next, select a Merge Mode:

  * Manual: requires each duplicate grouping to be manually merged, also enables the Notify Users field.

  * Automatic: automatically merges duplicate groupings, without notifying users, based on the records with a similarity percentage above the threshold set in the Similarity Threshold field.




Enable the Active toggle to start capturing duplicates with this rule as soon as it is saved.

Lastly, create at least one deduplication rule in the Deduplication Rules field, by clicking Add a line, under the Unique ID Field column.

  * Select a field in the model from the Unique ID Field drop-down menu. This field is referenced for similar records.

  * Select a matching condition in the Match If field to apply the deduplication rule, depending on the text in the Unique ID Field:

    * Exact Match: the characters in the text match exactly.

    * Case/Accent Insensitive Match: the characters in the text match, regardless of casing and language-specific accent differences.




Importante

At least one Deduplication Rules must be set for the rule to capture duplicates.

Suggerimento

A few more fields are available for an advanced configuration.

If on a multi-company database, the Cross-Company field is available. When enabled, duplicates across different companies are suggested.

Activate [Modalità sviluppatore (modalità di debug)](../general/developer_mode.html#developer-mode) to display the Suggestion Threshold field. Duplicates with a similarity below the threshold set in this field are **not** suggested.

With the rule’s configuration complete, either close the rule form, or run the rule manually to instantly capture duplicate records.

#### Manually run a deduplication rule¶

To manually run a specific deduplication rule at any time, navigate to Data Cleaning app ‣ Configuration ‣ Deduplication, and select the rule to run.

Then, on the rule form, select the Deduplicate button on the top-left. Upon doing so, the __ Duplicates smart button displays the number of duplicates captured.

Click on the __ Duplicates smart button to manage these records.

## Recycle records¶

Use the _recycle records_ feature to rid the database of old and outdated records.

The _Field Recycle Records_ dashboard displays records that can be archived or deleted, by matching conditions within the records set by the recycle record’s rules.

Navigate to this dashboard by going to Data Cleaning app ‣ Recycle Records.

The RECYCLE RULES sidebar lists each of the active recycle record rules.

By default, the All option is selected. Records are displayed with the following columns:

  * Record ID: the ID of the original record.

  * Record Name: the name or title of the original record.




Select a specific rule in the RECYCLE RULES sidebar to filter the records.

To recycle records, click the __ Validate button on the row of the record.

Upon doing so, the record is recycled, depending on how the rule is configured, to be either archived or deleted from the database.

Suggerimento

Discard groupings by clicking the __ Discard button. Upon doing so, the record is hidden from the list, and is not detected by the recycle rule again in the future.

View discarded records by selecting the Discarded filter from the [search bar](../essentials/search.html#search-filters) drop-down menu.

### Recycle record rules¶

The _Recycle Records Rules_ set the conditions for how records are recycled.

These rules can be configured for each model in the database, and with varying levels of specificity. To get started, navigate to Data Cleaning app ‣ Configuration ‣ Recycle Records.

Suggerimento

Recycle rules run once a day, by default, as part of a scheduled action cron (_Data Recycle: Clean Records_). However, each rule can be run manually anytime.

By default, no recycle record rules exist. Click the New button to create a new rule.

On the recycle record rule form, first choose a Model for this rule to target. Selecting a model updates the rule title to the chosen model.

Optionally, configure a Filter to specify the records eligible for this rule. The number of eligible records is shown in the __ # record(s) link.

Next, configure the field and time range for how the rule detects the records to recycle:

  * Time Field: select a field from the model to base the time (Delta).

  * Delta: type the length of time, which must be a whole number (e.g. `7`).

  * Delta Unit: select the unit of time (Days, Weeks, Months, or Years).




Then, select a Recycle Mode:

  * Manual: requires each detected record to be manually recycled, and enables the Notify Users field.

  * Automatic: automatically merges recycled groupings, without notifying users.




Lastly, select a Recycle Action to either Archive or Delete records. If Delete is selected, choose whether or not to Include Archived records in the rule.

With the rule’s configuration complete, either close the rule form, or run the rule manually to instantly capture records to recycle.

Example

A recycle rule can be configured to delete archived leads and opportunities that were last updated a year ago, and with a specific lost reason, by using the following configuration:

  * Model: Lead/Opportunity

  * Filter:

    * `Active` `is` `not set`

    * `Lost Reason` `is in` `Too expensive`

  * Time Field: Last Updated on (Lead/Opportunity)

  * Delta: `1`

  * Delta Unit: Years

  * Recycle Mode: Automatic

  * Recycle Action: Delete

  * Include Archived: __




#### Manually run a recycle rule¶

To manually run a specific recycle rule at any time, navigate to Data Cleaning app ‣ Configuration ‣ Recycle Records, and select the rule to run.

Then, on the rule form, click the Run Now button on the top-left. Upon doing so, the __ Records smart button displays the number of records captured.

Click the __ Records smart button to manage these records.

## Field cleaning¶

Use the field cleaning feature to maintain consistent formatting of names, phone numbers, IDs and other fields throughout a database.

The _Field Cleaning Records_ dashboard displays formatting changes to data in fields of a record, to follow a convention set by the field cleaning rules.

Navigate to this dashboard by going to Data Cleaning app ‣ Field Cleaning.

The CLEANING RULES sidebar lists each of the active cleaning rules.

By default, the All rule is selected. Records are listed with the following columns:

  * Record ID: the ID of the original record.

  * Record Name: the name or title of the original record.

  * Field: the original record’s field that contains the value to format.

  * Current: the current value in the field of the original record.

  * Suggested: the suggested formatted value in the field of the original record.




To clean and format records, click the __ Validate button on the row of the record.

Upon doing so, the record is formatted and/or cleaned.

Suggerimento

Discard records by clicking the __ Discard button. Upon doing so, the record is hidden from the list and will not be detected by the field cleaning rule again in the future.

View discarded records by selecting the Discarded filter from the [search bar](../essentials/search.html#search-filters).

### Field cleaning rules¶

The _Field Cleaning Rules_ set the conditions for fields to be cleaned and/or formatted.

These rules can be configured for each model in the database, and with varying levels of specificity. To get started, navigate to Data Cleaning app ‣ Configuration ‣ Field Cleaning.

Suggerimento

The field cleaning rules run once every day, by default, as part of a scheduled action cron (_Data Cleaning: Clean Records_). However, each rule can be ran manually anytime.

By default, a Contact rule exists to format and clean up the **Contacts** app records. Select the Contact record to make edits, or select the New button to create a new rule.

On the field cleaning rule form, first choose a Model for this rule to target. Selecting a model updates the rule title to the chosen model.

Next, configure at least one rule by clicking Add a line in the Rules section.

Upon doing so, a Create Rules popover window appears with the following fields to configure:

  * Select a Field To Clean from the model to assign to an action.

  * Choose one of the following Action options:

    * Trim Spaces reveals the Trim field to select the All Spaces or Superfluous Spaces option. Leading, trailing, and successive spaces are considered superfluous.

Example

The contact name `Dr. John Doe` can be formatted with the following Trim options:

      * All Spaces: `DR.JohnDoe`

      * Superfluous Spaces: `DR. John Doe`

    * Set Type Case reveals the Case field to select either First Letters to Uppercase, All Uppercase, or All Lowercase.

Example

The lead/opportunity title `lumber inc, Lorraine douglas` can be formatted with the following Case options:

      * First Letters to Uppercase: `Lumber Inc, Lorraine Douglas`

      * All Uppercase: `LUMBER INC, LORRAINE DOUGLAS`

      * All Lowercase: `lumber inc, lorraine douglas`

    * Format Phone converts the phone number to an international country format.

Example

      * Belgium: `061928374` __` +32 61 92 83 74`

      * United States: `800 555-0101` __` +1 800-555-0101`

    * Scrap HTML converts HTML to plain text.

Example

HTML text¶
          
          <h1>John Doe</h1>
          <p>Lorem ipsum dolor sit <a href="https://example.com">amet</a>.</p>
          

Testo normale¶
          
          **John Doe** Lorem ipsum dolor sit amet [1] .[1] https://example.com
          

Once a field and action are selected, click Save to close the Create Rules popover window.




Then, select a Cleaning Mode:

  * Manual: requires each detected field to be manually cleaned and enables the Notify Users field.

  * Automatic: automatically cleans fields without notifying users.




With the rule’s configuration complete, either close the rule form, or run the rule manually to instantly capture fields to clean.

#### Manually run a field cleaning rule¶

To manually run a specific field cleaning rule at any time, navigate to Data Cleaning app ‣ Configuration ‣ Field Cleaning, and select the rule to run.

Then, on the rule form, select the Clean button on the top-left. Upon doing so, the __ Records smart button displays the number of records captured.

Click on the __ Records smart button to manage these records.

## Merge action manager¶

The _Merge Action Manager_ enables or disables the _Merge_ action available in the _Actions_ menu for models in the database.

Enable [Modalità sviluppatore (modalità di debug)](../general/developer_mode.html#developer-mode) and navigate to Data Cleaning app ‣ Configuration ‣ Merge Action Manager.

Models are listed with the following columns:

  * Model: technical name of the model.

  * Model Description: display name of the model.

  * Type: whether the model is of the _Base Object_ or _Custom Object_ type.

  * Transient Model: the model handles temporary data that does not need to be stored long-term in the database.

  * Can Be Merged: enables the _Merge_ action for the model.




To view which models are enabled by default, use the [search bar](../essentials/search.html#search-filters) to filter models that Can Be Merged.

Vedi anche

[Unisci contatti](../essentials/contacts/merge.html)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/productivity/data_cleaning.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](whatsapp.html "WhatsApp") |
  * [precedente](discuss/canned_responses.html "Risposte predefinite") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
  * [Produttività](../productivity.html) »
  * Pulizia dati


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-app purchases
  *[RTL]: right-to-left
  *[RST]: reStructuredText
  *[GUI]: graphical user interface
  *[TOC]: Table Of Contents
  *[SEO]: Search Engine Optimization
  *[EDI]: Electronic Data Exchange
  *[SDD]: SEPA Direct Debit
  *[PLE]: Programa de Libros Electrónico
  *[BoM]: Bill of Materials
  *[MO]: Manufacturing Order
  *[MPS]: Master Production Schedule
  *[OEE]: overall equipment effectiveness
  *[RFQ]: request for quotation
  *[RfQ]: Request for Quotation
  *[RfQs]: Requests for Quotation
  *[IU]: Interfaccia Utente
  *[UoM]: Unit of Measure
  *[PoS]: Point of Sale
  *[FBM]: Fulfilled by Merchant
  *[FBA]: Fulfilled by Amazon
  *[API]: Application Programming Interface
  *[IVA]: imposta sul valore aggiunto
  *[MRR]: Monthly Recurring Revenue
  *[ARR]: Annual Recurring Revenue
  *[USB]: Universal Serial Bus
  *[IoT]: Internet of Things
  *[OS]: Operating System
  *[SO]: sales order
  *[MRP]: Material Requirement Planning
  *[DNS]: Domain name System
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
  *[URL]: Uniform Resource Locators
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
  *[LIFO]: Last In, First Out
  *[SAQ]: Self-Assessment Questionnaire
  *[VAT]: Value-Added Tax Identification
  *[SMP]: Service Metadata Publisher
  *[AVCO]: Average Costing
  *[OdA]: Ordine di acquisto
  *[sportello unico OSS]: One-Stop Shop
  *[IAPs]: in-app purchases
  *[SOs]: Sales Orders
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
  *[CoA]: chart of accounts
  *[SEC]: Securities and Exchange Commission
  *[CFS]: Cash Flow Statement
  *[ACH]: automated clearing house
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
  *[SVLs]: stock move layers
  *[SP]: Scrap Order
  *[DO]: Delivery Order
  *[RFQs]: requests for quotation
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
  *[CSV]: Valori separati da virgola
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
  *[CIS]: Construction Industry Scheme
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
  *[HMRC]: HM Revenue and Customs
  *[SVL]: stock move layer
  *[JIT]: just-in-time
  *[FAQs]: Frequently Asked Questions