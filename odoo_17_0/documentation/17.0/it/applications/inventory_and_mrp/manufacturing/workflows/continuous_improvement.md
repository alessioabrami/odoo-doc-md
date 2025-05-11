# Continuous product improvement — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../shop_floor.html "Linea di produzione") |
  * [precedente](byproducts.html "Sottoprodotti") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Produzione](../../manufacturing.html) »
  * [Workflow](../workflows.html) »
  * Continuous product improvement



# Continuous product improvement¶

_Continuous improvement_ is a general philosophy intended to help individuals and organizations constantly improve themselves and the work they produce.

There are a variety of different methodologies that fall under the umbrella of continuous improvement. These include kaizen, six sigma, and lean, among others. While the specific steps of each method differ, their goal remains the same: implement a process by which improvement is a perpetual goal, rather than a one-time accomplishment.

The sections below contain details about how Odoo can be used to implement four general steps common to many of the most popular continuous improvement strategies, with links to documentation about configuring the necessary features. The final section details how a specific company might configure these Odoo implementations within their organization.

  1. Identify problems

  2. Suggest improvements

  3. Implement strategies

  4. Review actions




Importante

Continuous improvement is not a one-size-fits-all methodology. While most strategies include between four and six steps, proper implementation requires developing a system tailored to the specific needs of each company.

This is not a limitation, but rather a benefit, as it makes the methodology flexible enough to adapt to almost any use case. Odoo, in particular, adapts well to this flexibility, as it can be configured to meet the needs of almost any workflow.

As such, it is important to remember the content below only provides _examples_ of how Odoo _might_ be used. They should be viewed as more of a starting point, rather than a concrete outline that every organization must follow.

## Identify problems¶

Before improvement can begin, it is necessary to determine where improvement is necessary. This is where identifying problems comes into play. Two of the best Odoo apps for identifying problems with products or processes are _Helpdesk_ and _Quality_.

### Helpdesk¶

The _Helpdesk_ app is useful for receiving feedback from outside of the organization, like from clients or customers. This is accomplished by implementing one (or more) of the methods for [receiving tickets](../../../services/helpdesk/overview/receiving_tickets.html), including email aliases, live chat conversations, and website forms.

Using these methods, customers can submit feedback about problems, which is then reviewed by a member of a [helpdesk team](../../../services/helpdesk.html). Depending on the outcome of the review, the team member may decide to take further action to ensure the issue is addressed. This can include creating a [quality alert](../../quality/quality_management/quality_alerts.html).

### Qualità¶

The _Quality_ app is useful for receiving feedback from _within_ the organization, like from employees.

One method for accomplishing this is to set up a [quality control point](../../quality/quality_management/quality_control_points.html) (QCP). A QCP is used to automatically create quality checks at regular intervals, prompting employees to inspect, and confirm, the quality of a product.

If an issue is found, an employee can then create a [quality alert](../../quality/quality_management/quality_alerts.html) to notify a quality team. Quality alerts can also be created independent of a QCP, in the event that an employee discovers an issue without being prompted to check for one. This is a great way for customer support employees to notify a quality team of an issue brought to their attention by a customer ticket.

## Suggest improvements¶

Once a problem is identified, the next step is to put forward ideas for how to address the problem. As with identifying problems, the _Quality app_ is also useful for suggesting improvements. In addition, the _PLM_ (_Product Lifecycle Management_) app can be used for this purpose, as well.

### Qualità¶

When creating a [quality alert](../../quality/quality_management/quality_alerts.html) to bring an issue to the attention of a quality team, the Corrective Actions and Preventive Actions tabs can be used to provide feedback about how the issue can be addressed.

The Corrective Actions tab is used to suggest a method for fixing items affected by the issue. For example, `Screw the bolts on tighter, so the seat stays in place`.

The Preventive Actions tab is used to suggest a method for preventing the issue from occurring in the future. For example, `Do not tighten the screws too much, or they will be stripped`.

The quality team that reviews the alert sees these suggested actions, and can take them into account when deciding how to address the issue.

### Gestione del ciclo di vita del prodotto¶

The PLM app is used to manage the lifecycle of a product from its introduction through each successive version. As such, it is useful for testing ideas for product improvements.

Using [engineering change orders](../../plm/manage_changes/engineering_change_orders.html), product management teams can create new iterations of product BoMs, adding or removing specific components or operations, as needed. The products created using these BoMs are put through a review process to confirm the effectiveness of the changes.

## Implement strategies¶

Implementing strategies involves putting the proposed solutions from the suggest improvements step into action. The PLM app continues to be useful during this step, as it can be configured to make BoM updates. The _Field Service_ app can also be used by certain companies to make improvements to products that have already been sold to customers.

### Gestione del ciclo di vita del prodotto¶

