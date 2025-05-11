# Arabia Saudita — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](singapore.html "Singapore") |
  * [precedente](philippines.html "Filippine") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Arabia Saudita



# Arabia Saudita¶

## Configurazione¶

[Install](../../general/apps_modules.html#general-install) the following modules to get all the features of the Saudi Arabian localization:

Nome | Nome tecnico | Descrizione  
---|---|---  
Arabia Saudita - Contabilità | `l10n_sa` | [Pacchetto localizzazione fiscale predefinito](../fiscal_localizations.html#fiscal-localizations-packages)  
Arabia Saudita - Fatturazione elettronica | `l10n_sa_edi` | ZATCA e-invoices implementation  
Arabia Saudita-Punto Vendita | `l10n_sa_pos` | Point of Sale compliance  
  
## ZATCA e-invoices¶

The ZATCA e-invoicing system is designed to streamline and digitize the invoicing process for businesses operating in Saudi Arabia.

Vedi anche

[ZATCA e-invoicing page](https://zatca.gov.sa/en/E-Invoicing/Pages/default.aspx)

### Informazioni aziendali¶

Go to Settings ‣ General Settings ‣ Companies, click Update info, and ensure the following company information is complete and up-to-date.

  * The full Company Name.

  * All relevant Address fields, including the Building Number and Plot Identification (four digits each).

  * Select an enterprise Identification Scheme. It is recommended to use the Commercial Registration Number.

  * Enter the Identification Number for the selected Identification Scheme.

  * The VAT number.

  * Ensure the Currency is set to SAR.




Nota

It is also necessary to fill out similar information for partner companies.

### Modalità di simulazione¶

Importante

It is strongly recommended to thoroughly test all invoicing workflows using the Fatoora **simulation** portal first, as **any** invoice submitted to the regular Fatoora portal will be accounted for, which could lead to fines and penalties.

#### Fatoora simulation portal¶

Log in on the [Fatoora portal](https://fatoora.zatca.gov.sa/) using the company’s ZATCA credentials. Then, click the Fatoora Simulation Portal button to switch to the simulation portal.

Vedi anche

[ZACTA Fatoora portal user manual version 3 (May 2023)](https://zatca.gov.sa/en/E-Invoicing/Introduction/Guidelines/Documents/Fatoora_Portal_User_Manual_English.pdf)

#### ZATCA API integration¶

On Odoo, go to Accounting ‣ Configuration ‣ Settings. Under ZATCA API Integration, select the Simulation (Pre-Production) API mode and click Save.

#### Sales journals¶

Each sales journal on Odoo needs to be configured. To do so, go to Accounting ‣ Configuration ‣ Journals, open any sales journal (e.g., Customer Invoices), and go to the ZATCA tab. Once there, enter any Serial Number to identify the journal.

Nota

The same serial number can be used for all of the company’s sales journals.

Next, click Onboard Journal. In the dialog box, providing an OTP code is required. To retrieve it, open the [Fatoora simulation portal](https://fatoora.zatca.gov.sa/), click Onboard New Solution Unit/Device, choose the number of OTP codes to generate (one per journal to configure), and click Generate OTP Code. Copy an OTP code, it into the dialog box on Odoo, and click Request.

Nota

OTP codes expire after one hour.

Suggerimento

If any issue occurs during onboarding, click Regenerate CSR to start again.

#### Testing¶

When confirming an invoice, there is now an option to process the invoice, sending it directly the Fatoora simulation portal. Odoo displays the portal’s response after each submission. Only rejected invoices can be reset to draft and edited on Odoo. Furthermore, at the end of each day, Odoo sends all unprocessed invoices to the portal.

Suggerimento

  * Testing all invoicing workflows, preferably with real invoices and for a reasonable amount of time, is recommended.

  * Compare the invoices received statistics page on the Fatoora simulation portal with the list of invoices on Odoo to ensure both align.




#### Imposte¶

When using a **0% tax** in a customer invoice, it is necessary to specify the reason behind such a rate. To configure taxes, go to Accounting ‣ Configuration ‣ Settings ‣ Taxes, and open the tax to edit. Under the Advanced Options, select an Exemption Reason Code and click Save.

When using **retention** or **withholding an amount** in a customer invoice, the tax used to retain the amount needs to be specified.

### Modalità di produzione¶

When ready for production, change the API mode to Production and click Save.

Avvertimento

Setting the API mode to Production is **irreversible**.

The sales journals initially linked to the simulation portal now needs to be linked to the regular portal. To do so, onboard the journals again, ensuring to use the regular [Fatoora portal](https://fatoora.zatca.gov.sa/) this time.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/fiscal_localizations/saudi_arabia.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](singapore.html "Singapore") |
  * [precedente](philippines.html "Filippine") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Arabia Saudita


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