# Self-signed certificate for ePOS printers — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../employee_login.html "Multi-employee management") |
  * [precedente](https.html "Secure connection \(HTTPS\)") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Punto vendita](../../point_of_sale.html) »
  * [Configurazione](../configuration.html) »
  * Self-signed certificate for ePOS printers



# Self-signed certificate for ePOS printers¶

To work with Odoo, some printer models that can be used without an [IoT system](../../../general/iot.html) may require [the HTTPS protocol](https.html) to establish a secure connection between the browser and the printer. However, trying to reach the printer’s IP address using HTTPS leads to a warning page on most web browsers. In that case, you can temporarily force the connection, which allows you to reach the page in HTTPS and use the ePOS printer in Odoo as long as the browser window stays open.

Avvertimento

The connection is lost after closing the browser window. Therefore, this method should only be used as a **workaround** or as a pre-requisite for the following instructions.

## Generate, export, and import self-signed certificates¶

For a long-term solution, you must generate a **self-signed certificate**. Then, export and import it into your browser.

Importante

**Generating** an SSL certificate should only be done **once**. If you create another certificate, devices using the previous one will lose HTTPS access.

Windows 10 & Linux OSMac OSAndroid OSiOS

Generate a self-signed certificateExport a self-signed certificateImport a self-signed certificate

Navigate to the ePOS” IP address (e.g., `https://192.168.1.25`) and force the connection by clicking Advanced and Proceed to [IP address] (unsafe).

Warning page on Google Chrome, Windows 10¶

Then, sign in using your printer credentials to access the ePOS printer settings. To sign in, enter `epson` in the ID field and your printer serial number in the Password field.

Click Certificate List in the Authentication section, and click create to generate a new **Self-Signed Certificate**. The Common Name should be automatically filled out. If not, fill it in with the printer IP address number. Select the years the certificate will be valid in the Validity Period field, click Create, and Reset or manually restart the printer.

The self-signed certificate is generated. Reload the page and click SSL/TLS in the Security section to ensure **Selfsigned Certificate** is correctly selected in the Server Certificate section.

The export process is heavily dependent on the OS and the browser. Start by accessing your ePOS printer settings on your web browser by navigating to its IP address (e.g., `https://192.168.1.25`). Then, force the connection as explained in the **Generate a self-signed certificate tab**.

If you are using **Google Chrome** ,

  1. click Not secure next to the search bar, and Certificate is not valid;

  2. go to the Details tab and click Export;

  3. add `.crt` at the end of the file name to ensure it has the correct extension;

  4. select Base64-encoded ASCII, single certificate, at the bottom of the pop-up window;

  5. save, and the certificate is exported.




Avvertimento

Make sure that the certificate ends with the extension `.crt`. Otherwise, some browsers might not see the file during the import process.

If you are using **Mozilla Firefox** ,

  1. click the **lock-shaped** icon on the left of the address bar;

  2. go to Connection not secure ‣ More information ‣ Security tab ‣ View certificate;




  1. scroll down to the Miscellaneous section;

  2. click PEM (cert) in the Download section;

  3. save, and the certificate is exported.




The import process is heavily dependent on the OS and the browser.

Windows 10Linux

Windows 10 manages certificates, which means that self-signed certificates must be imported from the certification file rather than the browser. To do so,

  1. open the Windows File Explorer and locate the downloaded certification file;

  2. right-click on the certification file and click Install Certificate;

  3. select where to install the certificate and for whom - either for the Current User or all users (Local Machine). Then, click Next;

  4. on the `Certificate Store` screen, tick Place all certificates in the following store, click Browse…, and select Trusted Root Certification Authorities;

  5. click Finish, accept the pop-up security window;

  6. restart the computer to make sure that the changes are applied.




If you are using **Google Chrome** ,

  1. open Chrome;

  2. go to Settings ‣ Privacy and security ‣ Security ‣ Manage certificates;

  3. go to the Authorities tab, click Import, and select the exported certification file;

  4. accept all warnings;

  5. click ok;

  6. restart your browser.




If you are using **Mozilla Firefox** ,

  1. open Firefox;

  2. go to Settings ‣ Privacy & Security ‣ Security ‣ View Certificates… ‣ Import;

  3. select the exported certification file;

  4. tick the checkboxes and validate;

  5. restart your browser.




