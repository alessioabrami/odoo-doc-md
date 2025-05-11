# Creazione preventivi in PDF — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../invoicing.html "Invoicing Method") |
  * [precedente](orders_and_variants.html "Varianti prodotto su preventivi e ordini di vendita") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Preventivi di vendita](../sales_quotations.html) »
  * Creazione preventivi in PDF



# Creazione preventivi in PDF¶

Il _Creatore di preventivi PDF_ di Odoo _Vendite_ offre l’opportunità di inviare ai clienti un file PDF completamente personalizzato per i preventivi, mostrando l’azienda e i prodotti, varie informazioni ed elementi di design, invece di mostrare solo il prezzo e il totale.

Il Creatore di preventivi PDF raggruppa le pagine di intestazione, le descrizioni dei prodotti, i prezzi e i piè di pagina per creare preventivI dettagliatI. Inoltre, è possibile inserire nel PDF testi dinamici o note personalizzate per personalizzare l’offerta.

La presenza di un PDF personalizzato nei preventivi offre ai clienti un’esperienza di acquisto migliore e aggiunge un elegante livello di professionalità all’azienda.

Vedi anche

[Odoo Quick Tips - Creare un preventivo in PDF [video]](https://www.youtube.com/watch?v=tQNydBZt-VI)

Nota

Si consiglia di modificare i moduli PDF con il software Adobe. I campi del modulo nei modelli PDF di intestazione e piè di pagina sono necessari per ottenere valori dinamici con Odoo.

## Configurazione¶

Per aggiungere file PDF personalizzati per i preventivi, è **necessario** configurare la funzione Creazione preventivi PDF.

Per farlo, vai su Vendite ‣ Configurazione ‣ Impostazioni. In seguito, nella pagina Impostazioni, scorri fino alla sezione Preventivi e ordini e individua la funzione Creazione preventivi PDF.

## Aggiungere un PDF come intestazione/piè di pagina¶

In Odoo _Vendite_ è possibile aggiungere un PDF personalizzato che può essere utilizzato come intestazione o piè di pagina. Al momento dell’attivazione del creatore di preventivi in PDF, è possibile selezionare il numero di intestazioni e piè di pagina che si desidera utilizzare. I PDF verranno poi inseriti anche nel PDF finale.

Per aggiungere un PDF personalizzato come intestazione o piè di pagina. apri l’app Vendite ‣ Configurazione ‣ Intestazioni/Piè di pagina. Da qui, fai clic su Nuovo o Carica.

Facendo clic su Carica hai immediatamente la possibilità di caricare il documento desiderato. In seguito, il documento può essere ulteriormente configurato nella relativa scheda, oppure facendo clic sull’icona __(ellissi verticale) nell’angolo in alto a destra della scheda del documento per poi fare clic su Modifica.

Se fai clic su Nuovo si apre un modulo documenti vuoto, in cui è possibile caricare il PDF desiderato tramite il pulsante Carica il tuo file, situato nel campo Contenuto file.

Qui si possono modificare varie informazioni e configurazioni relative al documento caricato.

Il primo campo del modulo documenti è per il Nome del documento ed è in grigio (non cliccabile) finché non viene caricato un documento. Una volta caricato un PDF, il campo Nome viene popolato automaticamente con il nome del PDF e può essere modificato.

Successivamente, nel campo Tipo documento, fai clic sul menu a tendina e seleziona Intestazione o Piè di pagina per definire se questi file devono essere selezionabili all’inizio o alla fine del preventivo.

Nella sezione Modelli preventivo, questo PDF può essere limitato ai soli modelli di preventivo.

Nota

In alternativa, si può anche andare su Vendite ‣ Configurazione ‣ Modelli di preventivo, seleziona un modello e Aggiungi o Carica direttamente un PDF nella scheda Creazione preventivo.

Infine, oltre al campo Contenuto file, si ha la possibilità di configurare campi dinamici.

## Testo dinamico nei PDF¶

Durante la creazione di PDF personalizzati per i preventivi, utilizza _testi dinamici_ per Odoo per riempire automaticamente il contenuto del PDF con informazioni relative al preventivo dal database di Odoo, come nomi, prezzi, ecc.

I valori di testi dinamici sono componenti del modulo (input di testo) che possono essere aggiunti in un file PDF e che Odoo riempie automaticamente con le informazioni relative al preventivo.

### Valori testo dinamico¶

Di seguito sono riportati i valori di testo dinamico più comuni utilizzati nei PDF personalizzati, già mappati nei campi corretti, e ciò che rappresentano.

Per intestazioni e piè di pagina:

  * name: Riferimento ordine di vendita

  * partner_id__name: Nome cliente

  * user_id__name: Nome addetto vendite

  * amount_untaxed: Importo imponibile

  * amount_total: Importo totale

  * delivery_date: Data di consegna

  * validity_date: Data di scadenza

  * client_order_ref: Riferimento cliente




Per PDF di prodotti:

  * description: Descrizione prodotto

  * quantity: Quantità

  * uom: Unità di misura (UdM)

  * price_unit: Unità di prezzo

  * discount: Sconto

  * product_sale_price: Prezzo di listino del prodotto

  * taxes: Nomi imposte uniti da virgola (`,`)

  * tax_excl_price: Prezzo tasse escluse

  * tax_incl_price: Prezzo tasse incluse




Dopo aver caricato un PDF, è possibile Configurare campi dinamici. Ciò consente di mappare qualsiasi nome di campo trovato nel PDF al campo che si desidera mostrare, annotando qualsiasi percorso esistente. Le intestazioni e i piè di pagina partono dal modello sale_order corrente, mentre i documenti del prodotto seguono il percorso sale_order_line. Lasciare questo percorso vuoto consente di inserire note personalizzate, direttamente dal preventivo specifico che le richiede.

Example

When a PDF is built, it’s best practice to use common dynamic text values (name and partner_id_name). When uploaded into the database, Odoo auto-populates those fields with the information from their respective fields.

In this case, Odoo would auto-populate the Sales Order Reference in the name dynamic text field, and the Customer Name in the partner_id_name field.

Once the PDF file(s) are complete, save them to the computer’s hard drive, and proceed to upload them to Odoo via Sales app ‣ Configuration ‣ Headers/Footers.

Example

When uploading PDF containing the form field invoice_partner_country, which is an information available in the sales order, configure the path of the Form Field Name to: \- partner_invoice_id.country_id.name for a header or footer document \- order_id.partner_invoice_id.country_id.name for a product document fills the form with the invoice partner country’s name when the PDF is built.

Example

When uploading any PDF containing the form field custom_note, leaving the path empty allows the seller to write down any note where that form field is in that document and shown when the PDF is built.

## Add PDF to product¶

In Odoo _Sales_ , it’s also possible to add a custom PDF to a product form. When a PDF is added to a product, and that product is used in a quotation, that PDF is also inserted in the final PDF.

To add a custom PDF to a product, start by navigating to Sales app ‣ Products ‣ Products, and select the desired product to add a custom PDF to.

Nota

A document could also be added to a product variant, instead of a product. If there are documents on a product _and_ on its variant, **only** the documents in the variant are shown.

To add a custom document to a product variant, navigate to Sales app ‣ Products ‣ Product Variants. Select the desired variant, click the Documents smart button, and proceed to upload the custom document to the specific product variant.

On the product page, click the Documents smart button at the top of the page to navigate to a Documents page for that product, where files related to that product can be uploaded. From this page, either click New or Upload.

Clicking Upload opens the computer’s local file directory. An uploaded document can be further configured on the document card, or by clicking the __(vertical ellipsis) icon in the top-right corner of the document card, and then clicking Edit.

Se fai clic su Nuovo si apre un modulo documenti vuoto, in cui è possibile caricare il PDF desiderato tramite il pulsante Carica il tuo file, situato nel campo Contenuto file.

### PDF form configuration¶

Il primo campo del modulo documenti è per il Nome del documento ed è in grigio (non cliccabile) finché non viene caricato un documento. Una volta caricato un PDF, il campo Nome viene popolato automaticamente con il nome del PDF e può essere modificato.

Prior to uploading a document, there’s the option to designate whether the document is a File or URL from the Type drop-down field menu.

Nota

If a PDF is uploaded, the Type field is auto-populated to File, and it cannot be modified.

Then, in the Sales section, in the Visible at field, click the drop-down menu, and select either: On quotation, On confirmed order, or Inside quote pdf.

  * Quotation: the document is sent to (and accessible by) customers at any time.

  * Confirmed order: the document is sent to customers upon the confirmation of an order. This is best for user manuals and other supplemental documents.

  * Inside quote: the document is included in the PDF of the quotation, between the header pages and the Pricing section of the quote.




Example

When the Inside quote option for the Visible at field is chosen, and the custom PDF file, `Corner Desk.pdf` is uploaded, the PDF is visible on the quotation in the _customer portal_ under the Documents field.

> Beside the File Content field, you have the possibility to Configure dynamic fields. When doing so, remember that the starting model is the sale_order_line, unlike for headers and footers that start from the sale_order.

Lastly, in the E-Commerce section, decide whether or not to Publish on Website so that the PDF appears on the product page in the online store.

Example

When the Publish on Website option is enabled, a link to the uploaded document, `Corner Desk.pdf`, appears on the product’s page in the online store.

It appears beneath a Documents heading, with a link showcasing the name of the uploaded document.

> ## PDF quote¶

On a sales order, in the Quote Builder tab, select additional documents to be merged into the final PDF. If a selected document has custom fields, they appear as editable text boxes to be filled in.

Once a quote with a pre-configured PDF has been confirmed, Odoo provides the option to print the confirmed quote to check for errors, or to keep for records.

To print the PDF quote, navigate to the confirmed quote, and click the ⚙️ (gear) icon to reveal a drop-down menu. From this drop-down menu, select Print, then select PDF Quote.

Doing so instantly downloads the PDF quote. When opened, the PDF quote, along with the configured product PDF that was set to be visible inside the quote, can be viewed and printed.

Nota

Download these [`PDF quote builder examples`](../../../../_downloads/c2c6ce32294dfddffcfefcf2775f7a09/pdfquotebuilderexamples.zip) or download [`sample quotation`](../../../../_downloads/312a470653db882b08ad72eb30cb4088/sample_quotation.pdf) for added reference.

Vedi anche

  * [Modelli preventivo](quote_template.html)




[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/sales/sales/sales_quotations/pdf_quote_builder.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../invoicing.html "Invoicing Method") |
  * [precedente](orders_and_variants.html "Varianti prodotto su preventivi e ordini di vendita") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Preventivi di vendita](../sales_quotations.html) »
  * Creazione preventivi in PDF


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
  *[MRR]: monthly recurring revenue
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