# Engineering change orders — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](eco_type.html "ECO types and stages") |
  * [precedente](../manage_changes.html "Change management") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Product lifecycle management](../../plm.html) »
  * [Change management](../manage_changes.html) »
  * Engineering change orders



# Engineering change orders¶

Utilize _engineering change orders_ (_ECOs_) to track, implement, and revert change versions made to products, and [bills of materials](../../manufacturing/basic_setup/bill_configuration.html).

Engineering change orders can be created:

  1. directly in the ECO type.

  2. automatically from feedback submitted to the [ECO type’s email alias](eco_type.html#plm-eco-eco-type).




## Crea OMT¶

To create a new ECO, begin by navigating to the **PLM** app. Then, select the ECO type that should be used to track the progress of the change. On the Engineering Change Orders page, click the New button in the top-left corner.

Nota

[ECO types](eco_type.html) categorize and organize change orders. Doing so can ensure that employees only view the ECOs related to their responsibilities, whether it involves new product introductions, targeted product line updates, or regulatory compliance fulfillment.

On the ECO form, fill in the following fields accordingly:

  * Description is a brief summary of the improvement.

  * Type: specifies the ECO type project for organizing the ECOs.

  * Apply on determines if the ECO changes the Bill of Materials or the Product Only.

  * Product indicates the product being improved.

  * Bill of Materials specifies the changed BoM. It auto-populates if the product in Product field has an existing BoM. If multiple BoMs exist, select the intended radio options from the drop-down menu.

> Importante
> 
> A Product must be selected before Bill of Materials options is available.

  * Company field is used in multi-company databases. Specify if the change applies to products in a specific company, or leave blank if the change applies to all companies.

> Nota
> 
> Company is only available to specify with multiple companies enabled. See [Multi-azienda](../../../general/multi_company.html).

  * Responsible represents the assignee in charge of this ECO. (Optional)

  * Effective specifies when the ECO becomes live. Choosing As soon as possible means the ECO applies to the production BoM as soon as an authorized user applies the changes. At Date with a specific date selected will only apply the BoM at that date, making it easier to track the version history of the BoM in production.

  * Tags are assigned to ECOs for prioritization and organization. Create a new tag by typing the name in the field and selecting Create from the drop-down menu. (Optional)




After filling out the ECO form, click the Start Revision button to begin implementing the changes.

By pressing Start Revision, three actions occur:

  1. The Documents smart button appears, storing the relevant files of the BoM.

  2. A copy of the production BoM is stored in the newly-appeared Revision smart button of the ECO. The next available version number (e.g., `V2`, `V3`, …) is also assigned to keep track of all BoM versions.

  3. The stages of the ECO Type are displayed in the top-right corner of the ECO.




Nota

The Revision smart button is available **only** when the Bill of Materials radio button is selected in the Apply on field, and the Start Revision button has been pressed.

## Change components¶

To modify the components in a BoM, click the Revision smart button on an ECO to access the new version of the BoM. Odoo distinguishes the non-production version of the BoM from the current version, by flagging the test BoM with a large Archived tag.

Example

After clicking the Start Revision button for an ECO for the product, `[D_0045 Stool]`, make changes to the product’s BoM by clicking the Revision smart button. Doing so opens the archived BoM, marked with a large red Archived flag.

On the new BoM, in the Components tab, proceed to modify the components list, by changing the Quantity of existing components, adding new components using the Add a line button, and removing components with the 🗑️ (trash) icon.

Example

In version two of the BoM for a keyboard, the component quantities are reduced, and an additional component, `Stabilizers`, is added.

### Compare changes¶

To compare a revised BoM to the previous version, navigate to the ECO for that BoM in either of these ways:

  1. From the revised BoM, click the ECO name (for example, `ECO005: Improve...`) in the breadcrumbs located in the top-left corner.

  2. From the PLM Overview, click the Engineering Changes button on the BOM Updates Kanban card. Click the Kanban card for the appropriate ECO to open it.




On the ECO form, a new BoM Changes tab displays the differences between the current BoM and the new version.

Blue text indicates new components added to the revised BoM that are not in the production BoM. Black text represents updates shared by both BoMs, while red text indicates components removed in the revised BoM.

Changes and tests are encapsulated in the revised BoM, and do **not** affect the BoM currently used in production. That is, until the changes are applied.

Example

View the summary of the differences between the current and revised keyboard BoMs in the BoM Changes tab of the ECO.

## Change operations¶

To modify the operations in a BoM, click the Revision smart button on an ECO to access the archived, new version of the BoM.

In the new BoM version, switch to the Operations tab to view and edit BoM operations. To make changes, select each operation, which opens the corresponding Open: Operations pop-up window.

Nota

The Operations tab is _not_ available by default. To enable it, navigate to Manufacturing app ‣ Configuration ‣ Settings, and check the Work Orders box.

Make changes to any of the fields in the Open: Operations pop-up window, then click Save once completed.

Create new operations by clicking the Add a line button, and remove new operations by clicking the Archive Operation button.

### Compare changes¶

To compare a revised operations to the previous version, navigate to the ECO for the BoM in either of these ways:

  1. From the revised BoM, click the ECO name (for example, `ECO005: Improve...`) in the breadcrumbs located in the top-left corner

  2. From the PLM Overview, select the ECO type card, and then the correct ECO from the Kanban view.




On the ECO form, a new Operation Changes tab displays the differences between the current production BoM and the new version.

Blue text indicates new operations added to the revised BoM that do not yet exist in the production BoM. Black text represents updates shared by both BoMs, while red text indicates operations removed in the revised BoM.

Modifications to the BoM in an ECO will **not** affect the BoM used in production. That is, until the changes are applied.

In the Operation Changes tab, each row of details, beneath the columns in the table, reflect the following information:

  * Operation: Name of the operation that was modified.

  * Step: specifies the quality control point, visible when the operation includes detailed instructions.




Nota

To check for instructions, click the operation line item in the Operations tab of a BoM. Then, in the Open: Operations pop-up window, look for the Instructions smart button displayed at the top.

Example

The `Assembly` Operation includes `10` detailed Instructions to complete it.

  * Step Type details the type of quality control for further instructions in the operation.

  * Type corresponds with the colored text to specify how the revised BoM differs from the production BoM. Operation change types can be Add, Remove, or Update.

  * Work Center specifies the work center at which the operation is performed.

  * Manual Duration Change refers to the change in the Default Duration field in the Open: Operations pop-up window, which specifies the expected time for completing the operation.




Example

The Operation Changes tab compares the production BoM with the revised BoM in the ECO.

In the revised BoM, a new `Assembly` Operation at the Work Center `Assembly Line 1` is added. In addition, the expected duration of the operation is `20.00` minutes, as specified by the Manual Duration Change.

To supplement the `Assembly` operation, two quality control point instructions are added:

  1. The first is the Step `QCP00039`, a Step Type to Register Production of components.

  2. The second Step is `QCP00034`, an `Instructions` Step Type that provides additional assembly details.




## Applica modifiche¶

After verifying the changes, move the ECO to a [verification stage](eco_type.html#plm-eco-stage-config), which are stages that require approval before the revised changes can be applied to the production BoM.

Once the approvers accept the changes, the Apply Changes button becomes available. Click this button, and the ECO is automatically moved to a closing stage. The changes are applied, which archives the original production BoM, and the revised BoM becomes the new production BoM.

### Verify changes¶

To ensure the changes are live, from the ECO where the Apply Changes button was pressed, return to the revised BoM by clicking the Revision smart button.

On the revised BoM, the large red Archived flag is removed.

To further verify the changes, check the production BoM by going to Manufacturing app ‣ Products ‣ Products and select the product.

Then, on the product form, click the Bill of Materials smart button, and select the BoM from the list. In the Miscellaneous tab of the BoM, the Version field is updated to match the version number shown on the Revision smart button of the latest ECO.

Example

After applying the changes of the ECO for the keyboard, view the version of the current keyboard BoM in the Miscellaneous tab. Here, the Version number has been updated to `2`, matching the `V2` that appears in the Revision smart button of the ECO.

## View changes¶

To review proposed changes, navigate to the PLM app ‣ Overview. In the `BOM Updates` ECO type card, the # Engineering Changes button represents the number of operational changes created.

Click on the # Engineering Changes button to open the Kanban view of the ECO type. To view the suggestion, select an ECO in the `New` stage.

On the ECO, view a summary of the proposed changes in the Operation Changes tab. Click the Revision smart button to navigate to the revised BoM and look into the proposed changes in greater detail.

Example

An operator suggested another check for broken components by adding a step while performing the `Assemble switches` operation for the MO `WH/MO/00010` for the product, `Keyboard`.

Then, this created ECO can be viewed by navigating to the `BOM Changes` ECO type found in PLM app ‣ Overview.

The Responsible field is assigned to the operator who made the suggestion, allowing the employee revising the BoM to seek further clarification from the person who proposed the changes.

On the revised BoM, switch to the Operations tab, and select the __(Show Instructions) icon. Doing so opens a list of Steps to perform the operation, with the newest instruction titled `New Step Suggestion:`, followed by the user-entered title. Click the line item to view the suggested changes.

### Quality control points¶

Importante

The [Quality](../../quality.html) app is required to configure quality control points.

On the [quality control point](../../quality/quality_management/quality_control_points.html#quality-quality-management-quality-control-points) form, ensure the following form fields are accurately filled out to give detailed instructions for operators:

  * Title: rename to give a concise description of the new instruction.

  * Control per: using the drop-down menu, determine whether this instruction applies broadly for the Product, specifically for this Operation _only_ , or a particular Quantity of the product.

  * Type: categorizes the control point type. From the drop-down menu, select Instructions to detail an instruction for the worker. To receive input from the workers, select the Take a Picture, Register Consumed Materials, Print Label, or other [quality check options](../../quality/quality_management/quality_control_points.html#quality-quality-management-quality-control-points).




Vedi anche

[Configure quality control points](../../quality/quality_management/quality_control_points.html#quality-quality-management-quality-control-points)

Once the quality control point is configured, return to the Steps list using the breadcrumbs. Finally, drag the last quality control line item to its intended order of instructions.

Example

Drag and reorder the `Check for broken switches` instruction, by clicking and dragging its __(draggable) icon to move it from the bottom to the second position.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/inventory_and_mrp/plm/manage_changes/engineering_change_orders.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](eco_type.html "ECO types and stages") |
  * [precedente](../manage_changes.html "Change management") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Supply Chain](../../../inventory_and_mrp.html) »
  * [Product lifecycle management](../../plm.html) »
  * [Change management](../manage_changes.html) »
  * Engineering change orders


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
  *[FBM]: Fulfilled by Merchant
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