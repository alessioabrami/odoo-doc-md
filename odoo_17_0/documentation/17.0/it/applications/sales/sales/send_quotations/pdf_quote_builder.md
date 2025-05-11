# Creazione preventivi in PDF — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../invoicing.html "Invoicing Method") |
  * [precedente](orders_and_variants.html "Varianti prodotto su preventivi e ordini di vendita") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Send Quotations](../send_quotations.html) »
  * Creazione preventivi in PDF



# Creazione preventivi in PDF¶

Il _Creatore di preventivi PDF_ di Odoo _Vendite_ offre l’opportunità di inviare ai clienti un file PDF completamente personalizzato per i preventivi, mostrando l’azienda e i prodotti, varie informazioni ed elementi di design, invece di mostrare solo il prezzo e il totale.

The PDF Quote Builder groups header pages, product descriptions, the price(s), and footer pages to create a detailed quote. It can also inject dynamic texts in the PDF to personalize the offer for the customer.

La presenza di un PDF personalizzato nei preventivi offre ai clienti un’esperienza di acquisto migliore e aggiunge un elegante livello di professionalità all’azienda.

Vedi anche

[Odoo Quick Tips - Creare un preventivo in PDF [video]](https://www.youtube.com/watch?v=tQNydBZt-VI)

Nota

Si consiglia di modificare i moduli PDF con il software Adobe. I campi del modulo nei modelli PDF di intestazione e piè di pagina sono necessari per ottenere valori dinamici con Odoo.

## Configurazione¶

Per aggiungere file PDF personalizzati per i preventivi, è **necessario** configurare la funzione Creazione preventivi PDF.

Per farlo, vai su Vendite ‣ Configurazione ‣ Impostazioni. In seguito, nella pagina Impostazioni, scorri fino alla sezione Preventivi e ordini e individua la funzione Creazione preventivi PDF.

Here, custom Header pages and Footer pages can be uploaded. To upload either, click the Upload your file button, or the ✏️ (pencil) icon to the right of the desired field, and proceed to locate, select, and upload the desired PDF file.

Nota

Headers and footers can also be added directly in a quotation template, so it’s possible to have different variations per template.

Clicking the 🗑️ (trash) icon deletes the current PDF file and replaces the blank field with an Upload your file button.

Once the desired PDF file(s) are uploaded in the appropriate fields in the PDF Quote builder section of the _Sales_ Settings page, be sure to click Save.

The files uploaded here will be the default PDF used for all quotes.

Nota

Values set in the PDF Quote Builder settings are company-specific.

## Testo dinamico nei PDF¶

Durante la creazione di PDF personalizzati per i preventivi, utilizza _testi dinamici_ per Odoo per riempire automaticamente il contenuto del PDF con informazioni relative al preventivo dal database di Odoo, come nomi, prezzi, ecc.

I valori di testi dinamici sono componenti del modulo (input di testo) che possono essere aggiunti in un file PDF e che Odoo riempie automaticamente con le informazioni relative al preventivo.

### Valori testo dinamico¶

Below are common dynamic text values used in custom PDFs, and what they represent:

  * name: Riferimento ordine di vendita

  * partner_id__name: Nome cliente

  * user_id__name: Nome addetto vendite

  * amount_untaxed: Importo imponibile

  * amount_total: Importo totale

  * delivery_date: Data di consegna

  * validity_date: Data di scadenza

  * client_order_ref: Riferimento cliente




Nota

Double underscore notation for partner_id__name and user_id__name values are used in place of the typically used `.` symbol because the library currently does not support the `.` symbol.

Product-specific dynamic text values are as follows:

  * description: Descrizione prodotto

  * quantity: Quantità

  * uom: Unità di misura (UdM)

  * price_unit: Unità di prezzo

  * discount: Sconto

  * product_sale_price: Prezzo di listino del prodotto

  * taxes: Nomi imposte uniti da virgola (`,`)

  * tax_excl_price: Prezzo tasse escluse

  * tax_incl_price: Prezzo tasse incluse




Example

When a PDF is built, it’s best practice to use common dynamic text values (name and partner_id_name). When uploaded into the database, Odoo auto-populates those fields with the information from their respective fields.

In this case, Odoo would auto-populate the Sales Order Reference in the name dynamic text field, and the Customer Name in the partner_id_name field.

Once the PDF file(s) are complete, save them to the computer’s hard drive, and proceed to upload them to Odoo via Sales app ‣ Configuration ‣ Settings ‣ PDF Quote builder.

Upload the created PDF in the Header pages or Footer pages field.

Once the upload(s) are complete, click Save.

## Add PDF to product¶

In Odoo _Sales_ , it’s also possible to add a custom PDF to a product form. When a PDF is added to a product, and that product is used in a quotation, that PDF is also inserted in the final PDF.

To add a custom PDF to a product, start by navigating to Sales app ‣ Products ‣ Products, and select the desired product to which a custom PDF should be added.

Nota

A document could also be added to a product variant, instead of a product. If there are documents on a product _and_ on its variant, **only** the documents in the variant are shown.

To add a custom document to a product variant, navigate to Sales app ‣ Products ‣ Product Variants. Select the desired variant, click the Documents smart button, and proceed to upload the custom document(s) to the specific product variant.

On the product page, click the Documents smart button at the top of the page.

Doing so reveals a separate Documents page for that product, wherein files related to that product can be uploaded. From this page, either click New or Upload.

Clicking Upload instantly provides the opportunity to upload the desired document. Then, the document can be further configured on the document card, or by clicking the three dots icon in the top right corner of the document card, and then clicking Edit.

Se fai clic su Nuovo si apre un modulo documenti vuoto, in cui è possibile caricare il PDF desiderato tramite il pulsante Carica il tuo file, situato nel campo Contenuto file.

Qui si possono modificare varie informazioni e configurazioni relative al documento caricato.

Il primo campo del modulo documenti è per il Nome del documento ed è in grigio (non cliccabile) finché non viene caricato un documento. Una volta caricato un PDF, il campo Nome viene popolato automaticamente con il nome del PDF e può essere modificato.

Prior to uploading a document, there’s the option to designate whether the document is a File or URL from the Type drop-down field menu.

Nota

If a PDF is uploaded, the Type field is auto-populated to File, and it cannot be modified.

Then, in the Sales section, in the Visible at field, click the drop-down menu, and select either: Quotation, Confirmed order, or Inside quote.

  * Quotation: the document is sent to (and accessible by) customers at any time.

  * Confirmed order: the document is sent to customers upon the confirmation of an order. This is best for user manuals and other supplemental documents.

  * Inside quote: the document is included in the PDF of the quotation, between the header pages and the Pricing section of the quote.




Example

When the Inside quote option for the Visible at field is chosen, and the custom PDF file, `Sample Builder.pdf` is uploaded, the PDF is visible on the quotation the in the _customer portal_ under the Documents field.

> Lastly, in the E-Commerce section, decide whether or not to Show on product page on the front-end (in the online store).

Example

When the Show on product page option is enabled, a link to the uploaded document, `Sample Builder.pdf`, appears on the product’s page, located on the frontend in the online store.

It appears beneath a Documents heading, with a link showcasing the name of the uploaded document.

> ## PDF quote¶

Once a quote with a pre-configured PDF has been confirmed, Odoo provides the option to print the confirmed quote to check for errors, or to keep for records.

To print the PDF quote, navigate to the confirmed quote, and click the ⚙️ (gear) icon to reveal a drop-down menu. From this drop-down menu, select Print, then select PDF Quote.

Doing so instantly downloads the PDF quote. When opened, the PDF quote, along with the configured product PDF that was set to be visible inside the quote, can be viewed and printed.

Nota

Download these [`PDF quote builder examples`](../../../../_downloads/5f0840ed187116c425fdac2ab4b592e1/pdfquotebuilderexamples.zip) for added reference.

Vedi anche

  * [Modelli preventivo](quote_template.html)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/sales/send_quotations/pdf_quote_builder.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../invoicing.html "Invoicing Method") |
  * [precedente](orders_and_variants.html "Varianti prodotto su preventivi e ordini di vendita") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Send Quotations](../send_quotations.html) »
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
  *[FBM]: Fulfilled By Merchant
  *[FBA]: Fulfilled by Amazon
  *[API]: Application Programming Interface