# Cile — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](colombia.html "Colombia") |
  * [precedente](canada.html "Canada") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Cile



# Cile¶

Suggerimento

Watch the two webinar recordings below for a general presentation of the localization, and search the playlist for tutorials to discover practical workflows while using Odoo in Chile.

  * [Webinar: intro and demo](https://youtu.be/BHnByZiyYcM).

  * [Webinar: delivery guide](https://youtu.be/X7i4PftnEdU).

  * [Playlist of tutorials](https://youtube.com/playlist?list=PL1-aSABtP6AB6UY7VUFnVgeYOaz33fb4P).




Vedi anche

  * [Chilean localization app tour](https://www.youtube.com/watch?v=3qYkgbmBYHw)

  * [Chilean localization smart tutorial](https://www.odoo.com/slides/smart-tutorial-localizacion-de-chile-131)

  * [Documentation on e-invoicing’s legality and compliance in Chile](../accounting/customer_invoices/electronic_invoicing/chile.html)




## Moduli¶

[Install](../../general/apps_modules.html#general-install) the following modules to utilize all the features of the Chilean localization.

Nome | Nome tecnico | Descrizione  
---|---|---  
Chile - Accounting | `l10n_cl` | Adds the minimal accounting features required for a company to operate in Chile under the SII regulations and guidelines.  
Chile - Accounting Reports | `l10n_cl_reports` | Adds the _Propuesta F29_ and _Balance Tributario (8 columnas)_ reports.  
Chile - E-invoicing | `l10n_cl_edi` | Includes all technical and functional requirements to receive and generate **electronic receipts** and **invoices** online based on the SII regulations.  
Electronic Exports of Goods for Chile | `l10n_cl_edi_exports` | Includes technical and functional requirements to generate electronic invoices for exporting goods based on the SII and customs regulations.  
Chile - E-Invoicing Delivery Guide | `l10n_cl_edi_stock` | Includes all technical and functional requirements to generate delivery guides via web service based on the SII regulations.  
  
Nota

  * Odoo automatically installs the appropriate package for the company according to the country selected at the creation of the database.

  * The _Chile - E-Invoicing Delivery Guide_ module depends on the _Inventory_ application.




Importante

All features are only available if the company already completed the [SII Sistema de Facturación de Mercado](https://www.sii.cl/factura_electronica/factura_mercado/proceso_certificacion.htm) certification process.

## Informazioni aziendali¶

Navigate to Settings ‣ Companies: Update Info and ensure the following company information is up-to-date and correctly filled in:

  * Company Name

  * Address:

    * Street

    * City

    * State

    * ZIP

    * Country

  * Tax ID: enter the identification number for the selected Taxpayer Type.

  * Activity Names: select up to four activity codes.

  * Company Activity Description: enter a short description of the company’s activity.




## Accounting settings¶

Next, navigate to Accounting ‣ Configuration ‣ Settings ‣ Chilean Localization and follow the instructions to configure the:

  * Fiscal information

  * Electronic invoice data

  * DTE incoming email server

  * Signature certificates




### Fiscal information¶

Configure the following Tax payer information:

  * Taxpayer Type by selecting the taxpayer type that applies:

    * VAT Affected (1st Category): for invoices that charge taxes to customers

    * Fees Receipt Issuer (2nd Category): for suppliers who issue fees receipt (Boleta)

    * End consumer: only issues receipts

    * Foreigner

  * SII Office: select your company’s SII regional office




### Electronic invoice data¶

Select your SII Web Services environment:

  * SII - Test: for test databases using test CAFs obtained from the SII. In this mode, the direct connection flows can be tested, with the files being sent to the SII.

  * SII - Production: for production databases.

  * SII - Demo Mode: files are created and accepted automatically in demo mode but are **not** sent to the SII. For this reason, rejection errors or _Accepted with Objections_ will not appear in this mode. Every internal validation can be tested in demo mode. Avoid selecting this option in a production database.




Then, enter the Legal Electronic Invoicing Data:

  * SII Resolution N°

  * SII Resolution Date




## DTE incoming email server¶

The DTE Email Box Electronic Invoicing can be defined to receive your customers” claim and acceptance emails. Enabling this option from Accounting ‣ Configuration ‣ Settings ‣ Chilean Localization is necessary if you want to use _Email Box Electronic Invoicing_ as the DTE incoming email server.

Importante

In order to receive your SII documents, it’s necessary to set up your own email server. More information on how to do this can be found in this documentation: [Comunicazione in Odoo via e-mail](../../general/email_communication.html)

Begin by clicking Configure DTE Incoming Email, then click New to add a server and fill in the following fields:

  * Name: give the server a name.

  * Server Type: select the server type used.

    * IMAP Server

    * POP Server

    * Local Server: uses a local script to fetch emails and create new records. The script can be found in the Configuration section with this option selected.

    * Gmail OAuth Authentication: requires your Gmail API credentials to be configured in the general settings. A direct link to the configuration can be found in the Login Information section.

  * DTE Server: enable this option. By checking this option, this email account will be used to receive the electronic invoices from the suppliers, and communications from the SII regarding the electronic invoices issued. In this case, this email should match both emails declared on the SII site in the section: _ACTUALIZACION DE DATOS DEL CONTRIBUYENTE_ , _Mail Contacto SII_ and _Mail Contacto Empresas_.




In the Server & Login tab (for IMAP and POP servers):

  * Server Name: enter the hostname or IP of the server.

  * Port: enter the server port.

  * SSL/TLS: enable this option if connections are encrypted using the SSL/TLS protocol.

  * Username: enter the server login username.

  * Password: enter the server login password.




Suggerimento

Before going live, it is recommended to archive or remove all emails related to vendor bills that are not required to be processed in Odoo from your inbox.

### Certificato¶

A digital certificate in `.pfx` format is required to generate the electronic invoice signature. To add one, click Configure Signature Certificates under the Signature Certificates section. Then, click New to configure the certificate:

  * Certificate Key: click Upload your file and select the `.pfx` file.

  * Certificate Passkey: enter the file’s passphrase.

  * Subject Serial Number: depending on the certificate format, the field might not be automatically populated. In that case, enter the certificate’s legal representative RUT.

  * Certificate Owner: select one if you need to restrict the certificate for a specific user. Leave the field empty to share it with all billing users.




Avvertimento

If the Certificate Owner field is set to a specific user, and there are no certificates shared with users, then the automatic sending of electronic documents and receipt acknowledgments is **disabled**.

## Multicurrency¶

The official currency rate is provided by [Chilean mindicador.cl](https://mindicador.cl/). Navigate to Accounting ‣ Configuration ‣ Settings ‣ Currencies: Automatic Currency Rates to set an Interval for when the rate is automatically updated, or to select another Service.

## Partner information¶

Configuring partner contacts is also required to send SII electronic invoices. Open the Contacts app to do so and fill in the following fields on a new or existing contact form.

  * Nome

  * E-mail

  * Identification Number

  * Taxpayer Type

  * Activity Description




In the Electronic Invoicing tab:

  * DTE Email: enter the sender’s email address for the partner.

  * Delivery Guide Price: select which price the delivery guide displays, if any.




Nota

The DTE Email is the email used for sending electronic documents and must be set in the contact that will be part of an electronic document.

## Document types¶

Accounting documents are categorized by SII-defined document types.

Document types are created automatically upon installation of the localization module, and can be managed by navigating to Accounting ‣ Configuration ‣ Document Types.

Nota

Several document types are inactive by default but can be activated by toggling the Active option.

### Use on invoices¶

The document type on each transaction is determined by:

  * The journal related to the invoice, identifying if the journal uses documents.

  * The condition applied based on the type of issuer and recipient (e.g., the buyer or vendor’s fiscal regime).




## Registri¶

_Sales journals_ in Odoo usually represent a business unit or location.

Example

  * Ventas Santiago.

  * Ventas Valparaiso.




For retail stores it is common to have one journal per POS.

Example

  * Cashier 1.

  * Cashier 2.




The _purchase_ transactions can be managed with a single journal, but sometimes companies use more than one journal in order to handle some accounting transactions that are not related to vendor bills. This configuration can easily be set by using the following model.

Example

  * Tax payments to the government.

  * Employees payments.




### Create a sales journal¶

To create a sales journal, navigate to Accounting ‣ Configuration ‣ Journals. Then, click the New button, and fill in the following required information:

  * Type: select Sale from the drop-down menu for customer invoice journals.

  * Point of sale type: if the sales journal will be used for electronic documents, the option Online must be selected. Otherwise, if the journal is used for invoices imported from a previous system or if you are using the SII portal _Facturación MiPyme_ , you can use the option Manual.

  * Use Documents: check this field if the journal will use document types. This field is only applicable to purchase and sales journals that can be related to the different sets of document types available in Chile. By default, all the sales journals created will use documents.




Next, from the Jounal Entries tab, define the Default Income Account and Dedicated Credit Note Squence in the Accounting Information section. Configuring these fields is required for one of the debit notes use cases.

## CAF¶

A _folio authorization code_ (CAF) is required for each document type that will be issued electronically. The CAF is a file the SII provides to the issuer with the folios/sequences authorized for the electronic invoice documents.

Your company can request multiple folios and obtain several CAFs linked to different folio ranges. These CAFs are shared within all journals, so you only need one active CAF per document type, and it will be applied to all journals.

Please refer to the [SII documentation](https://palena.sii.cl/dte/mn_timbraje.html) to check the details on how to acquire the CAF files.

Importante

The CAFs required by the SII are different from production to test (certification mode). Make sure you have the correct CAF set depending on your environment.

### Upload CAF files¶

Once the CAF files have been acquired from the SII portal, they need to be uploaded in the database by navigating to Accounting ‣ Configuration: Chilean SII ‣ CAFs. Then, click the New begin the configuration. On the CAF form, upload your CAF file by clicking the Upload your file button and then click Save.

Once uploaded, the status changes to In Use. At this moment, when a transaction is used for this document type, the invoice number takes the first folio in the sequence.

Importante

The document types have to be active before uploading the CAF files. In case some folios have been used in the previous system, the next valid folio has to be set when the first transaction is created.

## Piano dei conti¶

The chart of accounts is installed by default as part of the data set included in the localization module. The accounts are mapped automatically in:

  * Imposte

  * Default Account Payable

  * Default Account Receivable

  * Conti trasferimento

  * Tasso di cambio




Vedi anche

[Piano dei conti](../accounting/get_started/chart_of_accounts.html)

## Imposte¶

As part of the localization module, taxes are created automatically with their related financial account and configuration. These taxes can be managed from Accounting ‣ Configuration ‣ Taxes.

Chile has several tax types, the most common ones are:

  * **VAT** : the regular VAT can have several rates.

  * **ILA** : the tax for alcoholic drinks.




Vedi anche

[Imposte](../accounting/taxes.html)

## Usage and testing¶

### Electronic invoice workflow¶

In the Chilean localization, the electronic invoice workflow includes customer invoice issuance and vendor bill reception. The following diagram explains how information is shared to the SII, customers, and vendors.

### Customer invoice emission¶

After the partners and journals are created and configured, the invoices are created in the standard way. For Chile, one of the differences is the document type that is automatically selected based on the taxpayer. The document type can be changed manually if needed on the invoice by navigating to Accounting ‣ Customers ‣ Invoices.

Importante

Documents type 33 electronic invoice must have at least one item with tax, otherwise the SII rejects the document validation.

#### Validation and DTE status¶

Once all invoice information is filled, either manually or automatically when generated from a sales order, validate the invoice. After the invoice is posted:

  * The DTE file is created automatically and recorded in the chatter.

  * The DTE SII status is set as Pending to be sent.




The DTE status is updated automatically by Odoo with a scheduled action that runs every day at night, if the response from the SII is needed immediately, you can do it manually as well by following the DTE status workflow:

  1. The first step is to send the DTE to the SII. This can be sent manually by clicking the Enviar Ahora button. This generates a SII Tack number for the invoice, which is used to check the details sent by the SII via email. Then, the DTE status is updated to Ask for Status.

  2. Once the SII response is received, Odoo updates the DTE status. To do it manually, click on the button Verify on SII. The result can either be Accepted, Accepted With Objection or Rejected.

Importante

There are intermediate statuses in the SII before acceptance or rejection. It’s recommended to **NOT** continuously click Verify in SII for smooth processing.

  3. The final response from the SII can take on one of these values:

     * Accepted: indicates the invoice information is correct, our document is now fiscally valid and it’s automatically sent to the customer.

     * Accepted with objections: indicates the invoice information is correct, but a minor issue was identified, nevertheless the document is now fiscally valid and it’s automatically sent to the customer.

     * Rejected: indicates the invoice information is incorrect and must be corrected. Details are sent to emails you registered in the SII. If it is properly configured in Odoo, the details are also retrieved in the chatter once the email server is processed.

If the invoice is rejected please follow these steps:

       1. Change the document to Draft.

       2. Make the required corrections based on the message received from the SII in the chatter.

       3. Post the invoice again.




#### Crossed references¶

When the invoice is created, as a result of another fiscal document, the information related to the originator document must be registered in the Cross-Reference tab. This tab is commonly used for credit or debit notes, however, in some cases it can be used for customer invoices, as well. In the case of the credit and debit notes, they are set automatically by Odoo.

#### Invoice PDF report¶

Once the invoice is accepted and validated by the SII and the PDF is printed, it includes the fiscal elements that indicate that the document is fiscally valid.

Importante

If you are hosted in Odoo SH or On-Premise, you should manually install the [pdf417gen](https://pypi.org/project/pdf417gen/) library. Use the following command to install it: **pip install pdf417gen**.

#### Commercial validation¶

Once the invoice has been sent to the customer:

  1. DTE Partner Status changes to Sent.

  2. The customer must send a reception confirmation email.

  3. Subsequently, if commercial terms and invoice data are correct, an acceptance confirmation is sent; otherwise, a claim is sent.

  4. The field DTE Acceptance Status is updated automatically.




#### Processed for claimed invoices¶

Once the invoice has been accepted by the SII, **it can not be cancelled in Odoo**. In case you get a claim for your customer, the correct way to proceed is with a credit note to either cancel the invoice or correct it. Please refer to the Credit notes section for more details.

#### Common errors¶

There are multiple reasons behind a rejection from the SII, but these are some of the common errors you might have and how to solve them:

  * **Error:** `RECHAZO- DTE Sin Comuna Origen`

**Hint:** make sure the company address is properly filled including the state and city.

  * **Error:** `en Monto - IVA debe declararse`

**Hint:** the invoice lines should include one VAT tax, make sure you add one on each invoice line.

  * **Error:** `Rut No Autorizado a Firmar`

**Hint:** the RUT entered is not allowed to invoice electronically, make sure the company RUT is correct and is valid in the SII to invoice electronically.

  * **Error:** `Fecha/Número Resolucion Invalido RECHAZO- CAF Vencido : (Firma_DTE[AAAA-MM-DD] - CAF[AAAA-MM-DD]) &gt; 6 meses`

**Hint:** try to add a new CAF related to this document as the one you’re using is expired.

  * **Error:** `Element '{http://www.sii.cl/SiiDte%7DRutReceptor': This element is not expected. Expected is ( {http://www.sii.cl/SiiDte%7DRutEnvia ).`

**Hint:** Make sure the field Document Type and VAT are set in the customer and in the main company.

  * **Error:** `Usuario sin permiso de envio.`

**Hint:** this error indicates that most likely, your company has not passed the [Certification process](https://www.sii.cl/factura_electronica/factura_mercado/proceso_certificacion.htm) in the SII \- Sistema de Facturación de Mercado. If this is the case, please contact your Account Manager or Customer Support as this certification is not part of the Odoo services, but we can give you some alternatives. If you already passed the certification process, this error appears when a user different from the owner of the certificate is trying to send DTE files to the SII.

  * **Error:** `CARATULA`

**Hint:** there are just five reasons why this error could show up and all of them are related to the _Caratula_ section of the XML:

>     * The company’s RUT number is incorrect or missing.
> 
>     * The certificate owner RUT number is incorrect or missing.
> 
>     * The SII’s RUT number (this should be correct by default) is incorrect or missing.
> 
>     * The resolution date is incorrect or missing.
> 
>     * The resolution number is incorrect or missing.




### Credit notes¶

When a cancellation or correction is needed over a validated invoice, a credit note must be generated. It is important to consider that a CAF file is required for the credit note, which is identified as Document Type 61 in the SII. Please refer to the CAF section for more information on the process to load the CAF on each document type.

#### Casi d’uso¶

##### Cancel referenced document¶

In case you need to cancel or invalidate an invoice, navigate to Accounting ‣ Customers ‣ Invoices and select the desired invoice. Then, use the button Add Credit Note and select Full Refund, in this case the SII reference code is automatically set to Anula Documento de referencia.

##### Correct referenced document¶

If a correction in the invoice information is required, for example the street name on the original invoice is wrong, then use the button Add Credit Note, select Partial Refund and select the option Only Text Correction. In this case the SII Reference Code field is automatically set to Corrects Referenced Document Text.

Odoo creates a credit note with the corrected text in an invoice and Price `0.00`.

Importante

Make sure to define the Default Credit Account in the sales journal specifically for this use case.

##### Corrects referenced document amount¶

When a correction on the amounts is required, use the button Add Credit note and select Partial Refund. In this case the SII Reference Code is automatically set to Corrige el monto del Documento de Referencia.

### Debit notes¶

In Chilean localization, debit notes, in addition to credit notes, can be created using the Add Debit Note button, with two main use cases.

#### Casi d’uso¶

##### Add debt on invoices¶

The primary use case for debit notes is to increase the value of an existing invoice. To do so, select option 3\. Corrige el monto del Documento de Referencia for the Reference Code SII field.

In this case Odoo automatically includes the Source Invoice in the Cross Reference tab.

Suggerimento

You can only add debit notes to an invoice already accepted by the SII.

##### Cancel credit notes¶

In Chile, debits notes are used to cancel a valid credit note. To do this, click the Add Debit Note button and select the 1: Anula Documentos de referencia option for the Reference Code SII field.

### Fatture fornitore¶

As part of the Chilean localization, you can configure your incoming email server to match the one you have registered in the SII in order to:

  * Automatically receive the vendor bills DTE and create the vendor bill based on this information.

  * Automatically send the reception acknowledgement to your vendor.

  * Accept or claim the document and send this status to your vendor.




#### Reception¶

As soon as the vendor email with the attached DTE is received:

  1. The vendor bill maps all the information included in the XML.

  2. An email is sent to the vendor with the reception acknowledgement.

  3. The DTE Status is set as Acuse de Recibido Enviado.




#### Acceptation¶

If all the commercial information is correct on your vendor bill, then you can accept the document using the Aceptar Documento button. Once this is done, the DTE Acceptation Status changes to Accepted and an email of acceptance is sent to the vendor.

#### Richiedi¶

In case there is a commercial issue or the information is not correct on your vendor bill, you can claim the document before validating it, using the Claim button. Once this is done, the DTE Acceptation Status changes to Claim and a rejection email is sent to the vendor.

If you claim a vendor bill, the status changes from Draft to Cancel automatically. Considering this as best practice, all the claimed documents should be cancelled as they won’t be valid for your accounting records.

### Electronic purchase invoice¶

The _electronic purchase invoice_ is a feature included in the `l10n_cl_edi` module.

Once all configurations have been made for electronic invoices (e.g., uploading a valid company certificate, setting up master data, etc.), the electronic purchase invoices need their own CAFs. Please refer to the CAF documentation to check the details on how to acquire the CAFs for electronic purchase invoices.

Electronic purchase invoices are useful when vendors are not obligated to expedite an electronic vendor bill for your purchase. Still, your obligations require a document to be sent to the SII as proof of purchase.

#### Configurazione¶

To generate an electronic purchase invoice from a vendor bill, the bill must be created in a purchase journal with the _Use Documents_ feature enabled. It is possible to modify an existing purchase journal or create a new one in the following process.

To modify the existing purchase journal, or create a new purchase journal, navigate to Accounting ‣ Configuration ‣ Journals. Then, click the New button, and fill in the following required information:

  * Type: select Purchase from the drop-down menu for vendor bill journals.

  * Use Documents: check this field so the journal can generate electronic documents (in this case the electronic purchase invoice).




#### Generate an electronic purchase invoice¶

To generate this type of document, it is necessary to create a vendor bill in Odoo. To do so, navigate to Accounting ‣ Vendors ‣ Bills, and click the New button.

When all of the electronic purchase invoice information is filled, select the option (46) Electronic Purchase Invoice in the Document Type field:

After the vendor bill is posted:

  * The DTE file (Electronic Tax Document) is automatically created and added to the chatter.

  * The DTE SII Status is set as Pending to be sent.




Odoo automatically updates the _DTE Status_ every night using a scheduled action. To get a response from the SII immediately, click the Send now to SII button.

### Delivery guide¶

To install the Delivery Guide module, go to Apps and search for `Chile (l10n_cl)`. Then click Install on the module Chile - E-Invoicing Delivery Guide.

Nota

Chile - E-Invoicing Delivery Guide has a dependency with Chile - Facturación Electrónica. Odoo will install the dependency automatically when the Delivery Guide module is installed.

The _Delivery Guide_ module includes the ability to send the DTE to SII and the stamp in PDF reports for deliveries.

Once all configurations have been made for electronic invoices (e.g., uploading a valid company certificate, setting up master data, etc.), delivery guides need their own CAFs. Please refer to the CAF documentation to check the details on how to acquire the CAF for electronic Delivery Guides.

Verify the following important information in the Price for the Delivery Guide configuration:

  * From Sales Order: delivery guide takes the product price from the sales order and shows it on the document.

  * From Product Template: Odoo takes the price configured in the product template and shows it on the document.

  * No show price: no price is shown in the delivery guide.




Electronic delivery guides are used to move stock from one place to another and they can represent sales, sampling, consignment, internal transfers, and basically any product move.

#### Delivery guide from a sales process¶

Avvertimento

A delivery guide should **not** be longer than one page or contain more than 60 product lines.

When a sales order is created and confirmed, a delivery order is generated. After validating the delivery order, the option to create a delivery guide is activated.

Avvertimento

When clicking on Create Delivery Guide for the first time, a warning message pops up, stating the following:

`No se encontró una secuencia para la guía de despacho. Por favor, establezca el primer número dentro del campo número para la guía de despacho`

This warning message means the user needs to indicate the next sequence number Odoo has to take to generate the delivery guide (e.g. next available CAF number), and only happens the first time a delivery guide is created in Odoo. After the first document has been correctly generated, Odoo takes the next available number in the CAF file to generate the following delivery guide.

After the delivery guide is created:

  * The DTE file (Electronic Tax Document) is automatically created and added to the chatter.

  * The DTE SII Status is set as Pending to be sent.




The DTE Status is automatically updated by Odoo with a scheduled action that runs every night. To get a response from the SII immediately, press the Send now to SII button.

Once the delivery guide is sent, it may then be printed by clicking on the Print Delivery Guide button.

Delivery guide will have fiscal elements that indicate that the document is fiscally valid when printed (if hosted in _Odoo SH_ or on _On-premise_ remember to manually add the pdf417gen library mentioned in the Invoice PDF report section).

### Electronic receipt¶

To install the Electronic Receipt module, go to Apps and search for `Chile (l10n_cl)`. Then click Install on the module Chile - Electronic Receipt.

Nota

Chile - Electronic Receipt has a dependency with Chile - Facturación Electrónica. Odoo will install the dependency automatically when the E-invoicing Delivery Guide module is installed.

Once all configurations have been made for electronic invoices (e.g., uploading a valid company certificate, setting up master data, etc.), electronic receipts need their own CAFs. Please refer to the CAF documentation to check the details on how to acquire the CAFs for electronic receipts.

Electronic receipts are useful when clients do not need an electronic invoice. By default, there is a partner in the database called Anonymous Final Consumer with a generic RUT `66666666-6` and taxpayer type of Final Consumer. This partner can be used for electronic receipts or a new record may be created for the same purpose.

Although electronic receipts should be used for final consumers with a generic RUT, it can also be used for specific partners. After the partners and journals are created and configured, the electronic receipts are created in the standard way as electronic invoice, but the type of document (39) Electronic Receipt should be selected in the invoice form:

#### Validation and DTE status¶

When all of the electronic receipt information is filled, manually (or automatically) proceed to validate the receipt from the sales order. By default, Electronic Invoice is selected as the Document Type, however in order to validate the receipt correctly, make sure to edit the Document Type and change to Electronic Receipt.

After the receipt is posted:

  * The DTE file (Electronic Tax Document) is created automatically and added to the chatter.

  * The DTE SII Status is set as Pending to be sent.




The DTE Status is automatically updated by Odoo with a scheduled action that runs every day at night. To get a response from the SII immediately, press the Send now to SII button.

Please refer to the DTE Workflow for electronic invoices as the workflow for electronic receipt follows the same process.

### Electronic export of goods¶

To install the Electronic Exports of Goods module, go to Apps and search for `Chile (l10n_cl)`. Then click Install on the module Electronic Exports of Goods for Chile.

Nota

Chile - Electronic Exports of Goods for Chile has a dependency with Chile \- Facturación Electrónica.

Once all configurations have been made for electronic invoices (e.g., uploading a valid company certificate, setting up master data, etc.), electronic exports of goods need their own CAFs. Please refer to the CAF documentation to check the details on how to acquire the CAFs for electronic receipts.

Electronic invoices for the export of goods are tax documents that are used not only for the SII but are also used with customs and contain the information required by it.

#### Contact configurations¶

#### Chilean customs¶

When creating an electronic exports of goods invoice, these new fields in the Other Info tab are required to comply with Chilean regulations.

#### PDF report¶

Once the invoice is accepted and validated by the SII and the PDF is printed, it includes the fiscal elements that indicate that the document is fiscally valid and a new section needed for customs.

### eCommerce electronic invoicing¶

To install the Chilean eCommerce module, go to Apps, search for the module by its technical name `l10n_cl_edi_website_sale, and click the Activate button.

This module enables the features and configurations to:

  * Generate electronic documents from the _eCommerce_ application

  * Support for required fiscal fields in the _eCommerce_ application

  * Effectively let the final client decide the electronic document to be generated for their purchase




Once all of the configurations are made for the Chilean electronic invoice flow, the following configurations are required for the eCommerce flow to be integrated.

To configure your website to generate electronic documents during the sale process, go to Website ‣ Configuration ‣ Settings ‣ Invoicing and activate the Automatic Invoice feature. Activating this feature allows electronic documents to be automatically generated when an online payment is confirmed.

Since an online payment needs to be confirmed for the _automatic invoice_ feature to generate the document, a payment provider must be configured for the related website.

Nota

Review the [Online payments](../payment_providers.html) documentation for information on which payment providers are supported in Odoo, and how to configure them.

It is also recommended to configure your products so they are able to be invoiced when an online payment is confirmed. To do so, go to Website ‣ eCommerce ‣ Products and select the product template of the desired product. Then, set the Invoicing Policy to Ordered quantities.

#### Invoicing flows¶

Clients from Chile will be able to select if they need an **invoice** or a **ballot** for their purchase with an extra step added during the checkout process.

If the customer selects the Electronic Invoice option, fiscal fields are required to be filled out, including the Activity Description, the Identification Number and their DTE Email.

If the client selects the Electronic Receipts option, they will be directed to the next step, and the electronic document will be generated for the _Consumidor Final Anónimo_ contact.

Clients from countries other than Chile, will have their electronic receipts automatically generated for them by Odoo.

Nota

If a purchase through eCommerce requires an export, the customer will need to contact your company to generate an electronic export invoice (_document type 110_), which can be done from the _Accounting_ app.

### Point of Sale electronic invoicing¶

To install the Chilean Module for Point of Sale, go to the Apps application on the main Odoo dashboard, search for the module by its technical name `l10n_cl_edi_pos`, and click the Activate button.

This module enables the following features and configurations to:

  * Generate electronic documents from the _Point of Sale_ application

  * Support the required fiscal fields for contacts created in the _Point of Sale_ application

  * Effectively lets the final client decide the type of electronic document to be generated for their purchase

  * Print QR or 5-digit codes in tickets to access to electronic invoices




To configure contacts with the required fiscal information, review the partner information section, or directly modify a contact. Navigate to Point of Sale ‣ Session ‣ Customers ‣ Details, and edit any of the following fields:

  * Nome

  * E-mail

  * Identification Type

  * Tax Payer Type

  * Type Giro

  * DTE Email

  * RUT




To configure the products, navigate to Point of Sale ‣ Products ‣ Products and select a product record. In the Sales tab of the product form, it is necessary to mark the product as Available for POS, this makes the product available for sale in the _Point of Sale_ app.

Optionally, the following features are available for configuration in the Point of Sale ‣ Configuration ‣ Settings ‣ Bills & Receipts section:

  * Use QR code on ticket: this feature enables a QR code to be printed on the user’s receipt so they can easily request an invoice after their purchase

  * Generate a code on ticket: this feature enables a 5-digit code to be generated on the receipt, allowing the user to request an invoice through the customer portal




#### Invoicing flows¶

The following sections cover the invoicing flows for the _Point of Sale_ application.

##### Electronic receipts: anonymous end user¶

When making a purchase as an anonymous user that does not request an electronic invoice, Odoo automatically selects Consumidor Final Anónimo as the contact for the order and generates the electronic receipt.

Nota

If the client requests a credit note due to a return of their purchase, the credit note should be made using the _Accounting_ app. See the [credit notes and refunds](../accounting/customer_invoices/credit_notes.html) documentation for detailed instructions.

##### Electronic receipts: specific customer¶

When specific user makes a purchase that does not request an electronic invoice, Odoo automatically selects the contact for the order as the Consumidor Final Anónimo, and allows you to select or create the required customer contact with their fiscal information for the receipt.

Nota

If the client requests a credit note because of a return of this type of purchase, the credit note and return process can be managed directly from the POS session.

##### Electronic invoices¶

When clients request an electronic invoice, it is possible to select or create the required contact with their fiscal information. When the payment is being made, select the option Invoice to generate the document.

Nota

For both the electronic receipts and invoices, if the product is not affected by taxes, Odoo detects this and generates the correct type of document for tax-exempt sales.

##### Resi¶

For electronic receipts (not generated for the _Consumidor Final Anónimo_) and electronic invoices, it is possible to manage the process to return products sold in a POS order by selecting the Refund button.

Orders can be searched by the order status or by contact, and be selected for the refund to be based on the client’s original order.

When the return payment is validated, Odoo generates the necessary credit note, referencing the original receipt or invoice, partially or fully cancelling the document.

Vedi anche

[Smart tutorial - Electronic invoicing for point of sale](https://www.youtube.com/watch?v=B2XuWmtlmno&t=360s).

## Rapporti finanziari¶

### Balance tributario de 8 columnas¶

This report presents the accounts in detail (with their respective balances), classifying them according to their origin and determining the level of profit or loss that the business had within the evaluated period of time.

You can find this report in Accounting ‣ Reporting ‣ Balance Sheet and selecting in the Report field the option Chilean Fiscal Balance (8 Columns) (CL).

### Propuesta F29¶

The form _F29_ is a new system that the SII enabled to taxpayers, and that replaces the _Purchase and Sales Books_. This report is integrated by Purchase Register (CR) and the Sales Register (RV). Its purpose is to support the transactions related to VAT, improving its control and declaration.

Importante

The _Propuesta F29 (CL)_ report in Odoo covers the basic legal requirements as a first proposal for your final tax declaration.

This record is supplied by the electronic tax documents (DTE’s) that have been received by the SII.

You can find this report in Accounting ‣ Reporting ‣ Tax Reports and selecting the Report option Propuesta F29 (CL).

It is possible to set the PPM and the Proportional Factor for the fiscal year from the Accounting ‣ Configuration ‣ Settings.

Or manually in the reports by clicking on the ✏️ (pencil) icon.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/finance/fiscal_localizations/chile.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](colombia.html "Colombia") |
  * [precedente](canada.html "Canada") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Cile


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
  *[FBM]: Fulfilled by Merchant
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
  *[FPS]: Faster Payment System
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
  *[PAC]: fornitori autorizzati
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
  *[CIS]: Central Invoice System
  *[CAE]: Código de Autorización Electrónico
  *[FE]: Factura Electrónica
  *[CFE]: Comprobante Fiscal Electrónico
  *[ANAF]: Agenzia nazionale rumena per l'amministrazione fiscale
  *[Sdi]: Sistema di Interscambio
  *[NF-e]: Nota Fiscal Eletrônica
  *[NFS-e]: Nota Fiscal de Serviços Eletrônica
  *[NFC-e]: Nota Fiscal de Consumidor Eletrônica
  *[SEFAZ]: Secretaria da Fazenda