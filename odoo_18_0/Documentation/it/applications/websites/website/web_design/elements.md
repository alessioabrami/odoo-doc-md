# Elementi — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../pages.html "Pagine") |
  * [precedente](themes.html "General theme") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Siti web](../../../websites.html) »
  * [Sito web](../../website.html) »
  * [Web design](../web_design.html) »
  * Elementi



# Elementi¶

Elements help structure and present content effectively. They range from text-based components like titles, lists and text highlights to interactive ones such as buttons and links. Visual elements like images, icons, videos, and animations can also be added to improve content presentation and organization.

To add or modify a website element:

  1. Navigate to the relevant website page and click on Edit.

  2. Click the section on the page where you want to add or modify an element.

  3. Make the necessary changes.

  4. Click on Save.




Nota

The default styles for headings, buttons, links, and paragraph text, for example, are defined in the [Theme tab](themes.html) of the website editor.

## Titles¶

Titles define headings and organize website content into different levels for clarity and structure. To insert a title, type `/title`, choose the heading style (Heading 1, Heading 2, or Heading 3), and type the text.

Suggerimento

Alternatively, type the text, select it, and choose the appropriate style from the Inline Text section in the Customize tab of the website editor. Additional formatting options, such as fonts and colors, are also available in this section.

## Pulsanti¶

Buttons are interactive elements that allow to link to another page or to a page anchor. To insert a button:

  1. Type `/button`.

  2. Enter the button’s label in the Link Label field.

  3. Add the URL or Email. Type `/` to search for a page and `#` to link to an anchor.

  4. Set the Style, Size, and Layout to define the button’s appearance.

  5. If needed, toggle the switch to open the linked page or anchor in a new tab.

  6. Click Apply to save changes.




Suggerimento

To modify an existing button, click the button and edit the options in the Inline text section of the website editor.

## Immagini¶

To insert an image:

  1. Type `/image`.

  2. [Search the Unsplash database](../../../general/integrations/unsplash.html) or click Upload an image to choose a file from your local images.

  3. Fai clic su Aggiungi.

  4. To customize the image, click on the image and edit the options in the Image section of the website editor. For example:

     * Replace the image.

     * Define an [alt tag](https://help.siteimprove.com/support/solutions/articles/80000448480-where-are-alt-tags-used-and-why-are-they-important) in the Description field.

     * Enter a title tag in the Tooltip field. This text will appear when visitors hover their mouse over the image.

     * Add a Shape; some shapes also allow for color customization.

     * Adjust the image’s Width, e.g., to improve performance. A smaller size may be suggested if it is sufficient for display.

     * Resize the image using the Transform tool.

     * Adjust the Padding to add space (in pixels) around the image.

     * Etc.




## Videos¶

To add a video, type `/video`, insert the URL, and turn on the desired options:

  * Autoplay: to automatically play the video when the page is accessed. The video is automatically muted by default.

  * Loop: to play the video on a loop.

  * Hide player controls

  * Hide fullscreen button




## Icone¶

To insert an icon, type `/image`, go to the Icons tab, select an icon, and click Add. To modify an icon, click on it and use the Icon section of the website editor to customize options, such as Color, Size, Animations, Shape, etc.

## Collegamenti¶

Links are used to connect different pages and resources, guiding visitors and improving navigation. To add a link, type `/link`, then, in the pop-up that opens, enter the link’s Label and add the URL or Email. Type `/` to search for a page and `#` to link to an anchor.

Suggerimento

By default, the Style field is set to Link. Select a different style to transform the link into a button.

## Liste¶

Lists help organize content clearly, making information easier to read and improving web pages” structures. Type `/list` and choose from three different types of lists: Bulleted lists, Numbered lists, or Checklists.

## Text highlights¶

Highlights can be added to titles and text using in the Inline Text section of the website editor. To add a highlight:

  1. Select the text or title you want to highlight.

  2. In the website editor, click on Highlight.

  3. Select the highlight style.

  4. Modify its Color.

  5. Choose its Thickness.




## Animations¶

Animations are used to add movement to [building blocks](building_blocks.html) and website elements such as images and text. Three types of animation are available: On Scroll, On Appearance, and On Hover (for images only).

To add an animation to a website element:

  1. Click on the element.

  2. In the website editor, go to the relevant section for the element (e.g., Button, Column, Inline Text, etc.).

  3. In the Animation field, select the desired animation type.

  4. Customize the animation settings as needed. Available options vary based on the selected animation type.




### Animations on scroll¶

For animations on scroll, it is possible to:

>   * Choose In to add the animation when the element enters the screen and Out to add it when it leaves the screen.
> 
>   * Select an Effect.
> 
>   * Choose the Direction of the effect.
> 
>   * Adapt the Intensity of the effect.
> 
>   * Define the Scroll Zone, where the first value represents the percentage of the screen shown when the effect starts, and the second value represents its percentage at the end.
> 
> 


### Animations on appearance¶

For animations on appearance, it is possible to:

>   * Choose among different effects.
> 
>   * Choose the Direction of the effect.
> 
>   * Pick a Trigger option to define when the animation occurs: either the First Time only or Every Time.
> 
>   * Adapt the Intensity of the effect.
> 
>   * If you want the animation to be triggered after a number of seconds, define this number in the Start After field.
> 
>   * Choose a Duration for the animation.
> 
> 


### Animations on hover (for images only)¶

Animations On hover can be added to images. You can choose the Effect of the animation, as well as the Color and the Stroke Width.

Vedi anche

[Odoo HTML editor](../../../essentials/html_editor.html)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/websites/website/web_design/elements.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../pages.html "Pagine") |
  * [precedente](themes.html "General theme") |
  * [Odoo 18.0 documentazione](../../../../index-2.html) »
  * [Documentazione utente](../../../../applications.html) »
  * [Siti web](../../../websites.html) »
  * [Sito web](../../website.html) »
  * [Web design](../web_design.html) »
  * Elementi


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
  *[URL]: Uniform Resource Locators
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