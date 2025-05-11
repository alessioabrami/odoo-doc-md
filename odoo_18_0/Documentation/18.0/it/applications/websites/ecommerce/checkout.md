# Check-out — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](payments.html "Fornitori di pagamento") |
  * [precedente](cart.html "Aggiungi al carrello") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Siti web](../../websites.html) »
  * [E-commerce](../ecommerce.html) »
  * Check-out



# Check-out¶

Once customers have added their desired products to the cart, they can access it by clicking the __button in the header to start the checkout process. In Odoo eCommerce, this process consists of sequential steps, some of which support additional features. The related checkout pages can be customized using the website editor.

## Checkout policy¶

To allow customers to checkout as guests or force them to sign in/create an account, go to Website ‣ Configuration ‣ Settings, scroll down to the Shop - Checkout Process section, and configure the Sign in/up at checkout setting. The following options are available:

  * Optional: Customers can check out as guests and register later via the order confirmation email to track their order.

  * Disabled (buy as guest): Customers can checkout as guests without creating an account.

  * Mandatory (no guest checkout): Customers must sign in or create an account at the Review Order step to complete their purchase.




### B2B access management¶

To restrict checkout to selected B2B customers, follow these steps:

  1. Go to Website ‣ Configuration ‣ Settings, and in the Shop - Checkout Process section, enable the Mandatory (no guest checkout) option.

  2. Scroll down to the Privacy section, go to Customer Account, and select On invitation.

  3. Go to Website ‣ eCommerce ‣ Customers, switch to the List view, and select the customers you wish to grant access to your [portal](../../general/users/portal.html).

  4. Click the __ Actions button, then Grant portal access.

  5. Review the selected customers in the Portal Access Management pop-up and click Grant Access.




Once done, the relevant customers receive an email confirming their account creation, including instructions on setting a password and activating their account.

Nota

  * You can revoke access or re-invite a customer using the related buttons in the Portal Access Management pop-up.

  * Users can only have one [portal access](../../general/users/portal.html) per email.

  * Settings are website-specific, so you could set up a B2C website that allows guest checkout and B2B website with mandatory sign-in.




Vedi anche

  * [Customer accounts](customer_accounts.html)

  * [Portal access](../../general/users/portal.html)




## Checkout steps¶

During the checkout process, customers are taken through the following steps:

  * Review order

  * Delivery

  * Extra info (if enabled)

  * Payment

  * Order confirmation




Each step can be customized using the website editor: Click Edit to add [building blocks](../website/web_design/building_blocks.html) from the Blocks tab or open to the Customize tab to enable various checkout options.

Nota

Content added through building blocks is **specific** to each step.

### Review order¶

The Review Order step allows customers to see the items they added to their cart, adjust quantities, or Remove products. Information related to the product prices and taxes applied are also displayed. Customers can then click the Checkout button to continue to the Delivery step.

Open the website editor to enable checkout options such as:

  * Suggested Accessories: to showcase [accessory products](products/cross_upselling.html#ecommerce-cross-upselling-accessory);

  * Promo Code: to allow customers to redeem [gift cards](../../sales/sales/products_prices/ewallets_giftcards.html#ewallet-gift-gift-cards) or apply [discount codes](../../sales/sales/products_prices/loyalty_discount.html);

  * Add to Wishlist: To allow signed-in users to remove a product from their cart and add it to their wishlist, go to Website ‣ Configuration ‣ Settings, scroll to the Shop - Products section, and enable Wishlists. The Add to Wishlist option is then enabled by default in the website editor.




Nota

  * If a [fiscal position](../../finance/fiscal_localizations.html) is detected automatically, the product tax is determined based on the customer’s IP address.

  * If the installed [payment provider](../../finance/payment_providers.html) supports [express checkout](../../finance/payment_providers.html#payment-providers-express-checkout), a dedicated button is displayed, allowing customers to go straight from the cart to the confirmation page without filling out the contact form.




### Consegna¶

Once they have reviewed their order:

  * Unsigned-in customers are prompted to Sign in or enter their Email address, along with their delivery address and phone details;

  * Signed-in customers can select the appropriate Delivery address.




They can then [choose a delivery method](shipping.html), select or enter their Billing Address (or toggle the Same as delivery address switch if the billing and delivery addresses are identical), and click Confirm to proceed to the next step.

Suggerimento

For B2B customers, you can also enable optional VAT and Company name fields by toggling the Show B2B Fields option in the website editor.

### Info aggiuntive¶

You can add an Extra Info step in the checkout process to collect additional customer information through an online form, which is then included in the [sales order](order_handling.html#handling-sales). To do so enable the Extra Step option in the website editor. The form can be [customized](../website/web_design/building_blocks/dynamic_content.html#website-dynamic-content-form) as needed.

Suggerimento

Alternatively, go to Website ‣ Configuration ‣ Settings, scroll to the Shop - Checkout Process section, enable Extra Step During Checkout, and click Save. Click __ Configure Form to customize the form.

### Pagamento¶

At the Payment step, customers Choose a payment method, enter their payment details, and click Pay now.

You can require customers to agree to your [terms and conditions](../../finance/accounting/customer_invoices/terms_conditions.html) before payment. To enable this option, go to the website editor and toggle the Accept Terms & Conditions feature.

Suggerimento

Enable the [developer mode](../../general/developer_mode.html#developer-mode) and click the __ bug icon to display an [availability](../../finance/payment_providers.html#payment-providers-availability) report for payment providers and payment methods, which helps diagnose potential availability issues on the payment form.

### Order confirmation¶

The final step of the checkout process is the Order confirmation, which provides a summary of the customer’s purchase details.

Vedi anche

[Order handling](order_handling.html)

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/websites/ecommerce/checkout.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](payments.html "Fornitori di pagamento") |
  * [precedente](cart.html "Aggiungi al carrello") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Siti web](../../websites.html) »
  * [E-commerce](../ecommerce.html) »
  * Check-out


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
  *[EDI]: Electronic Data Exchange
  *[SDD]: SEPA Direct Debit
  *[PLE]: Programa de Libros Electrónico
  *[BoM]: Bill of Materials
  *[MO]: Manufacturing Order
  *[MPS]: Master Production Schedule
  *[OEE]: overall equipment effectiveness
  *[RFQ]: request for quotation
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
  *[RFQs]: requests for quotation
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
  *[CSV]: Valori separati da virgola
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
  *[FAQs]: Frequently Asked Questions