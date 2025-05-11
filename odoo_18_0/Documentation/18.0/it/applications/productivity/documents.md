# Documenti — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](sign.html "Firma") |
  * [precedente](../productivity.html "Produttività") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
  * [Produttività](../productivity.html) »
  * Documenti



# Documenti¶

**Odoo Documents** allows you to store, view, and manage files within Odoo.

Folders and documents are organized into sections accessible from the tree on the left. The following sections are available:

  * All: displays all folders and files the user has access to.

  * __ Company: contains folders and files shared across the company. Access is determined by the access rights defined for the folder and file.

  * __ My Drive: the user’s personal workspace for organizing and accessing files and folders they own or have uploaded.

  * __ Shared with me: includes files that have been shared with the user but are not part of any parent folder they have access to.

  * __ Recent: shows recently modified files the user has permission to view or edit.

  * __ Trash: stores deleted files and folders.




Click a section in the tree to view its contents. Select a folder to open it, manage it, and access its files.

Click a file to open it and take available actions. To close the file, press **Esc** or click the __( close) icon. You can also drag and drop a file or folder to move it to another folder or section.

Suggerimento

  * Use the [search bar](../essentials/search.html#search-values) to quickly find specific items.

  * The [chatter](discuss/chatter.html) tracks changes to folders and files and allows communication with internal users and external contacts. Click the __( Info & Tags) button in the upper-right corner next to the view to access it.




Vedi anche

[Sign documentation](sign.html)

## Configurazione¶

### Ritardo eliminazione¶

By default, items moved to the trash remain there for 30 days before being permanently deleted. To adjust this delay, go to Documents ‣ Configuration ‣ Settings and edit the Deletion delay (days) field.

### File centralization¶

Enabling file centralization for a specific app automatically organizes all associated files into dedicated folders. To do so, go to Documents ‣ Configuration ‣ Settings. For example, enabling Human Resources makes HR documents automatically available in the HR folder, while documents related to Payroll are automatically available in the Payroll sub-folder. Select the desired folder from the dropdown list and select the Tags to be added to the relevant files.

Suggerimento

When centralizing accounting files, click Journals to configure specific sub-folders for individual journals.

Nota

  * Changing the folder or tags does not affect existing files; the changes will apply only to newly created ones.

  * If file centralization is enabled for an app, deleting a record in that app moves its attachments to the trash in the Documents app.




## Cartelle¶

You can organize files in folders available in the __ Company or __ My Drive sections.

To create a folder, select the desired section in the tree, click New, and select Folder. In the pop-up, enter the folder’s Name and click Save. To create a sub-folder, select the parent folder first, then follow the same steps.

Nota

Some folders and sub-folders are created automatically based on the file centralization settings.

To manage a folder or sub-folder, select it and click the __( Actions) icon above the tree. The following options are available in the menu:

  * __ Download: Download the folder as a .zip file, including its files and sub-folders.

  * __ Rename: Modify the folder’s name.

  * __ Share: Share the folder or manage its access rights.

  * __ Add shortcut: This option is only available for sub-folders and allows to create a shortcut to a sub-folder.

    * If you have editing permissions, the shortcut is created in the same folder.

    * If you don’t have editing permissions, the shortcut appears in the __ My Drive section.

You can then drag and drop it into the desired folder.

  * __ Add star: Mark a folder as a favorite for quicker access. This setting is user-specific and does not affect other users” workspaces. You can then use the [Starred filter](../essentials/search.html#search-favorites) to navigate to your favorite folders quickly.

  * __ Info & Tags: View the folder’s details and chatter.

  * __ Move to trash: Move the folder and its content to the trash.

  * __ Actions on Select: Define the server actions that are available (as buttons) for the files in the folder. Click an action to add or remove it. Click Add Custom Action to [create a new one](../../developer/reference/backend/actions.html#reference-actions-server).

  * __ Automations: Create [automation rules](../studio/automated_actions.html).




Importante

Setting up custom actions and automation rules may impact your [pricing plan](https://www.odoo.com/pricing).

## File¶

To upload a file, select the desired folder in the tree, click New and select Upload.

Suggerimento

  * On Odoo Online databases, each uploaded file must not exceed 64MB.

  * You can also drag and drop a file from your computer to the desired folder within the Documents app.




### URL links¶

To add a link to a URL (e.g., a video) and make it accessible from a folder, click New and select Link. Enter the URL, add a Name, and select the appropriate Folder.

### Fogli di calcolo¶

To create a spreadsheet, click New and select Spreadsheet.

Vedi anche

[Spreadsheet documentation](spreadsheet.html)

### Managing files¶

Several buttons are available in the top bar when opening a file:

  * the __ Action menu, which includes the options described below

  * Share: to share the file or manage its access rights

  * Download

  * any buttons defined for the folder




The following options are available in the __ Action menu:

  * __ Duplicate: Create a copy of the file.

  * __ Move to Trash: Move the file to the trash.

  * __ Rename

  * __ Info & tags: View the file’s details and chatter.

  * __ Create shortcut: A shortcut is a pointer to a file, allowing access from multiple folders without duplicating the file.

    * If you have editing permissions, the shortcut is created in the same folder.

    * If you don’t have editing permissions, the shortcut appears in the __ My Drive section.

You can then drag and drop it into the desired folder.

  * __ Manage versions: View all versions of the file in upload order, download a specific version, or upload a new one as needed.

  * __ Lock: Protect the file from any modifications.

  * __ Copy Links: Copy the file’s URL for sharing. Access is controlled based on the file’s access rights.

  * __ Split PDF: Split a PDF file.




Suggerimento

You can use folder-specific email aliases to automatically save files sent to the alias into the corresponding folder.

### Splitting and merging PDFs¶

To divide a PDF into individual or groups of pages, open the PDF and click __ Split PDF in the upper-right part of the document preview. Click the __( scissors) icon between pages to remove a split if needed, then click Split to confirm.

To merge PDF files, follow these steps:

  1. Navigate to the folder containing the files you want to merge, then switch to the list view and select the relevant files.

  2. Click the __ Action button and select __ Merge PDFs.

  3. If needed, click Add file to browse and select a PDF file from your computer.

  4. Click the __( scissors) icon between the files.

  5. Click Split to merge them.




Nota

The original PDFs are replaced by the merged version.

Suggerimento

  * Press **Shift + S** to add or remove all splits between pages.

  * To delete a specific page, select the page, then click Delete.




### Requesting files¶

Request files from users as a reminder for them to upload specific files. To do so, follow these steps:

  1. Click New and select Request.

  2. Enter a Document Name and select the person you’re requesting it from in the Request To field.

  3. If needed, set a Due Date In, choose the Folder where the file should be added, add Tags, and write a Message.

  4. Click Request.




A placeholder for the missing file is created in the selected folder. Once the file is available, click the placeholder to upload it.

Suggerimento

You can also request a document from the [list of scheduled activities](../essentials/activities.html#activities-all).

To see the list of all requested files, switch to the Activity view of the Documents app and go to the Requested Document column. Click a requested file’s date to view its details. You can then:

  * Upload a file using the __( upload) button;

  * Edit the activity using the __( edit) button;

  * Cancel the activity using the __( cancel) button;

  * Send a reminder email. Click Preview to preview the content of the reminder email if needed, then Send Now.




To send a reminder email for all requested files, click the __( ellipsis) icon in the Requested Document column and select Document Request: Reminder.

## Details panel¶

To view a folder’s or file’s information and tags, select the folder or file, then click the __( Info & Tags) button in the upper-right corner next to the view icons.

The details panel allows the following:

  * Change the file’s folder or the folder’s name.

  * View the file’s or folder’s size and the folder’s item count.

  * Change the file’s or folder’s Owner and Contact. By default, the person who creates a file or folder is set as its Owner and granted full access rights to it. To change it, select the required user from the dropdown list. The Contact is a person who only has Viewer access rights to the file or folder, e.g., an existing supplier in the database.

Nota

To view a file from their user profile, a user must be set as the Contact and have at least Viewer access.




### Alias e-mail¶

You can use an email alias to automatically save files sent to the email alias into a specific folder. To set up an email alias for a folder, follow these steps:

  1. Select the folder where files should be saved.

  2. Click the __( Info & Tags) in the upper-right corner next to the view icons.

  3. In the details panel, enter the desired Email alias and select or create the domain.

  4. Optionally, specify an Activity type and assignee to create an [activity](../essentials/activities.html) when a file is received via the alias.

  5. Optionally, select the Tags to automatically apply to the files created through the alias.




Vedi anche

[Gestire messaggi in entrata](../general/email_communication/email_servers_inbound.html)

### Etichette¶

Tags help organize and categorize files, making it easier to search and filter them. To configure tags for files, go to Documents ‣ Configuration ‣ Tags. Click New to create a new tag. Enter the Tag Name, select a Color, and optionally add a Tooltip that appears when hovering over the tag.

To add tags to a file, open the file, click the __( Info & Tags) in the upper-right corner next to the view icons, and then, in the details panel, select a tag from the dropdown list.

Nota

Alias tags can also be used to automatically apply tags to files created through the alias.

## Share and access rights¶

Nota

You can only share folders and files and edit their access rights if you have editing rights.

Access rights can be set on:

  * folders: Select the folder, click the __( gear) icon, and select Share.

  * files: Open the file and click Share in the top bar.




In the Share pop-up, grant access to specific users or contacts by selecting their name from the dropdown menu or by adding their email address manually, then select Viewer or Editor.

Suggerimento

To remove a permission or set an expiration date for it, hover the mouse over the relevant contact and click the __( remove) or __( calendar) button, respectively.

To set General access for Internal users or Anyone with the link, select Viewer, Editor, or None (to restrict access completely). For Anyone with the link, you can further specify whether the folder or file should be Discoverable (accessible through browsing) or require that users Must have the link to access it.

Nota

  * Public users Must have the link to access a folder or file on the portal when connecting for the first time.

  * Each folder and file URL includes the access rights that have been set for it. When you share a folder, the person you share it with is directed to a dedicated portal where they can view the files in that folder, excluding any with restricted access.




Suggerimento

[Portal users](../general/users/portal.html) can access folders and files they have permission to view or edit through the customer portal by clicking the Documents card.

## File digitization with AI¶

Files available in the Finance folder can be digitized. Select the file, click Create Vendor Bill, Create Customer Invoice, or Create Customer Credit Note, then click Send for Digitization.

Vedi anche

[AI-powered document digitization](../finance/accounting/vendor_bills/invoice_digitization.html)

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/productivity/documents.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](sign.html "Firma") |
  * [precedente](../productivity.html "Produttività") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
  * [Produttività](../productivity.html) »
  * Documenti


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