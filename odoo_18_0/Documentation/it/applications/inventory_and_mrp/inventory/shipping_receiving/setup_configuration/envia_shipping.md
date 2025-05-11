# Envia.com integration — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](fedex.html "FedEx integration") |
  * [precedente](dhl_credentials.html "DHL integration") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Shipping and receiving](../../shipping_receiving.html) »
  * [Delivery methods](../setup_configuration.html) »
  * Envia.com integration



# Envia.com integration¶

Envia.com is a shipping service that connects businesses with multiple carriers in Odoo. Key features include:

  * **Multi-carrier & international shipping**: Compare rates across carriers and select the best option for domestic or global shipments.

  * **Automated label generation** : Generate shipping labels at order confirmation.

  * **Real-time rate calculation** : Fetch rates based on package details and destination.




## Setup in Envia¶

To integrate [Envia.com](https://www.envia.com/) with Odoo, first create an account and activate the necessary shipping carriers. Then, obtain the API credentials, which is used to connect Envia.com to the Odoo database.

### Create an account and activate carriers¶

Begin by going to [Envia.com](https://www.envia.com/).

After signing in, in the left sidebar, click Settings ‣ Print Options and Carriers. Next, select the country to set the currency and display available shipping carriers.

Importante

When signing up, make sure to select the correct language **and** country in the upper right-hand corner. This affects the currency of the account!

After deciding on the desired carrier, click Activate, then click Services to select the carrier’s available shipping options.

Suggerimento

Billing is always processed in the currency of the country that matches the primary billing address. If the company operates in multiple countries, consider creating separate accounts for each location.

Nota

Envia will send an SMS or WhatsApp message to confirm the email address and phone number.

### Generate Envia.com credentials¶

Go to [Envia.com](https://www.envia.com/), navigate to Developers ‣ API Keys, on the left menu, then click add to generate a new key.

This key is required to authenticate Odoo’s connection with Envia.com. Retrieve it at any time by returning to the API Keys section.

## Installazione in Odoo¶

[Install](../../../../general/apps_modules.html#general-install) the Envia Shipping (`delivery_envia`) module, and proceed to the following sections to configure the integration in Odoo.

### Envia.com shipping connector configuration¶

After activating the Envia.com connector, create a delivery method by going to Inventory ‣ Configuration ‣ Delivery Methods and click New.

Fill out the following form fields:

  * Shipping Method: Name of the shipping method, e.g. `Envia.com`.

  * Provider: Select Envia from the drop-down menu.

  * Delivery Product: The product listed on the sales order as the delivery charge. A specific delivery product for Envia.com must be created.

  * In the Envia Configuration tab, enter the Envia Production Access Token.

  * In the Envia Configuration tab, enter the Envia Sandbox Access Token.

  * Insurance percentage: If insurance is needed, place a percentage of the value to insure. If not, leave it as 0. Keep in mind that the insurance price is calculated only after the label has been generated, including for LTL shipments.




Suggerimento

It is mandatory to fill both the production and sandbox tokens, but it could be left as a random character as it is not validated at this point.

Additional considerations for the Envia Default Package:

  * The package is specified in mm and kg. The weight refers to the container itself, not its contents. Leave the weight as `0` if no weight is reported, and set the max weight to `0` if there is no specified limit.

  * Envia Package Type: Set to Box by default. Ensure the correct type is selected, as it affects the available carriers and options displayed, which vary depending on this selection.




Once previous fields are properly set, navigate to the Envia Configuration tab, and in the Envia.com Service Name field, click the __(refresh) icon to sync the carriers. In the pop-up window that appears, select a carrier and a service level from the list.

Importante

Envia keeps the main currency of the account fixed. In order to provide more precise conversions for the costs of shipping, specify the currency that is set for the account on Envia. If necessary, Odoo offers the option to change the country. By default it uses the country associated with the company.

Nota

If more than one shipping option is needed, create more shipping methods in Odoo and modify any parameter like the package, carrier, or service.

### Shipping information¶

To use Envia.com to generate shipping labels, the following information **must** be filled out accurately and completely in Odoo:

  1. **Customer information** : When creating a quotation, ensure the selected Customer has a valid phone number, email address, and shipping address.

To verify, select the Customer field to open their contact page. Here, add their shipping address in the Contact field, along with their Mobile number and Email address.

  2. **Product weight** : Ensure all products in a delivery order have a specified Weight in the Inventory tab of their product form. Refer to the [Product weight section](third_party_shipper.html#inventory-shipping-receiving-configure-weight) of this article for detailed instructions.

  3. **Warehouse address** : By default all packages are sent from the specified address in the warehouse, make sure to set the address for correct label generation.




### Address filling guide¶

Each country has rules regarding how an address is filled. This is a comprehensive guide of each country’s expected fields exceptions:

Nazione | Indirizzo | Indirizzo 2 | Città | State_id  
---|---|---|---|---  
Argentina | Street and number | Locality | Città | Province  
Brasile | Eccezione | Neighborhood | Città | Stato  
Cile | Street and number | Città | Commune | Regione  
Colombia | Street and number | Not needed | Municipality | Ufficio  
Guatemala | Street and number | Neighborhood | Città | Stato  
Messico | Street and number | Neighborhood | Città | Stato  
Uruguay | Street and number | Complementary info | Locality | Stato  
  
Countries not listed here should be entered normally.

Nota

For some countries, the zip code is not commonly requested. If empty, Odoo will use Envia’s zip approximation services to get the zip code.

For Colombia, the zip code is extracted from the city selected in `city_id` if the localization is installed, otherwise Odoo will use the zip field.

Nota

Colombia and Mexico have a list of cities referred to as `city_id` in Odoo. If `city_id` is set, it is used as the city field. If not set, then Odoo will try to use the city field.

Nota

In Mexico, some carriers might require the Colony field, commonly known as neighborhood. It is not always mandatory, but when using the **EDI for Mexico (Advanced Features)** module, the Colony field is required.

Nota

In Brazil the address is split to comply with regulation, so `street_name` is used for the street name only. `street_number1` is used for the street number and `street_number2` is used for the complement. This logic also applies if the Extended Addresses module is installed.

## Generate labels with Envia¶

When creating a quotation in Odoo, add shipping and the Envia.com shipping product. Then, Validate the delivery. Shipping label documents are automatically generated in the chatter, which include the following:

  1. Shipping label(s) depending on the number of packages.

  2. Return label(s) if the Envia.com connector is configured for returns.




Importante

When labels are created, Envia.com automatically charges the configured account and the final amount is logged in the chatter. If multi-currency operations occur, the amount logged is calculated using Odoo’s rate. Actual rates may vary.

Additionally, the tracking number is now available.

Nota

Brazilian Authorities might request the invoice related to the shipping (NFe). It is recommended to physically attach the invoice of the order along with the label.

### International shipping¶

For international shipments it is required to fill both the HS code and the country of Origin of Goods, both can be found on the product’s Inventory tab.

### LTL shipments¶

LTL shipment labels can be generated through the Envia connector. The insurance for LTL shipments is based on the _insurance percentage_ specified in the delivery method’s form.

Importante

For Mexico, since a _Bill of Landing_ needs to be created for the shipment, Odoo is required to send the UNSPSC code of the contents, as well as a unit of measure for transportation which is **X8A - Pallet de madera** by default.

Nota

Additional services are available when selecting `pallet` as a Envia Package Type on the delivery method, which allows selecting additional services like lift assistance and deliveries during weekends.

## Tracking and cancellation¶

Shipments registered with Envia can be tracked using the Tracking smart button from the delivery order or using the tracking link from the [customer portal](../../../../general/users/portal.html).

## FAQ¶

### Measuring volumetric weight¶

Many carriers have several measurements for weight. There is the actual weight of the products in the parcel, and the volumetric weight. Volumetric weight is the volume that a package occupies when in transit, i.e. the physical size of a package.

Nota

Due to volumetric weight, it is possible that the actual weight in the label is higher than the calculated value.

### Which printing options are available?¶

On Envia.com in Settings ‣ Print options and Carriers printing options for each of the carriers displayed, make sure to use the appropriate format for the chosen carrier.

### The needed service is not available¶

For available carriers, make sure that they are enabled through Envia.

### Who will pay customs duties?¶

It’s important to make sure that if there are exports to other countries, use Envia’s carrier settings to configure whether it is paid by the sender or the receiver.

### What is «Envia error»?¶

It’s a message that appears when there’s an error in Envia. This message mentions what went wrong in their platform so it can be addressed.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/inventory_and_mrp/inventory/shipping_receiving/setup_configuration/envia_shipping.rst)

### Navigazione

  * [indice](../../../../../genindex.html "Indice generale")
  * [moduli](../../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](fedex.html "FedEx integration") |
  * [precedente](dhl_credentials.html "DHL integration") |
  * [Odoo 18.0 documentazione](../../../../../index-2.html) »
  * [Documentazione utente](../../../../../applications.html) »
  * [Supply Chain](../../../../inventory_and_mrp.html) »
  * [Magazzino](../../../inventory.html) »
  * [Shipping and receiving](../../shipping_receiving.html) »
  * [Delivery methods](../setup_configuration.html) »
  * Envia.com integration


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
  *[MPS]: Master Production Schedule
  *[OEE]: overall equipment effectiveness
  *[RFQ]: Request for Quotation
  *[RfQ]: request for quotation
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
  *[VAT]: Value-Added Tax Identification
  *[SMP]: Service Metadata Publisher
  *[AVCO]: Average Cost
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
  *[SVLs]: stock move layers
  *[SP]: Scrap Order
  *[DO]: Delivery Order
  *[RFQs]: Requests for Quotations
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
  *[SVL]: stock move layer
  *[JIT]: just-in-time