On Mac OS, you can secure the connection for all browsers by following these steps:

  1. open Safari and navigate to your printer’s IP address. Doing so leads to a warning page;

  2. on the warning page, go to Show Details ‣ visit this website ‣ Visit Website, validate;

  3. reboot the printer so you can use it with any other browser.




To generate and export an SSL certificate and send it to IOS devices, open **Google Chrome** or **Mozilla Firefox**. Then,

Generate a self-signed certificateExport a self-signed certificate

Navigate to the ePOS” IP address (e.g., `https://192.168.1.25`) and force the connection by clicking Advanced and Proceed to [IP address] (unsafe).

Warning page on Google Chrome, Windows 10¶

Then, sign in using your printer credentials to access the ePOS printer settings. To sign in, enter `epson` in the ID field and your printer serial number in the Password field.

Click Certificate List in the Authentication section, and click create to generate a new **Self-Signed Certificate**. The Common Name should be automatically filled out. If not, fill it in with the printer IP address number. Select the years the certificate will be valid in the Validity Period field, click Create, and Reset or manually restart the printer.

The self-signed certificate is generated. Reload the page and click SSL/TLS in the Security section to ensure **Selfsigned Certificate** is correctly selected in the Server Certificate section.

The export process is heavily dependent on the OS and the browser. Start by accessing your ePOS printer settings on your web browser by navigating to its IP address (e.g., `https://192.168.1.25`). Then, force the connection as explained in the **Generate a self-signed certificate tab**.

If you are using **Google Chrome** ,

  1. click Not secure next to the search bar, and Certificate is not valid;

  2. go to the Details tab and click Export;

  3. add `.crt` at the end of the file name to ensure it has the correct extension;

  4. select Base64-encoded ASCII, single certificate, at the bottom of the pop-up window;

  5. save, and the certificate is exported.




Avvertimento

Make sure that the certificate ends with the extension `.crt`. Otherwise, some browsers might not find the file during the import process.

If you are using **Mozilla Firefox** ,

  1. click the **lock-shaped** icon on the left of the address bar;

  2. go to Connection not secure ‣ More information ‣ Security tab ‣ View certificate;

  3. scroll down to the Miscellaneous section;

  4. click PEM (cert) in the Download section;

  5. save, and the certificate is exported.




To import an SSL certificate into an Android device, first create and export it from a computer. Next, transfer the `.crt` file to the device using email, Bluetooth, or USB. Once the file is on the device,

  1. open the settings and search for `certificate`;

  2. click Certificate AC (Install from device storage);

  3. select the certificate file to install it on the device.




Nota

The specific steps for installing a certificate may vary depending on the version of Android and the device manufacturer.

To import an SSL certificate into an iOS device, first create and export it from a computer. Then, transfer the `.crt` file to the device using email, Bluetooth, or any file-sharing service.

Downloading this file triggers a warning pop-up window. Click Allow to download the configuration profile, and close the second pop-up window. Then,

  1. go to the **Settings App** on the iOS device;

  2. click Profile Downloaded under the user’s details box;

  3. locate the downloaded `.crt` file and select it;

  4. click Install on the top right of the screen;

  5. if a passcode is set on the device, enter the passcode;

  6. click Install on the top right of the certificate warning screen and the pop-up window;

  7. click Done.




The certificate is installed, but it still needs to be authenticated. To do so,

  1. go to Settings ‣ General ‣ About > Certificate Trust Settings;

  2. enable the installed certificate using the **slide button** ;

  3. click Continue on the pop-up window.




Importante

  * If you need to export SSL certificates from an operating system or web browser that has not been mentioned, search for `export SSL certificate` \+ `the name of your browser or operating system` in your preferred search engine.

  * Similarly, to import SSL certificates from an unmentioned OS or browser, search for `import SSL certificate root authority` \+ `the name of your browser or operating system` in your preferred search engine.




## Check if the certificate was imported correctly¶

To confirm your printer’s connection is secure, connect to its IP address using HTTPS. For example, navigate to `https://192.168.1.25` in your browser. If the SSL certificate has been applied correctly, you should no longer see a warning page, and the address bar should display a padlock icon, indicating that the connection is secure.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/sales/point_of_sale/configuration/epos_ssc.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../employee_login.html "Multi-employee management") |
  * [precedente](https.html "Secure connection \(HTTPS\)") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Punto vendita](../../point_of_sale.html) »
  * [Configurazione](../configuration.html) »
  * Self-signed certificate for ePOS printers


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-App Purchase
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