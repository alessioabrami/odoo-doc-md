# Kenya — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](luxembourg.html "Lussemburgo") |
  * [precedente](jordan.html "Giordania") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Kenya



# Kenya¶

## Configurazione¶

Install the 🇰🇪 **Kenyan** [fiscal localization package](../fiscal_localizations.html#fiscal-localizations-packages) to get all the features of the Kenyan localization.

## eTIMS¶

The [Kenya Revenue Authority (KRA)](https://www.kra.go.ke/) has implemented the [electronic Tax Invoice Management System (eTIMS)](https://www.kra.go.ke/online-services/etims) for tax collection.

To submit documents through eTIMS, you must use an OSCU that integrates with the existing **Trader Invoicing System (TIS)** , such as the one provided by Odoo. The OSCU is used to validate, encrypt, sign, transmit, and store tax invoices.

Nota

Make sure to [install](../../general/apps_modules.html#general-install) the **Kenya eTIMS EDI** modules to use the OSCU device fully.

### OSCU device initialization¶

The OSCU must be initialized before use. To do so, navigate to Settings ‣ General Settings, click Update Info in the Companies section, and enter your Tax ID.

To initialize the OSCU:

  1. Go to Settings ‣ General Settings and scroll down to the Kenya eTIMS Integration section.

  2. Set the eTIMS Server Mode to Test for the initialization.

  3. Enter the Serial Number of the device and tick the two check boxes.

  4. Click Initialize OSCU.




Nota

Three server modes are available:

  * Demo: Designed for demo purposes; it uses mock data and does not require an initialized OSCU;

  * Test: Used to test the connection to eTIMS;

  * Production: Used for live databases that are ready to send data.




Importante

If your device has **already been initialized** (through another ERP, for example), enable the [Modalità sviluppatore (modalità di debug)](../../general/developer_mode.html). Then, in the Kenya eTIMS Integration section, enter the ID of the unit in the Unit ID field and the key obtained through a previous initialization in the CMC Key field. Click Save when done.

Once the **OSCU module** has been initialized, an OSCU serial number is generated for each company on that database with its **country** set to Kenya. The serial number is generated based on the VAT number of the company (regardless of its validity). It is a unique and sequential serial number starting with the prefix `ODOO` followed by the company’s **VAT number** and a sequence of numbers.

### Registering on eTIMS¶

Taxpayers _must_ sign up and create an account on the [KRA portal](https://etims.kra.go.ke/basic/login/indexLogin). If you do not have an account yet:

  1. Sign up, enter your **PIN** , and verify that all information is correct, including your phone number, email address, and postal address. Correct any errors on the [iTax page](https://itax.kra.go.ke/KRA-Portal/).

  2. An OTP is sent to the phone number provided. Unblock promotional messages if you do not receive it.

  3. Upload the **business owner ID** _or_ **director’s ID** (as listed on iTax), along with the filled-out and signed **commitment form** .

  4. On the **eTIMS dashboard** , click Service request at the top of the page. Select OSCU as the **eTIMS type** , enter `Odoo KE LTD` as the third-party integrator, and enter your company’s OSCU serial number retrieved earlier.




Nota

Service request approvals are usually quick. If there’s a delay, contact the eTIMS operation or KRA office.

Commitment form

  * Part 1: Fill in the taxpayer’s information.

  * Part 2: Fill in the business owner’s _or_ director’s information.

  * Part 3: Fill in your unique serial number found in Odoo.

  * Part 4: Tick **OSCU** , enter Odoo KE LTD PIN `PO52112956W`, and enter the Odoo version you’re using (17.0 or onwards).

  * Part 5: Check the mandatory boxes, enter a date, and sign.




### eTIMS codes¶

Common standard codes are **automatically** fetched from the KRA eTIMS API servers every two days. To fetch them manually, proceed as follows:

  1. Enable the [Modalità sviluppatore (modalità di debug)](../../general/developer_mode.html).

  2. Go to Settings ‣ Technical ‣ Automation: Scheduled Actions and search for KE eTIMS: Fetch KRA standard codes.

  3. Click the action in the list, then click Run Manually to fetch the codes.




Go to Accounting ‣ Configuration ‣ KE OSCU Codes to view the complete list of fetched OSCU codes.

### UNSPSC codes¶

The KRA needs UNSPSC codes for a product to be **registered**. UNSPSC codes are **automatically** fetched from the KRA eTIMS API servers every day. To fetch them manually, proceed as follows:

  1. Enable the [Modalità sviluppatore (modalità di debug)](../../general/developer_mode.html).

  2. Go to Settings ‣ Technical ‣ Automation: Scheduled Actions and search for KE eTIMS: Fetch UNSPSC codes from eTIMS.

  3. Click the action in the list, then click Run Manually to fetch the codes.




Go to the **product form** , and in the Accounting tab, click the UNSPSC Category field to view the complete list of fetched UNSPSC codes.

### Notices¶

Notices are **automatically** fetched from the KRA eTIMS API servers every day. To fetch them **manually** , proceed as follows:

  1. Enable the [Modalità sviluppatore (modalità di debug)](../../general/developer_mode.html).

  2. Go to Settings ‣ Technical ‣ Automation: Scheduled Actions and search for KE eTIMS: Fetch KRA notices from eTIMS.

  3. Click the action in the list, then click Run Manually to fetch the notices.




Go to Accounting ‣ Configuration ‣ KE OSCU Notices to view the complete list of fetched notices.

### Multi-azienda¶

Vedi anche

[Aziende](../../general/companies.html)

If you have [multiple companies](../accounting.html#accounting-multi-company), you can centralize and manage them all on a single Odoo database. The KRA identifies and differentiates the **main** company from its **subsidiaries** by using IDs. Furthermore, subsidiaries are classified as **branches** of the main company.

To configure the company’s ID, open the **Settings** app, click Update Info in the Companies section, and search for the eTIMS Branch Code field. The **main company** has a branch ID equal to `00` in a multi-company environment. Companies that are _not_ the main company have a branch ID other than `00` and are assigned an ID by the KRA.

To add a branch, go to the Branches tab in the **company settings** and click Add a line.

To fetch the **branch ID** from the KRA for your non-main companies, ensure the main company has a Kenyan Tax ID and the OSCU device has been initialized. Then, go to the Branches tab and click Populate from KRA.

Nota

  * The KRA considers each **place of supply** as a separate branch (ID).

  * The **OSCU** device must be initialized independently for each branch.




### Contact branch ID¶

To attribute a branch ID to a contact, access the contact form, go to the Accounting tab, and enter the branch code in the eTIMS Branch Code field.

Nota

By default, contacts” branch IDs are set to `OO`.

### KRA sequences¶

Importante

Odoo invoice sequences and KRA sequences are **different**.

In Odoo, invoice sequences depend on the **main company**. Main companies can see the invoices of branches, but branches **cannot** see the main company’s invoices or those of other branches.

The KRA needs **independent** sequences per branch. Therefore, Odoo manages sequences individually per branch.

Example

If you have a main company with two branches, the invoice sequence would be the following:

  * Creating an invoice on **branch 1** : INV/2024/00001;

  * Creating an invoice on **branch 2** : INV/2024/00002;

  * Creating an invoice on the **main company** : INV/2024/00003.




This is how Odoo manages sequences to be compliant with the KRA regulations:

  * Creating an invoice on **branch 1** : INV/2024/00001;

  * Creating an invoice on **branch 2** : INV/2024/00001;

  * Creating an invoice on the **main company** : INV/2024/00001.




## Assicurazione¶

For **health service providers** , you can send insurance information about the main and branch companies and update it in eTIMS. To do so, go to Accounting ‣ Configuration ‣ Settings, scroll to the Kenya eTIMS Integration section, and fill in the Code, Name, and Rate fields. Click Send Insurance Details when done.

## Product registration¶

The KRA requires **products to be registered** first before conducting business operations (such as stock movements, BOM, customer invoices, etc.). For a product to be registered, the following fields must be defined on the product form:

  * In the General Information tab: Cost.

  * In the Accounting tab:

    * Packaging Unit;

    * Packaging Quantity;

    * Origin Country;

    * eTIMS Product Type;

    * Insurance Applicable;

    * UNSPSC Category.




If the elements above are defined, the product is automatically registered while sending the operation to the KRA. If not, you will be alerted by a yellow banner at the top of the screen inviting you to check the missing elements.

## Stock movements¶

All **stock movements** must be sent to the KRA. They do not require an invoice if they are internal operations or stock adjustments; therefore, Odoo automatically sends them if at least one of the following conditions are met:

  1. No contact is set for the move;

  2. The contact is your main company or a branch of the main company.




If the stock moves are **external operations** (e.g., to contacts that are not part of the main company or its branches), the stock moves are automatically sent _after_ the invoice is sent to eTIMS.

Nota

  * The stock move must be confirmed before sending the invoice to eTIMS.

  * The product(s) must be registered for the stock move to be sent to eTIMS. If the product has not been registered yet, a yellow banner will prompt the products” registration.




## Acquisti¶

Odoo automatically fetches new vendor bills from eTIMS every day. You need to confirm the fetched vendor bills and send the confirmation to the KRA. To confirm a vendor bill, it must be linked to one or several confirmed purchase order line(s).

In the case of purchases (not customs imports), the steps to link purchase order lines with bills are the following:

  1. Go to Accounting ‣ Vendors ‣ Bills. The vendor bill is fetched from the KRA servers. The JSON file is available in the chatter of the vendor bill if needed.

  2. Odoo looks at the Tax ID (PIN) of the vendor (partner);

     * If it is unknown, a new contact (partner) is created.

     * If it is known and the branch ID is the same, Odoo uses the known contact.

  3. In the fetched bill from the KRA, select the Product. Each vendor bill _must_ contain a product to be confirmed and sent to eTIMS later on.

  4. Odoo checks existing purchase order lines matching the product(s) entered at the previous step and the partner (if any). Click the Purchase Order Line field, and select the correct related purchase order line(s) matching the product(s). The quantities on the bill _must_ be the same as the received quantities indicated on the purchase order.

If no existing purchase order line matches the lines of the fetched bill, click Create Purchase Order and create a purchase order based on the unmatched line(s). Validate the resulting stock move and Confirm the bill.

  5. Set a method in the eTIMS Payment Method field..

  6. Once all steps are completed, click Send to eTIMS to send the vendor bill. When the vendor bill has been confirmed on eTIMS, the **KRA invoice number** can be found in the eTIMS Details tab.




## Fatturazione¶

Nota

The KRA does _not_ accept sales if the product is not in stock.

This is the **advised sales flow** in Odoo when selling:

  1. Create a **sales order**.

  2. Validate the delivery.

  3. Confirm the invoice.

  4. Click Send and print, and then enable Send to eTIMS.

  5. Click Send & print to send the invoice.




Once the invoice has been sent and signed by the KRA, the following information can be found on it:

  * **KRA invoice number** ;

  * Mandatory KRA invoice fields, such as **SCU information** , **date** , **SCU ID** , **receipt number** , **item count** , **internal date** , and **receipt signature** ;

  * The **KRA tax table** ;

  * A unique **KRA QR code** for the signed invoice.




## Imports¶

Customs import codes are **automatically** fetched from the KRA eTIMS API servers every day. To fetch them manually, proceed as follows:

  1. Enable the [Modalità sviluppatore (modalità di debug)](../../general/developer_mode.html).

  2. Go to Settings ‣ Technical ‣ Automation: Scheduled Actions and search for KE eTIMS: Receive Customs Imports from the OSCU.

  3. Click the action in the list, then click Run Manually to fetch the codes.




Go to Accounting ‣ Vendors ‣ Customs Imports to view the imported codes.

The following steps are required to send and have **customs imports** signed by the KRA:

  1. Go to Accounting ‣ Vendors ‣ Customs Imports; The customs import is fetched automatically from the KRA.

  2. Match the imported item with an existing registered product in the Product field (or create a product if no related product exists).

  3. Set a vendor in the Partner field.

  4. Based on the partner, match the imported item with its related purchase order (see purchase steps). The stock must be correctly adjusted when the customs import is approved.

If no related purchase order exists, create one and Confirm it. Then, confirm the delivery by clicking Receive Products, then Validate on the purchase order.

  5. Click Match and Approve or Match and Reject, depending on the situation of the goods.




Nota

The JSON file received from the KRA is attached to the chatter of the customs import.

## BOM¶

The KRA requires all BOMs to be sent to them. To send BOMs to eTIMS, the product and its components _must_ be registered. To access a product’s BOM, click on the product and then click the Bill of Materials smart button.

Make sure the KRA’s required fields are filled in the KRA eTIMS details section of the Accounting tab in the product form, and click Send to eTIMS. The successful sending of the BOM is confirmed in the chatter, where you can also find the sent information in an attached JSON file.

## Credit notes¶

The KRA does not accept credit notes with quantities or prices higher than the initial invoice. When creating a credit note, a KRA reason must be indicated: In the credit note form, go to the eTIMS Details tab, select the eTIMS Credit Note Reason, and then select the invoice number in the Reversal of field.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/fiscal_localizations/kenya.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](luxembourg.html "Lussemburgo") |
  * [precedente](jordan.html "Giordania") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Kenya


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
  *[PAC]: Proveedor Autorizado de Certificación / Authorized Certification Provider
  *[PUE]: Pago en una Sola Exhibición/Payment in a Single Exhibition
  *[PPD]: Pago en Parcialidades o Diferido/Payment in Installements or Deferred
  *[CFDI]: Comprobante Fiscal Digital por Internet
  *[OSCU]: Online Sales Control Unit
  *[BOM]: Bill of Materials