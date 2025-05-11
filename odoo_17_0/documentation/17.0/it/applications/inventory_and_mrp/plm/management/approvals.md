# Approvazioni — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../repairs.html "Riparazioni") |
  * [precedente](../management.html "Project management") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Product lifecycle management](../../plm.html) »
  * [Project management](../management.html) »
  * Approvazioni



# Approvazioni¶

Notify stakeholders and managers automatically by assigning approvers to stages of [engineering change orders](../manage_changes/engineering_change_orders.html#plm-eco) (ECOs) under review. Changes can only be applied after the assigned approver accepts them. Approvals ensure reviews by team members, which prevents mistakes and premature actions.

Vedi anche

[Stage configuration](../manage_changes/eco_type.html#plm-eco-stage-config)

## Add approver¶

To add an approver, first go to the PLM app, and click on the project card of an ECO type to open the Gantt view of the ECOs.

On the Engineering Change Orders page, hover over the intended stage, and select the ⚙️ (gear) icon. Then, click Edit to open a pop-up window.

Nota

Approvers can be added to any stage, but it’s strongly recommended to assign them to the _verification_ stage, which comes before the _closing_ stage, where ECOs are applied, and the BoM version is updated.

See the documentation about [stage types](../manage_changes/eco_type.html#plm-eco-stage-config) for more information.

In the Edit stage pop-up window, click the Add a line button, located under Approvals. Then, type in the approver’s position (or title) under Role (e.g. `Engineering Manager`, `Quality Team`, etc.), and select the relevant User from the drop-down menu.

Next, set the Approval Type to Is required to approve, Approves, but the approval is optional, or Comments only.

Example

Assign the `CTO`, «Mitchell Admin,» as a required approver for ECOs in the `Validated` stage in the `New Product Introduction` ECO type.

Approvals from the quality and marketing teams are **not** required to apply changes to the ECO because their Approval Type is set to Approves, but the approval is optional and Comments only, respectively.

## Manage approvals¶

Approvers can easily track their to-do approvals by navigating to the PLM app, and looking at the card for an ECO type, which shows the count of open tasks assigned to them.

Here’s what each button on an ECO project card does:

  1. The # Engineering Changes button displays a count of in-progress ECOs of this ECO type. Clicking the button opens the Gantt view of the Engineering Change Orders page.

  2. My Validations displays a count of ECOs the approver must accept or reject. Clicking on this button displays ECOs pending approval or rejected (marked with the red Blocked state).

  3. The All Validations button shows the count of ECOs awaiting approval or rejected by any approver. Clicking it reveals these pending ECOs.

  4. To Apply displays a count of ECOs to which the user needs to apply changes. Clicking on the button displays all the ECOs to approve, and apply changes to, in the verification stage.

ECOs marked with the green Done stage have already been approved, and the user just needs to click on the ECO to enter the form view, and click the Apply Changes button.




### Approve ECOs¶

Navigate to an ECO in a verification stage, while logged in as the assigned approver, to see the Approve, Reject, and Apply Changes buttons.

To approve the ECO, and apply the changes onto the production BoM, click Approve, and then Apply Changes.

Note that the Apply Changes button will **not** work unless the Approve button was clicked first. Additionally, the chatter logs the history of the clicked buttons.

Avvertimento

When the Approval Type is **not** set to Is required to approve, approval from the associated user is not needed before applying changes with the Apply Changes button. Thus, the Apply Changes button **will work** without requiring the Approve button to be clicked first.

### Automated activities¶

When an ECO is moved to a verification stage, a planned activity is automatically created for assigned approvers to review the ECO. Approvers receive a notification in their activities inbox, accessible through the 🕘 (clock) icon at the top of the page.

In the to-do task list, the Engineering Change Order (ECO) notification displays the number of activities marked Late, Today, and Future. Clicking on each of these buttons shows a filtered Gantt view of the respective ECOs.

Example

Scheduled activities are shown as a number on the 🕘 (clock) icon, with `5` ECOs pending approval Today. Currently, there are `0` Late or Future ECOs.

> By clicking a pending ECO, a _planned activity_ for ECO Approval is recorded in the chatter. Click on the i (Info) icon to view additional information, including the approval’s Created date, the approver Assigned to it, and the due date.

#### Follow-up activities¶

When ECOs are rejected, tasks need to be assigned to project members for required modifications before ECO approval. To create tasks with deadlines, navigate to the rejected ECO form, and go to the chatter.

Select the Mark Done button in the Planned Activities section of the chatter to close the activity, and open a pop-up window for creating tasks.

In the Mark Done window, click Done & Schedule Next to open a new Schedule an Activity window. Next, set the Assigned to team member and the Due Date for completing the changes. Provide task details in the Summary field and the text box. Click the Schedule button to close the window.

After closing the window, on the ECO form, move the ECO back one stage. Doing so ensures that when the team member completes the changes, and returns the ECO to the verification stage, a new ECO Approval task is created for the approver.

Example

The approver creates an activity for the Responsible of the ECO, `Laurie Poiret`, that details the changes required for the approver to Accept the ECO. Clicking the Schedule button creates a planned activity for Laurie due on `08/15/2023`.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/plm/management/approvals.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../repairs.html "Riparazioni") |
  * [precedente](../management.html "Project management") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Product lifecycle management](../../plm.html) »
  * [Project management](../management.html) »
  * Approvazioni


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
  *[BoMs]: Bills of Materials
  *[MOs]: Manufacturing Orders