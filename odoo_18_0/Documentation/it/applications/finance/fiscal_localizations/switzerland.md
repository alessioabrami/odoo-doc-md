# Svizzera — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](thailand.html "Thailandia") |
  * [precedente](spain.html "Spagna") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Svizzera



# Svizzera¶

## ISR (In-payment Slip with Reference number)¶

The ISRs are payment slips used in Switzerland. You can print them directly from Odoo. On the customer invoices, there is a new button called _Print ISR_.

Suggerimento

The button _Print ISR_ only appears there is well a bank account defined on the invoice. You can use CH6309000000250097798 as bank account number and 010391391 as CHF ISR reference.

Then you open a pdf with the ISR.

There exists two layouts for ISR: one with, and one without the bank coordinates. To choose which one to use, there is an option to print the bank information on the ISR. To activate it, go in Accounting ‣ Configuration ‣ Settings ‣ Customer Invoices and enable **Print bank on ISR** :

### ISR reference on invoices¶

To ease the reconciliation process, you can add your ISR reference as **Payment Reference** on your invoices.

To do so, you need to configure the Journal you usually use to issue invoices. Go to Accounting ‣ Configuration ‣ Journals, open the Journal you want to modify (By default, the Journal is named _Customer Invoices_), click en _Edit_ , and open the _Advanced Settings_ tab. In the **Communication Standard** field, select _Switzerland_ , and click on _Save_.

## Currency Rate Live Update¶

You can update automatically your currencies rates based on the Federal Tax Administration from Switzerland. For this, go in Accounting ‣ Settings, activate the multi-currencies setting and choose the service you want.

## Updated VAT for January 2018¶

Starting from the 1st January 2018, new reduced VAT rates will be applied in Switzerland. The normal 8.0% rate will switch to 7.7% and the specific rate for the hotel sector will switch from 3.8% to 3.7%.

### How to update your taxes in Odoo Enterprise (Odoo Online or On-premise)?¶

If you have the V11.1 version, all the work is already been done, you don’t have to do anything.

If you have started on an earlier version, you first have to update the module «Switzerland - Accounting Reports». For this, you go in Apps ‣ remove the filter «Apps» ‣ search for «Switzerland - Accounting Reports» ‣ open the module ‣ click on «upgrade».

Once it has been done, you can work on creating new taxes for the updated rates.

Suggerimento

**Do not suppress or modify the existing taxes** (8.0% and 3.8%). You want to keep them since you may have to use both rates for a short period of time. Instead, remember to archive them once you have encoded all your 2017 transactions.

The creation of such taxes should be done in the following manner:

  * **Purchase taxes** : copy the origin tax, change its name, label on invoice, rate and tax group (effective from v10 only)

  * **Sale taxes** : copy the origin tax, change its name, label on invoice, rate and tax group (effective from v10 only). Since the vat report now shows the details for old and new rates, you should also set the tags accordingly to

    * For 7.7% taxes: Switzerland VAT Form: grid 302 base, Switzerland VAT Form: grid 302 tax

    * For 3.7% taxes: Switzerland VAT Form: grid 342 base, Switzerland VAT Form: grid 342 tax




You’ll find below, as examples, the correct configuration for all taxes included in Odoo by default

**Tax Name** | **Rate** | **Label on Invoice** | **Tax Group (effective from V10)** | **Tax Scope** | **Tag**  
---|---|---|---|---|---  
TVA 7.7% sur achat B&S (TN) | 7.7% | 7.7% achat | TVA 7.7% | Acquisti | Switzerland VAT Form: grid 400  
TVA 7.7% sur achat B&S (Incl. TN) | 7.7% | 7.7% achat Incl. | TVA 7.7% | Acquisti | Switzerland VAT Form: grid 400  
TVA 7.7% sur invest. et autres ch. (TN) | 7.7% | 7.7% invest. | TVA 7.7% | Acquisti | Switzerland VAT Form: grid 405  
TVA 7.7% sur invest. et autres ch. (Incl. TN) | 7.7% | 7.7% invest. Incl. | TVA 7.7% | Acquisti | Switzerland VAT Form: grid 405  
TVA 3.7% sur achat B&S (TS) | 3.7% | 3.7% achat | TVA 3.7% | Acquisti | Switzerland VAT Form: grid 400  
TVA 3.7% sur achat B&S (Incl. TS) | 3.7% | 3.7% achat Incl. | TVA 3.7% | Acquisti | Switzerland VAT Form: grid 400  
TVA 3.7% sur invest. et autres ch. (TS) | 3.7% | 3.7% invest | TVA 3.7% | Acquisti | Switzerland VAT Form: grid 405  
TVA 3.7% sur invest. et autres ch. (Incl. TS) | 3.7% | 3.7% invest. Incl. | TVA 3.7% | Acquisti | Switzerland VAT Form: grid 405  
TVA due a 7.7% (TN) | 7.7% | 7.7% | TVA 7.7% | Vendite | Switzerland VAT Form: grid 302 base, Switzerland VAT Form: grid 302 tax  
TVA due à 7.7% (Incl. TN) | 7.7% | 7.7% Incl. | TVA 7.7% | Vendite | Switzerland VAT Form: grid 302 base, Switzerland VAT Form: grid 302 tax  
TVA due à 3.7% (TS) | 3.7% | 3.7% | TVA 3.7% | Vendite | Switzerland VAT Form: grid 342 base, Switzerland VAT Form: grid 342 tax  
TVA due a 3.7% (Incl. TS) | 3.7% | 3.7% Incl. | TVA 3.7% | Vendite | Switzerland VAT Form: grid 342 base, Switzerland VAT Form: grid 342 tax  
  
If you have questions or remarks, please contact our support using odoo.com/help.

Suggerimento

Don’t forget to update your fiscal positions. If you have a version 11.1 (or higher), there is nothing to do. Otherwise, you will also have to update your fiscal positions accordingly.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/finance/fiscal_localizations/switzerland.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](thailand.html "Thailandia") |
  * [precedente](spain.html "Spagna") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Svizzera


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