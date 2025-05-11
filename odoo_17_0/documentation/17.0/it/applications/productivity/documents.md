# Documenti — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](sign.html "Firma") |
  * [precedente](../productivity.html "Produttività") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Produttività](../productivity.html) »
  * Documenti



# Documenti¶

**Odoo Documents** allows you to store, view, and manage files within Odoo.

You can upload any file (max 64MB per file on Odoo Online) and organize them in various workspaces.

Vedi anche

  * [Odoo Documents: product page](https://www.odoo.com/app/documents)

  * [Odoo Tutorials: Documents basics [video]](https://www.odoo.com/slides/slide/documents-basics-6841?fullscreen=1)

  * [Odoo Tutorials: Using Documents with your Accounting App [video]](https://www.odoo.com/slides/slide/accounting-integration-and-workflow-actions-6853?fullscreen=1)




## Configurazione¶

By going to Documents ‣ Configuration ‣ Settings, you can enable the centralization of files attached to a specific area of your activity. For example, by ticking Human Resources, your HR documents are automatically available in the HR workspace, while documents related to Payroll are automatically available in the Payroll sub-workspace. You can change the default workspace using the dropdown menu and edit its properties by clicking the __( Internal link) icon.

Nota

  * If you enable the centralization of your accounting files and documents, it is necessary to click on Journals and define each journal independently to allow automatic synchronization.

  * If you select a new workspace, existing documents are not moved. Only newly created documents will be found under the new workspace.




## Spazi di lavoro¶

Workspaces are hierarchical folders having their own set of tags and actions. Default workspaces exist, but you can create your own by going to Documents ‣ Configuration ‣ Workspaces and clicking New. On the new page, fill in the following information:

  * Nome

  * Parent Workspace: if you want to create a sub-workspace, select its Parent Workspace.




Three tabs are available: Tags, Access Rights, and Description.

### Etichette¶

Tags are used within workspaces to add a level of differentiation between documents. They are organized per category, and filters can be used to sort them.

From the Tags tab, click Add a line, create the Tag Category, and Name your tags.

Nota

  * The tags of a parent workspace apply to the child workspaces automatically;

  * Tags can be created and modified by going to Documents ‣ Configuration ‣ Tags;

  * Tags can also be created or edited by clicking the __( gear) icon on the left panel;

  * An email alias can be used to automatically send received documents to a specific workspace based on the tag assigned.




### Diritti di accesso¶

To manage your workspace access rights, go to the Access Rights tab. You can add Write Groups that can view, create, and edit the workspace’s documents. You can also add Read Groups that only view the workspace’s documents.

Suggerimento

Enable Own Documents Only to limit Read Groups and Write Groups to the documents of which they are owner.

### Descrizione¶

You can add descriptive information to your workspace by going to the Description tab.

Nota

Workspaces can also be created and edited by clicking the __( gear) icon on the left panel.

## Documents management¶

When selecting or opening a document, the right panel displays different options, including, for example:

  * __( Download);

  * __( Share this selection): a share URL is copied to your clipboard;

  * __( Replace): select a new file to replace the existing one. Scroll down to the bottom of the right panel to see the History and restore, download, or delete the document;

  * __( Lock);

  * __( Split).




You can also __ Open chatter or delete the document by clicking the __( Move to trash) icon.

Nota

Items moved to the trash are permanently deleted after 30 days.

To modify the name of your file, click on Name. A Contact or an Owner can be assigned. The related Workspace can be modified and it is possible to access the related Journal Entry or add Tags.

Nota

  * The Contact is a person related to the document who only has read access rights to the document, e.g., an existing supplier in your database;

  * The creator of a document is automatically assigned as its Owner and is granted full access rights to it. To replace the owner of a document, select the required user from the dropdown list in the Owner field.




Suggerimento

An employee must be a user and the owner of a document to view it in **My Profile**.

Different Actions are available at the bottom of the right panel, depending on the workspace where your document is stored.

### Split PDF documents¶

Select the PDF you want to split, and click the __( scissors) icon. A new view displays all the pages of the document.

By default, all pages are split when you click Split. To remove a split between two pages, click the __( scissors) icon.

Suggerimento

To merge documents from your dashboard, select them and click the __( scissors) icon. Click on the scissors between the two documents and click Split to merge the documents.

### Additional features¶

Select a workspace and click the __( down arrow) next to the Upload button to access additional features:

#### Richiesta¶

You can request files and organize them as documents to remind users to download them.

Select the workspace where the file should be stored, click the __( down arrow) next to the Upload button, then Request. Add the Document Name and select the person you need it from in the Request To field. You can also fill in the Due Date In, confirm the Workspace the document should belong to, and add Tags and a Message. Then, click Request. A placeholder for the missing document is created in the workspace.

When your document is available, click the placeholder to upload it.

You can see all missing documents by going to the **Activity** view and the Requested Document column.

Suggerimento

From the Activity view, you can send a **reminder email** to users from whom you are expecting a document. Go to the Requested Document column and click the __( ellipsis) icon, and Document Request: Reminder. Click on a date to see the details of a specific request. You can update it by clicking on the __( pen) icon, Preview the content of the reminder email, or Send Now to send a reminder email.

> #### Aggiungi link¶

To add a link to your documents dashboard, click Add a Link, enter the URL, and Name it.

#### Condividi¶

You can make a document or a workspace accessible to anyone by sharing a URL.

##### Share a document¶

To generate a **share link** to a document, select the document, click the __( down arrow) next to the Upload button, and click Share.

In the pop-up, you can Name the share link, set a validity date by filling in the Valid Until field, and if you own more than one site, select the Website you want so the right domain name is reflected in the URL.

Click Copy or Share to send the URL to whomever you want.

Suggerimento

You can also generate a share URL by selecting the document, going to the right panel, and clicking the __( Share this selection) icon.

##### Share a workspace¶

You can share a link to a workspace and allow users to Download its content or Download and Upload files to it.

To do so, go to the left column of your dashboard. In the Workspace section, select the workspace to share, and possibly one or several tags that will be automatically added to the uploaded documents. Then, click the __( down arrow) next to the Upload button and Share.

In the pop-up, a share URL you can Copy is displayed. You can Name your share link, set a validity date by filling in the Valid Until field, tick the Include Sub Folders box if you want to share the workspace’s sub-folders, and if you own more than one site, select the Website you want so the share link reflects the right domain name.

Then, allow users to either Download files from your workspace, or to Download and Upload files to it.

Nota

  * The links added to your workspace using the Add a Link option cannot be shared and are, therefore, excluded;

  * When tags are applied to a shared workspace, users can exclusively access the documents associated with those tags.




###### Caricato via e-mail¶

Select the Download and Upload option to enable users to upload their files to your workspace using an Email Alias. To create the email alias, enter its name in the Email Alias field. The [domain name](../general/email_communication.html) should be set by default, but you can modify it by clicking it.

The documents sent to this email alias are uploaded to the workspace using the chosen tags.

Nota

  * By default, the Document Owner is the person who uploads a file to a workspace, but you can select another user. You can also set a Contact, usually an external person, such as a partner.

  * Enable Create a new activity to automatically create an activity when a document is uploaded. Select the Activity type from the dropdown list and set the Due Date In field. You can also add a Summary and a Responsible person assigned to the activity.




Suggerimento

Go to Configuration ‣ Share & Emails to see and manage your share links. Select a line and click Delete to disable the URL. People who have received this link will no longer be able to access the document(s) or workspace.

#### Nuovo foglio di calcolo¶

To create a new [spreadsheet](spreadsheet.html), click New Spreadsheet. You can select a Blank spreadsheet or an [existing template](spreadsheet/templates.html).

## Workflow actions¶

Workflow actions help manage documents and overall business operations. These are automated actions that can be created and customized for each workspace. With a single click you can, for example, create, move, sign, add tags to a document, and process bills.

When a document meets the set criteria, these workflow actions appear on the right panel.

### Create workflow actions¶

To update an existing workflow action or create a new one, go to Documents ‣ Configuration ‣ Actions and click New.

Nota

An action applies to all **sub-workspaces** under the Related Workspace you selected.

### Set the conditions¶

Define the Action Name and then set the conditions that trigger the appearance of the __( play) icon on the right-side panel when selecting a file.

There are three basic types of conditions you can set:

  1. Tags: you can use the Contains and Does not contain conditions, meaning the files _must have_ or _must not have_ the tags set here;

  2. Contact: the files must be associated with the contact set here;

  3. Owner: the files must be associated with the owner set here.




Suggerimento

If you do not set any conditions, the action button appears for all files inside the selected workspace.

#### Advanced condition type: domain¶

Importante

It is recommended to have some knowledge of Odoo development to configure _Domain_ filters properly.

The [developer mode](../general/developer_mode.html#developer-mode) needs to be activated to access the Domain condition from the Actions tab. Once done, select the Domain condition type and click New Rule.

To create a rule, you typically select a field, an operator, and a value. For example, if you want to add a workflow action to all the PDF files inside a workspace, set the field to _Mime Type_ , the operator to _contains_ , and the pdf value.

Click the __( Add New Rule) icon and the __( Add branch) icon to add conditions and sub-conditions. You can then specify if your rule should match all or any conditions. You can also edit the rule directly using the Code editor.

### Configure the actions¶

Select the Actions tab to set up your action. You can simultaneously:

  * **Move to Workspace** : move the file to any workspace;

  * **Create** : create one of the following items attached to the file in your database:

    * **Link to record** : create a link between a document and a record from a specific model;

    * **Product template** : create a product you can edit directly;

    * **Task** : create a Project task you can edit directly;

    * **Signature PDF template** : create a new Sign template to send out;

    * **PDF to sign** : create a Sign template to sign directly;

    * **Applicant** : create a new HR application you can edit directly;

    * **Vendor bill** : create a vendor bill using OCR and AI to scrape information from the file content;

    * **Customer invoice** : create an invoice using OCR and AI to scrape information from the file;

    * **Vendor credit note** : create a vendor credit note using OCR and AI to scrape information from the file;

    * **Credit note** : create a customer credit note using OCR and AI to scrape information from the file;

    * **Miscellaneous Operations** : create an entry in the Miscellaneous Operations journal;

    * **Bank Statement** : import a bank statement;

    * **Purchase Receipt** : create a vendor receipt;

    * **Expense** : create an HR expense.

  * **Set Contact** : add a contact to the file, or replace an existing contact with a new one;

  * **Set Owner** : add an owner to the file, or replace an existing owner with a new one;

  * **Set Tags** : add, remove, and replace any number of tags;

  * **Activities - Mark all as Done** : mark all activities linked to the file as done;

  * **Activities - Schedule Activity** : create a new activity linked to the file as configured in the action. You can choose to set the activity on the document owner.




## Digitize documents with AI and optical character recognition (OCR)¶

Documents available in the Finance workspace can be digitized. Select the document to digitize, click Create Bill, Create Customer Invoice, or Create credit note, and then click Send for Digitization.

Vedi anche

[AI-powered document digitization](../finance/accounting/vendor_bills/invoice_digitization.html)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/productivity/documents.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](sign.html "Firma") |
  * [precedente](../productivity.html "Produttività") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
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
  *[EDI]: electronic data interchange
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
  *[FBM]: Fulfilled By Merchant
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
  *[RUT]: Registro único tributario
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
  *[CSV]: Valori separati da virgola
  *[SLAs]: Service Level Agreements
  *[SLA]: Service Level Agreement
  *[UTM]: Urchin Tracking Module
  *[GTM]: Google Tag Manager
  *[CDN]: Content Delivery Network
  *[CORS]: Cross-Origin Resource Sharing
  *[HTML]: HyperText Markup Language
  *[UI]: user interface