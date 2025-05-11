# India — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](indonesia.html "Indonesia") |
  * [precedente](hong_kong.html "Hong Kong") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * India



# India¶

## Installazione¶

[Install](../../general/apps_modules.html#general-install) the following modules to get all the features of the Indian localization:

Nome | Nome tecnico | Descrizione  
---|---|---  
Indian - Accounting | `l10n_in` | [Pacchetto localizzazione fiscale predefinito](../fiscal_localizations.html#fiscal-localizations-packages)  
Indian E-invoicing | `l10n_in_edi` | Indian e-invoicing integration  
Indian E-waybill | `l10n_in_edi_ewaybill` | Indian E-way bill integration  
Indian E-waybill Stock | `l10n_in_ewaybill_stock` | E-waybill creation from the Inventory app  
Indian - GSTR India eFiling | `l10n_in_reports_gstr` | Indian GST Return filing  
Indian - Accounting Reports | `l10n_in_reports` | Indian tax reports  
  
## e-Invoice system¶

Odoo is compliant with the **Indian Goods and Services Tax (GST) e-Invoice system** requirements.

### Imposta¶

#### NIC e-Invoice registration¶

You must register on the NIC e-Invoice portal to get your **API credentials**. You need these credentials to configure your Odoo Accounting app.

  1. Log in to the [NIC e-Invoice portal](https://einvoice1.gst.gov.in/) by clicking Login and entering your Username and Password;

Nota

If you are already registered on the NIC portal, you can use the same login credentials.

  2. From the dashboard, go to API Registration ‣ User Credentials ‣ Create API User;

  3. After that, you should receive an OTP code on your registered mobile number. Enter the OTP code and click Verify OTP;

  4. Select Through GSP for the API interface, set Tera Software Limited as GSP, and type in a Username and Password for your API. Once it is done, click Submit.




#### Configuration in Odoo¶

To enable the e-Invoice service in Odoo, go to Accounting ‣ Configuration ‣ Settings ‣ Indian Electronic Invoicing, and enter the Username and Password previously set for the API.

##### Registri¶

To automatically send e-Invoices to the NIC e-Invoice portal, you must first configure your _sales_ journal by going to Accounting ‣ Configuration ‣ Journals, opening your _sales_ journal, and in the Advanced Settings tab, under Electronic Data Interchange, enable E-Invoice (IN) and save.

### Flusso di lavoro¶

#### Invoice validation¶

Once an invoice is validated, a confirmation message is displayed at the top. Odoo automatically uploads the JSON-signed file of validated invoices to the NIC e-Invoice portal after some time. If you want to process the invoice immediately, click Process now.

Nota

  * You can find the JSON-signed file in the attached files in the chatter.

  * You can check the document’s EDI status under the EDI Document tab or the Electronic invoicing field of the invoice.




#### Invoice PDF report¶

Once an invoice is validated and submitted, the invoice PDF report can be printed. The report includes the IRN, Ack. No (acknowledgment number) and Ack. Date (acknowledgment date), and QR code. These certify that the invoice is a valid fiscal document.

#### e-Invoice cancellation¶

If you want to cancel an e-Invoice, go to the Other info tab of the invoice and fill out the Cancel reason and Cancel remarks fields. Then, click Request EDI cancellation. The status of the Electronic invoicing field changes to To Cancel.

Importante

Doing so cancels both the e-Invoice and the E-Way bill.

Nota

  * If you want to abort the cancellation before processing the invoice, then click Call Off EDI Cancellation.

  * Once you request to cancel the e-Invoice, Odoo automatically submits the JSON-signed file to the NIC e-Invoice portal. You can click Process now if you want to process the invoice immediately.




#### GST e-Invoice verification¶

After submitting an e-Invoice, you can verify if the invoice is signed from the GST e-Invoice system website itself.

  1. Download the JSON file from the attached files. It can be found in the chatter of the related invoice;

  2. Open the [NIC e-Invoice portal](https://einvoice1.gst.gov.in/) and go to Search ‣ Verify Signed Invoice;

  3. Select the JSON file and submit it;

If the file is signed, a confirmation message is displayed.




## E-Way bill¶

### Imposta¶

Odoo is compliant with the **Indian Goods and Services Tax (GST) E-waybill system** requirements.

#### API registration on NIC E-Way bill¶

You must register on the NIC E-Way bill portal to create your **API credentials**. You need these credentials to configure your Odoo Accounting app.

  1. Log in to the [NIC E-Way bill portal](https://ewaybillgst.gov.in/) by clicking Login and entering your Username and Password;

  2. From your dashboard, go to Registration ‣ For GSP;

  3. Click Send OTP. Once you have received the code on your registered mobile number, enter it and click Verify OTP;

  4. Check if Tera Software Limited is already on the registered GSP/ERP list. If so, use the username and password used to log in to the NIC portal. Otherwise, follow the next steps;

  5. Select Add/New, select Tera Software Limited as your GSP Name, create a Username and a Password for your API, and click Add.




#### Configuration in Odoo¶

To set up the E-Way bill service, go to Accounting ‣ Configuration ‣ Settings ‣ Indian Electronic WayBill ‣ Setup E-Way bill, and enter your Username and Password.

### Flusso di lavoro¶

#### Send an E-Way bill¶

To send an E-Way bill, confirm the customer invoice/vendor bill and click Send E-Way bill.

#### Invoice validation¶

Once an invoice/bill has been issued and sent via Send E-Way bill, a confirmation message is displayed.

Nota

  * You can find the JSON-signed file in the attached files in the chatter.

  * Odoo automatically uploads the JSON-signed file to the government portal after some time. Click Process now if you want to process the invoice/bill immediately.




#### Invoice PDF report¶

You can print the invoice PDF report once you have submitted the E-Way bill. The report includes the **E-Way bill number** and the **E-Way bill validity date**.

#### E-Way bill cancellation¶

If you want to cancel an E-Way bill, go to the E-Way bill tab of the related invoice/bill and fill out the Cancel reason and Cancel remarks fields. Then, click Request EDI Cancellation.

Importante

Doing so cancels both the e-Invoice (if applicable) and the E-Way bill.

Nota

  * If you want to abort the cancellation before processing the invoice, click Call Off EDI Cancellation.

  * Once you request to cancel the E-Way bill, Odoo automatically submits the JSON-signed file to the government portal. You can click Process Now if you want to process the invoice immediately.




### E-waybill creation from receipts and delivery orders¶

Nota

Make sure the **E-Way bill Stock** module is [installed](../../general/apps_modules.html#general-install) and the E-Way bill setup is complete.

To create E-Way bills from [receipts and deliveries](../../inventory_and_mrp/inventory/shipping_receiving/daily_operations.html) in the Inventory app, follow these steps:

  1. Go to Inventory ‣ Operations ‣ Deliveries or Inventory ‣ Operations ‣ Receipts and select an existing delivery order/receipt or create a new one.

  2. Click Create E-waybill/Challan.

Nota

To create an E-way bill:

     * A delivery order must be in the Done state (i.e., validated)

     * A receipt must have the Ready or Done state.

  3. Click Generate e-Waybill to validate the E-Way bill and send it to the NIC E-Way bill portal.

Suggerimento

To use the E-Way bill as a challan for goods deliveries without sending it to the NIC E-Waybill portal, click Use as Challan.




To print the E-waybill or the challan, click the __(gear) icon and select __ Ewaybill / Delivery Challan.

## Indian GST Return filing¶

### Enable API access¶

To file GST Returns in Odoo, you must first enable API access on the GST portal.

  1. Log into the [GST portal](https://services.gst.gov.in/services/login) by entering your Username and Password, and go to My Profile on your **profile menu** ;

  2. Select Manage API Access, and click Yes to enable API access;




Nota

It is recommended to set the Duration to 30 days to avoid the need for frequent token reauthentication.

  1. Doing so enables a Duration drop-down menu. Select the Duration of your preference, and click Confirm.




### Indian GST Service In Odoo¶

Once you have enabled the API access on the GST portal, you can set up the Indian GST Service in Odoo.

Go to Accounting ‣ Configuration ‣ Settings ‣ Indian GST Service and enter the GST Username. Click Send OTP, enter the code, and finally, Validate.

> ### File-in GST Return¶

When the Indian GST Service is configured, you can file your GST return. Go to Accounting ‣ Reporting ‣ India ‣ GST Return periods and create a new **GST Return Period** if it does not exist. GST Return file-in is done in **three steps** in Odoo:

Nota

**Tax Return Periodicity** can be [configured](../accounting/reporting/tax_returns.html) according to the user’s needs.

#### Send GSTR-1¶

  1. The user can verify the GSTR-1 report before uploading it to the **GST portal** by clicking GSTR-1 Report;

  2. The user can also get details to be submitted in **GSTR-1** in **Spreadsheet view** by clicking on Generate;

  3. If the **GSTR-1** report is correct, then click Push to GSTN to send it to the **GST portal**. The status of the GSTR-1 report changes to Sending;

  4. After a few seconds, the status of the **GSTR-1** report changes to Waiting for Status. It means that the **GSTR-1** report has been sent to the GST Portal and is being verified on the GST Portal;

  5. Once more, after a few seconds, the status either changes to Sent or Error in Invoice. The status Error in Invoice indicates that some of the invoices are not correctly filled out to be validated by the **GST portal** ;

     * If the state of the **GSTR-1** is Sent, it means your **GSTR-1** report is ready to be filed on the **GST portal**.

     * If the state of the **GSTR-1** is Error in Invoice, invoices can be checked for errors in the Log Note. Once issues have been resolved, the user can click Push to GSTN to submit the file again on the **GST portal**.

  6. Click Mark as Filed after filing the **GSTR-1** report on the **GST portal**. The status of the report changes to Filed in **Odoo**.




#### Receive GSTR-2B¶

Users can retrieve the **GSTR-2B Report** from the **GST portal**. This automatically reconciles the **GSTR-2B** report with your Odoo bills;

  1. Click Fetch GSTR-2B Summary to retrieve the **GSTR-2B** summary. After a few seconds, the status of the report changes to Waiting for Reception. This means Odoo is trying to receive the **GSTR-2B** report from the **GST portal** ;

  2. Once more, after a few seconds, the status of the **GSTR-2B** changes to the Being Processed. It means Odoo is reconciling the **GSTR-2B** report with your Odoo bills;

  3. Once it is done, the status of the **GSTR-2B** report changes to either Matched or Partially Matched;

     * If the status is Matched:

>      * If the status is Partially Matched, you can make changes in bills by clicking View Reconciled Bills. Once it is done, click re-match.

> 


#### GSTR-3 report¶

The GSTR-3 report is a monthly summary of **sales** and **purchases**. This return is auto-generated by extracting information from **GSTR-1** and **GSTR-2**.

  1. Users can compare the **GSTR-3** report with the **GSTR-3** report available on the **GST portal** to verify if they match by clicking GSTR-3 Report;

  2. Once the **GSTR-3** report has been verified by the user and the tax amount on the **GST portal** has been paid. Once paid, the report can be **closed** by clicking Closing Entry;

  3. In Closing Entry, add the tax amount paid on the **GST portal** using challan, and click POST to post the Closing Entry;

  4. Once posted, the **GSTR-3** report status changes to Filed.




## Tax reports¶

### GSTR-1 report¶

The GSTR-1 report is divided into sections. It displays the Base amount, CGST, SGST, IGST, and CESS for each section.

> ### GSTR-3 report¶

The GSTR-3 report contains different sections:

  * Details of inward and outward supply subject to a **reverse charge** ;

  * Eligible ITC;

  * Values of **exempt** , **Nil-rated** , and **non-GST** inward supply;

  * Details of inter-state supplies made to **unregistered** persons.

> 


[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/fiscal_localizations/india.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](indonesia.html "Indonesia") |
  * [precedente](hong_kong.html "Hong Kong") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * India


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