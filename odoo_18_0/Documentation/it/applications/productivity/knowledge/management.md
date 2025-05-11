# Article management — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](properties.html "Proprietà") |
  * [precedente](articles_editing.html "Article creation and editing") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Produttività](../../productivity.html) »
  * [Knowledge](../knowledge.html) »
  * Article management



# Article management¶

Knowledge allows for managing articles, which consists of structuring, sharing, removing, and retrieving them.

## Gestione di base¶

Click the __( ellipsis) icon and select one of the following actions for basic article management:

  * Move To: Select the article to move under a category or another article, then click Move Article.

  * Lock Content: Lock the article to stop edits. Click Unlock to edit again.

  * Create a Copy: Copy the article under the Private section.

  * Export: Open the browser’s print function.

  * Send to Trash: Move the article to the trash.




Nota

The following actions only apply to nested articles and [article items](articles_editing.html#knowledge-articles-editing-commands):

  * Convert into Article Item: Convert the nested article into an article item.

  * Convert into Article: Convert the article item into a nested article.




Suggerimento

  * Move an article directly from the sidebar tree by dragging and dropping it under another article or category.

  * Press `CTRL` / `CMD` \+ `K` to open the command palette, then type `?` to search for visible articles or `$` for hidden articles. Alternatively, hover over the Workspace category and click the __( eye) icon to find hidden articles.




## Structuring¶

The article structure follows a hierarchy with parent and nested articles organized within the following categories:

  * Favorites displays all articles marked as favorites.

  * Workspace displays articles accessible to all internal users.

  * Shared displays articles shared with specific users.

  * Private displays personal articles.




Nota

  * To mark an article as a favorite and display the Favorites category, click the __( star) icon in the top-right menu.

  * Nested articles inherit the access rights of their parent article.




## Sharing¶

Sharing an article involves configuring access rights, inviting users, providing online access, and determining its visibility in the sidebar tree.

Articles listed under a category in the sidebar tree are visible. Articles that certain users must search for through the command palette due to restricted access rights are hidden.

### Configure access rights¶

Click Share in the top-right menu to configure access rights.

#### Default access rights¶

Setting | Usa  
---|---  
Can edit | Allow all internal users to edit the article.  
Can read | Allow all internal users to read the article only.  
No access | Prevent all users from accessing the article in the sidebar tree or searching in the command palette.  
  
#### Visibilità¶

Setting | Usa  
---|---  
Everyone | The article is visible in the sidebar tree to all internal users.  
Members | The article is only visible in the sidebar tree to invited users, while other users can find it using the hidden article search by pressing `CTRL` / `CMD` \+ `K` and typing `$`.  
  
Nota

  * The Default Access Rights apply to all internal users except invited users; specific access rights override default access rights.

  * Selecting `Can edit` or `Can read` in the Default Access Rights moves the article to the Workspace category, while selecting `No access` moves it to the Private category if it is not shared with anyone.

  * The Visibility setting only applies to Workspace articles.




### Invite specific users¶

To grant specific internal or portal users access to a private article or to share a Workspace article with a portal user, follow these steps:

  1. Click Share in the top-right menu.

  2. Click Invite.

  3. Select the preferred Permission and add users in the Recipients field.

  4. Click Invite.




### Generate article URL¶

Click Share and activate the Share to web toggle to generate a URL. Click the __( copy) icon to copy the article’s URL.

Nota

  * If an article contains [inserted views](articles_editing.html#knowledge-articles-editing-views), users with the URL do not see them unless they can access the inserted content.

  * Having the Website app is necessary to share an article’s URL.




## Rimozione¶

Removing an article involves deleting or archiving it.

### Delete an article¶

Select an article in the sidebar tree and click the __( ellipsis) icon, then Send to Trash. The article is moved to the trash for 30 days before being permanently deleted.

To delete an article directly, click Search in the top-left menu, select an article, and click Actions ‣ Delete ‣ Delete to remove the article permanently.

Nota

To restore a trashed article, click Open the Trash at the bottom of the sidebar tree, select an article, and click Restore. Alternatively, click Search in the top-left menu. In the search bar, click Filters ‣ Trashed. Click the article, then Restore.

### Archive an article¶

Click Search, select an article, and click Actions ‣ Archive ‣ Archive.

Nota

To restore an archived article, click Search. In the search bar, click Filters ‣ Archived. Select the article and go to Actions ‣ Unarchive.

## Retrieval¶

Retrieving Knowledge articles consists of accessing them from various Odoo apps or restoring previous versions.

### Access articles from various apps¶

Knowledge articles are accessible from the [form view](../../studio/views.html#studio-views-general-form) of various apps. Click the __(Knowledge) icon in the top right corner to open the command palette, then choose one of the following search methods:

  * Search for an article: start typing the text to execute a semantic search that identifies relevant article information.

  * Advanced Search: after typing the text in the search bar, click Advanced Search to perform a parametric search with options to filter, group, or save articles.




### Version history¶

To retrieve a previous version of an article, select it in the sidebar tree and click the __( history) icon in the top-right menu to open the version history. Select a version and click Restore history.

Nota

In the version history, the Content tab shows the selected version, while the Comparison tab displays the differences between the article’s previous and current versions.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/productivity/knowledge/management.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](properties.html "Proprietà") |
  * [precedente](articles_editing.html "Article creation and editing") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Produttività](../../productivity.html) »
  * [Knowledge](../knowledge.html) »
  * Article management


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