Once BoM changes have gone through the proper review process, they can be approved, and the updated BoM put into use. This is accomplished by configuring one of the ECO review stages to [apply the changes](../../plm/manage_changes/engineering_change_orders.html#plm-eco-apply-changes) made to the BoM, at which point the updated BoM becomes available for new MOs.

Product BoMs can continue to be updated, as needed. The [version control](../../plm/manage_changes/version_control.html) features of the PLM app allow for easy management of all versions of a given BoM.

### Assistenza sul campo¶

The PLM app is a great way to make changes to product BoMs. However, these changes only affect products produced using the new BoM. If a defective product has already been sold to a customer, it may be necessary to repair (or update) that product.

In such a case, the _Field Service_ app can be used to schedule [onsite interventions](../../../services/field_service/creating_tasks.html). These interventions allow service technicians (or other employees) to be sent to a customer’s location to address an issue with a product.

## Review actions¶

Reviewing actions is where the «continuous» part of continuous improvement comes into play, as it allows an organization to evaluate the decisions made in the previous steps. As such, this step is, essentially, returning to the beginning of the process, so that additional problems can be identified and addressed.

This means that the _Helpdesk_ and _Quality_ apps should be used again to receive customer and employee feedback. Another app that may be useful at this stage is the _Surveys_ app.

### Sondaggi¶

After implementing changes to a product or process, it may be wise to solicit customers for their feedback directly, rather than waiting to hear from them of their own volition. This may bring to light feedback that customers may have otherwise neglected to share.

One of the best ways to accomplish this is through the [Surveys](../../../marketing/surveys.html) app. Creating a survey, and sending it to customers who receive an updated product, increases the likelihood of receiving relevant feedback about the product.

Example workflow: coat rack product improvement

 _Wood Hut_ is a manufacturer of fine wood products. They are committed to manufacturing products of the highest-possible quality, and are always looking for ways to improve the products they sell, along with the processes used to create them.

Wood Hut uses the Odoo platform to manage every element of their production, fulfillment, and customer satisfaction processes. They have developed a custom product improvement workflow that incorporates the Helpdesk, Quality, PLM, and Manufacturing apps.

One of Wood Hut’s most popular products is their _coat rack_. It’s made entirely of oak, and customers describe it as «sleek and elegant.» However, recent customer feedback about the coat rack has brought attention to quality issues that necessitate revising the current manufacturing process.

The product revision workflow begins when the customer service team receives a ticket in the Helpdesk app from a customer having problems with the coat rack she purchased. The customer, Abigail Peterson, has found that her coat rack falls over when more than five coats are hanging from it. This is a major issue, as the coat rack has enough dowels for six coats.

Marc, the customer service employee assigned to the helpdesk ticket, opens the Quality app, and creates a new quality alert. He tags the _Production Quality Team_ and assigns Julie Andreson as the quality employee responsible for the alert.

Julie reviews the alert, and consults with her team about the best course of action. They decide that it is necessary to revise the product’s BoM to prevent the issue from occurring in the future, which Julie notes in the Corrective Actions tab of the quality alert.

Then, Julie messages product engineer, Joe Kazan in the chatter of the quality alert to bring it to his attention. Joe opens the PLM app and creates a new ECO, noting the problem with the coat rack, and suggesting that a change to the product’s BoM may be necessary.

Joe clicks Start Revision, and then the Revision smart button to open version two of the coat rack’s BoM. This BoM was created alongside the ECO, and remains archived until it is approved.

After some testing, Joe discovers that adding a metal _support rod_ to the coat rack strengthens it, allowing the rack to hold six or more coats without falling over. He updates the BoM to include the support rod as one of the components, and adds an extra operation to make sure it is installed during the manufacturing process. Finally, he leaves a message in the chatter of the ECO, letting his manager, Jose, know that it is ready for review.

Jose reviews the changes, and confirms they are an effective method for addressing the problem with the coat rack. He moves the ECO to the _Approved_ stage, which makes version two of the coat rack BoM the current version.

Now, each time an MO is created to produce a coat rack, the updated BoM is automatically selected. Wood Hut begins producing the improved coat rack, and customer feedback confirms that the new version has addressed the problem with its predecessor.

Using the Odoo platform, Wood Hut has implemented an end-to-end product improvement process. Since the essential elements of this process (customer feedback, quality control, etc.) are always functioning, it can be reused to continuously update products and processes.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/inventory_and_mrp/manufacturing/workflows/continuous_improvement.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../shop_floor.html "Linea di produzione") |
  * [precedente](byproducts.html "Sottoprodotti") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Produzione](../../manufacturing.html) »
  * [Workflow](../workflows.html) »
  * Continuous product improvement


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
  *[SO]: sales order
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
  *[SOs]: sales orders
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
  *[QCP]: Quality Control Point
  *[QCPs]: Quality Control Points
  *[RO]: Repair Order
  *[POs]: purchase orders
  *[PLM]: Product Lifecycle Management