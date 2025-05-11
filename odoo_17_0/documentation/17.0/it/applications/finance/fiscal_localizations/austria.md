# Austria — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](belgium.html "Belgio") |
  * [precedente](australia.html "Australia") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Austria



# Austria¶

## Configurazione¶

[Install](../../general/apps_modules.html#general-install) the following modules to get all the features of the Austrian localization.

Nome | Nome tecnico | Descrizione  
---|---|---  
Austria - Accounting | `l10n_at` | Default [fiscal localization package](../fiscal_localizations.html#fiscal-localizations-packages).  
Austria - Accounting Reports | `l10n_at_reports` | Adds localized versions of financial reports  
Austrian SAF-T Export | `l10n_at_saft` | Adds the SAF-T export.  
  
## Rapporti finanziari¶

The following localized reports are available:

>   * Balance sheet according to [§ 224 UGB](https://www.ris.bka.gv.at/NormDokument.wxe?Abfrage=Bundesnormen&Gesetzesnummer=10001702&Artikel=&Paragraf=224&Anlage=&Uebergangsrecht=)
> 
>   * Profit and loss according to [§ 231 UGB](https://www.ris.bka.gv.at/NormDokument.wxe?Abfrage=Bundesnormen&Gesetzesnummer=10001702&Artikel=&Paragraf=231&Anlage=&Uebergangsrecht=) (Gesamtkostenverfahren)
> 
> 


Vedi anche

[Accounting reporting documentation](../accounting/reporting.html)

## SAF-T (Standard Audit File for Tax)¶

The Austrian tax office may request a SAF-T. The Austrian SAF-T Export module allows exporting the report in XML format.

### Configurazione¶

This section explains how to configure the database to ensure all the information required by the SAF-T is available. If anything is missing, a warning message listing which information is needed will be displayed during the export.

#### Informazioni aziendali¶

Open the database Settings. Under the Companies section, click Update Info and ensure the following fields are correctly filled in:

  * Address, by providing at least the following information:

    * Street

    * City

    * ZIP

    * Country

  * Phone

  * Company ID by providing your company’s tax ID

  * Tax ID by providing, if you have one, your UID-Nummer (including the country prefix)




##### Contact person¶

At least one **contact person** must be linked to your company in the Contacts app, and:

>   * Ensure the contact type is set to Individual.
> 
>   * Select your company in the Company name field.
> 
>   * Provide at least one phone number using the Phone or Mobile field.
> 
> 


#### Customer and supplier information¶

Using the Contacts app, fill in the Address of any partner that appears in your invoices, vendor bills, or payments.

For partners that are companies, fill in the VAT number (including the country prefix) in the Tax ID field.

#### Accounting settings¶

Go to Accounting ‣ Configuration ‣ Settings. Under the Austrian localization section, fill in the following fields:

  * ÖNACE-Code

  * Profit Assessment Method




Vedi anche

[ÖNACE information on the Austrian Economic Chambers website](https://www.wko.at/service/zahlen-daten-fakten/oenace.html)

#### Chart of accounts mapping¶

The Austrian SAF-T specifications define a chart of accounts (COA). All relevant accounts for the SAF-T export must be annotated with a fitting account from this COA.

The needed mapping information is supplied by adding tags to the accounts. For example, adding the `1000` tag to an account maps it (virtually) to the SAF-T COA account with the code `1000`. Any number can be used as long as there is an account in the SAF-T COA with that code.

The Austria - Accounting module adds a tag for each SAF-T COA account. Furthermore, it automatically maps many accounts from the default Austrian COA.

You can try exporting the SAF-T report to check if there are unmapped accounts (or mapped to multiple SAF-T accounts). A warning will be displayed if there is any issue with your configuration or the mapping. Clicking View Problematic Accounts lets you view them.

Vedi anche

[Chart of accounts documentation](../accounting/get_started/chart_of_accounts.html)

### Exporting the SAF-T report¶

To export the SAF-T report, go to Accounting ‣ Reports ‣ General Ledger. Click the right side of the PDF button and select SAF-T.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/fiscal_localizations/austria.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](belgium.html "Belgio") |
  * [precedente](australia.html "Australia") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Austria


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
  *[EDI]: Electronic Data Interchange
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