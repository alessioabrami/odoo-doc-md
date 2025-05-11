# Pagine — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](pages/menus.html "Menù") |
  * [precedente](web_design/elements.html "Elementi") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Siti web](../../websites.html) »
  * [Sito web](../website.html) »
  * Pagine



# Pagine¶

Odoo allows you to create pages for your website and customize their content and appearance to your needs.

**Static** pages have stable content, such as the homepage. You can manually create new ones, define their URLs, adapt their properties, etc. **Dynamic** pages, on the other hand, are generated dynamically. All pages generated automatically by Odoo, for example, when you install an app or module (e.g., `/shop` or `/blog`) or publish a new product or blog post, are dynamic pages and are therefore managed differently.

## Page creation¶

Website pages can be created from the **frontend** and the **backend**. To create a new website page, proceed as follows:

>   1.      * Either open the **Website** app, click \+ New in the top-right corner, then select Page;
> 
>      * Or go to Website ‣ Site ‣ Pages and click New.
> 
>   2. Enter a Page Title; this title is used in the menu and the page’s URL.
> 
>   3. Fai clic su Crea.
> 
>   4. Customize the page’s content and appearance using the website builder, then click Save.
> 
>   5. Publish the page.
> 
> 


Nota

Disable Add to menu if the page should not appear in the menu.

## Page management¶

### Publishing/unpublishing pages¶

Pages need to be published to make them accessible to website visitors. To publish or unpublish a page, access it and toggle the switch in the upper-right corner from Unpublished to Published, or vice versa.

Nota

It is also possible to:

>   * publish/unpublish a page from the page properties, where you can define a publishing date and/or restrict the page’s visibility if needed;
> 
>   * publish/unpublish several pages at once: go to Website ‣ Site ‣ Pages, select the pages, then click Action and select Publish or Unpublish.
> 
> 


### Pagina principale¶

When you create a website, Odoo creates a dedicated Home page by default, but you can define any website page as your homepage. To do so, go to Website ‣ Configuration ‣ Settings, then, in the Website info section, define the URL of the desired page in the field Homepage URL (e.g., `/shop`).

Alternatively, you can define any static page as your homepage by going to Website ‣ Site ‣ Properties. Select the Publish tab and enable Use as Homepage.

### Page properties¶

To modify a static page’s properties, access the page you wish to modify, then go to Site ‣ Properties.

The Name tab allows you to:

  * rename the page using the Page Name field;

  * modify the Page URL. In this case, you can redirect the old URL to the new one if needed. To do so, enable Redirect Old URL, then select the Type of redirection:

    * 301 Moved permanently: to redirect the page permanently;

    * 302 Moved temporarily: to redirect the page temporarily.




You can further adapt the page’s properties in the Publish tab:

  * Show in Top Menu: Disable if you don’t want the page to appear in the menu;

  * Use as Homepage: Enable if you want the page to be the homepage of your website;

  * Indexed: Disable if you don’t want the page to be shown in search engine results;

  * Published: Enable to publish the page;

  * Publishing Date: To publish the page at a specific moment, select the date, click the clock icon to set the time, then click the green check mark to validate your selection.

  * Visibility: Select who can access the page:

    * All

    * Signed In

    * Restricted Group: Select the [user access group(s)](../../general/users/access_rights.html) in the Authorized group field.

    * With Password: Enter the password in the Password field.




Suggerimento

 _Some_ of these properties can also be modified from Website ‣ Site ‣ Pages.

#### Duplicating pages¶

To duplicate a page, access the page, then go to Site ‣ Properties and click Duplicate Page. Enter a Page Name, then click OK. By default, the new page is added after the duplicated page in the menu, but you can remove it from the menu or change its position using the [menu editor](pages/menus.html).

#### Deleting pages¶

To delete a page, proceed as follows:

  1. Access the page, then go to Site ‣ Properties and click Delete Page.

  2. A pop-up window appears on the screen with all links referring to the page you want to delete, organized by category. To ensure website visitors don’t land on a 404 error page, you must update all the links on your website referring to the page. To do so, expand a category, then click on a link to open it in a new window. Alternatively, you can set up a redirection for the deleted page.

  3. Once you have updated the links (or set up a redirection), select the I am sure about this check box, then click OK.




### URL redirect mapping¶

URL redirect mapping consists in sending visitors and search engines to a URL different from the one they initially requested. This technique is used, for example, to prevent broken links when you delete a page, modify its URL, or migrate your site from another platform to an Odoo [domain](configuration/domain_names.html). It can also be used to improve [Search Engine Optimization (SEO)](pages/seo.html).

To access existing URL redirections and create new ones, [activate the developer mode](../../general/developer_mode.html) and go to Website ‣ Configuration ‣ Redirects.

Nota

  * A redirect record is added automatically every time you modify a page’s URL and enable Redirect Old URL.

  * You can set up redirections for static and dynamic pages.




To create a new redirection, click the New button, then fill in the fields:

  * Name: Enter a name to identify the redirect.

  * Action: Select the type of redirection:

>     * 404 Not found: visitors are redirected to a 404 error page when they try to access an unpublished or deleted page.
> 
>     * 301 Moved Permanently: for permanent redirections of unpublished or deleted static pages. The new URL is shown in search engine results, and the redirect is cached by browsers.
> 
>     * 302 Moved Temporarily: for short-term redirections, for example, if you are redesigning or updating a page. The new URL is neither cached by browsers nor shown in search engine results.
> 
>     * 308 Redirect/Rewrite: for permanent redirections of existing dynamic pages. The URL is renamed; the new name is shown in search engine results and is cached by browsers. Use this redirect type to rename a dynamic page, for example, if you wish to rename `/shop` into `/market`.

  * URL from: Enter the URL to be redirected (e.g., `/about-the-company`) or search for the desired dynamic page and select it from the list.

  * URL to: For 301, 302, and 308 redirects, enter the URL to be redirected to. If you want to redirect to an external URL, include the protocol (e.g., `https://`).

  * Website: Select a specific website.

  * Sequence: To define the order in which redirections are performed, e.g., in the case of redirect chains (i.e., a series of redirects where one URL is redirected to another one, which is itself further redirected to another URL).




Toggle the Activate switch to deactivate the redirection.

Importante

404, 301, and 302 redirections are meant to migrate traffic from unpublished or deleted pages to _new_ pages, while the 308 redirect is used for _permanent_ redirections of _existing_ pages.

Vedi anche

  * [Google documentation on redirects and search](https://developers.google.com/search/docs/crawling-indexing/301-redirects)

  * [Search Engine Optimization (SEO)](pages/seo.html)




  * [Menù](pages/menus.html)
  * [Search Engine Optimization (SEO)](pages/seo.html)



[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/websites/website/pages.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](pages/menus.html "Menù") |
  * [precedente](web_design/elements.html "Elementi") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Siti web](../../websites.html) »
  * [Sito web](../website.html) »
  * Pagine


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