# ECO type — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](version_control.html "Version control") |
  * [precedente](engineering_change_orders.html "Engineering change orders") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Product lifecycle management](../../plm.html) »
  * [Change management](../manage_changes.html) »
  * ECO type



# ECO type¶

An _ECO type_ is assigned to _engineering change orders_ (ECOs) to organize and track changes to products and bills of materials (BoMs). Each ECO type separates ECOs into a project in Gantt view, ensuring collaborators and stakeholders **only** view and assist with relevant BoM improvements.

For example, an electronic chip manufacturer might use “New Product Introduction”, “Product Improvement”, “Component Change”, and “Firmware Update” ECO types. Then, designers and engineers can focus on ECOs in the “New Product Introduction” and “Product Improvement” projects, avoiding unrelated supplier change or firmware update ECOs.

## Create ECO type¶

To access and manage ECO types, navigate to PLM app ‣ Configuration ‣ ECO Types.

Create a new ECO type by clicking New. On the new ECO Types form, fill in the following information:

  * Name: the name of the ECO type, which will organize all of the ECOs of this _type_ in a project.

  * Email Alias: if this optional field is filled, emails submitted to this email address automatically generate ECOs in the left-most stage of this ECO type.




Example

The `Formulation change` ECO type is used to organize and track related ECOs in a single project. Configuring the Email Alias field generates ECOs in the `Formulation change` project sent to the email address, `pawlish-change@pawlished-glam.odoo.com`.

## Edit ECO type¶

Modify existing ECO type names and email aliases by navigating to the PLM app ‣ Configuration ‣ ECO Types page. There, click on the desired ECO type from the list.

On the form for each ECO type, proceed to edit the Name and Email Alias fields.

## Fasi¶

Within an ECO type project, _stages_ are like milestones and are used to identify the progress of the ECO before the changes are ready to be applied. (e.g. “Feedback”, “In Progress”, “Approved”, “Complete”)

Additionally, required approvers can be added to each stage, ensuring that changes to the production BoM cannot proceed until the approver reviews and approves the ECO. Doing so prevents errors on the production BoM by enforcing at least one review of suggested changes before they’re applied on a production BoM.

For best practice, there should be at least one _verification_ stage, which is a stage with a required approver, and one _closing_ stage, which stores ECOs that have been either canceled or approved for use as the next production BoM.

### Create stage¶

To add a stage, go to the PLM app and select the intended project for an ECO type from the PLM Overview dashboard.

Then, on the Engineering Change Orders project pipeline for the ECO type, click the \+ Stage button. Doing so reveals a text box to fill in the name of the stage. After filling it in, click the Add button to finish adding the stage.

Example

A new `Assigned` stage separates assigned ECOs from the unassigned ones in the `New` stage. Adding another stage helps the product manager track unassigned tasks.

### Verification stage¶

Click an ECO type from PLM app ‣ Overview to open a kanban view of ECOs of this type.

To configure a verification stage, hover over the intended stage, and select the ⚙️ (gear) icon. Then, click Edit to open a pop-up window.

Configure the verification stage in the edit stage pop-up window, by checking the box for Allow to apply changes.

Then, add an approver in the Approvers section, by clicking Add a line, and specifying the Role of the reviewer, their User, and Approval Type.

Make sure at least one approver is configured with the Approval Type: Is required to approve.

The approver listed is automatically notified when ECOs are dropped in the stage specified in the pop-up window. Once finished, click Save & Close.

Example

In the ECO type `New Product Introduction`, the verification stage `Validated` is configured by clicking the ⚙️ (gear) icon, and selecting Edit. Doing so opens the Edit: Validated pop-up window.

By adding the `Engineering manager` as an approver, only ECOs approved by this user can proceed to the next stage, and have the changes applied on the production BoM.

Additionally, check the Allow to apply changes option to ensure proper behavior.

### Closing stage¶

Configure a closing stage by opening the Edit: [stage] pop-up window. To do so, hover over the intended stage and click the ⚙️ (gear) icon that appears in the top-right corner. Then, click Edit from the drop-down menu.

On the Edit: [stage] pop-up window, select the check boxes for Folded in kanban view, Allow to apply changes and Final Stage.

Example

The closing stage, `Effective` is configured by checking the Folded in kanban view, Allow to apply changes, and Final Stage options

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/plm/manage_changes/eco_type.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](version_control.html "Version control") |
  * [precedente](engineering_change_orders.html "Engineering change orders") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Product lifecycle management](../../plm.html) »
  * [Change management](../manage_changes.html) »
  * ECO type


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
  *[FBM]: Fulfilled By Merchant
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
  *[BOM]: Bill of Materials
  *[Bacs]: Bankers' Automated Clearing Services
  *[RCM]: Reverse Charge Mechanism
  *[PDT]: Payment Data Transfer
  *[ECO]: Engineering Change Order
  *[ECOs]: Engineering Change Orders