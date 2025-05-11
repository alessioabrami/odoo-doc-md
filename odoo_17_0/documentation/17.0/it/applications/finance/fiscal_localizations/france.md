# Francia — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](germany.html "Germania") |
  * [precedente](egypt.html "Egitto") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Francia



# Francia¶

## Moduli¶

The following modules related to the French localization are available:

Nome | Nome tecnico | Descrizione  
---|---|---  
France - Accounting | `l10n_fr` | French [fiscal localization package](../fiscal_localizations.html#fiscal-localizations-packages) that applies only to companies based in mainland France and doesn’t include DOM-TOMs.  
France - Accounting Reports | `l10n_fr_reports` | Export of the French VAT report, which can be sent to the DGFiP, an OGA, or a professional accountant.  
France - Payroll with Accounting | `l10n_fr_hr_payroll_account` | Includes the necessary accounting data for the French payroll rules.  
France - Factur-X integration with Chorus Pro | `l10n_fr_facturx_chorus_pro` | Adds fields needed for submitting invoices to Chorus Pro.  
France - FEC Export | `l10n_fr_fec` | Generates the FEC file as defined by the [Decree of July 29, 2013](http://legifrance.gouv.fr/eli/arrete/2013/7/29/BUDE1315492A/jo/texte).  
France - FEC Import | `l10n_fr_fec_import` | Import of standard FEC files, useful for importing accounting history.  
France - Adding Mandatory Invoice Mentions (Decree no. 2022-1299) | `l10n_fr_invoice_addr` | Adds address fields required to comply with [Decree 2022-1299](https://www.legifrance.gouv.fr/jorf/id/JORFTEXT000046383394).  
France - VAT Anti-Fraud Certification for Point of Sale (CGI 286 I-3 bis) | `10n_fr_pos_cert` | Point of Sale VAT anti-fraud certification  
  
Nota

The localization’s core modules are installed automatically with the localization. The rest can be manually [installed](../../general/apps_modules.html).

## Localization overview¶

The French localization package ensures compliance with French fiscal and accounting regulations. It includes tools for managing taxes, fiscal positions, reporting, and a predefined chart of accounts tailored to France’s standards.

The French localization package provides the following key features to ensure compliance with local fiscal and accounting regulations:

  * [Piano dei conti](../accounting/get_started/chart_of_accounts.html): a predefined structure tailored to French accounting standards

  * [Posizioni di bilancio (mappatura fiscale e contabile)](../accounting/taxes/fiscal_positions.html): automated tax adjustments based on customer or supplier registration status

  * [Taxes](../accounting/taxes.html): pre-configured tax rates, including standard VAT, zero-rated, and exempt options

  * [Payroll](../../hr/payroll.html)

  * Reporting




### Rendiconto¶

[Installing](../../general/apps_modules.html) the France - Accounting (`l10n_fr`) module gives access to some accounting reports specific to France, such as:

  * Bilan comptable (FR) (Balance Sheet)

  * Compte de résultats (FR) (Profit and Loss)

  * Rapport de taxes (FR) (Tax Report)




## Contabilità¶

### E-Invoicing¶

The [Chorus Pro](https://portail.chorus-pro.gouv.fr/aife_csm) portal, managed by the AIFE (Agence pour l’Informatique financière de l’État), is the official platform for submitting electronic invoices to French public entities. It allows businesses to send and manage invoices, track their processing status, and access payment updates. Since January 2020, electronic invoicing has been mandatory for all business-to-government (B2G) transactions in France. Odoo supports integration with Chorus Pro to submit invoices generated in Odoo.

#### Configurazione¶

To send invoices to Chorus Pro, the following configuration is required:

  1. [Install](../../general/apps_modules.html) the France - Factur-X integration with Chorus Pro (`l10n_fr_facturx_chorus_pro`) module.

  2. [Register](../accounting/customer_invoices/electronic_invoicing.html#e-invoicing-peppol-registration) with Peppol, as invoices are sent from Odoo to Chorus Pro via the [Peppol](../accounting/customer_invoices/electronic_invoicing.html#e-invoicing-peppol) network.

  3. If you don’t already have a Chorus Pro account, go to the [Chorus Pro](https://portail.chorus-pro.gouv.fr/aife_csm) page, click Créer un compte, and create one.

  4. Configure the relevant customers” contact form.




Vedi anche

[Chorus Pro documentation](https://portail.chorus-pro.gouv.fr/aife_documentation)

##### Clienti¶

To submit invoices to Chorus Pro, configure the relevant customers” contact form as follows:

  1. Verify the Country and Tax ID fields are filled out.

  2. In the Sales & Purchase tab, ensure the SIRET field is completed.

  3. In the Accounting tab, fill in the following fields in the Electronic Invoicing section:

     * Format: Select BIS Billing 3.0.

     * Peppol e-address (EAS): Select 0009 - SIRET-CODE.

     * Peppol Endpoint: Type `11000201100044`, the reference used by Chorus Pro.




#### Sending invoices to Chorus Pro¶

To send invoices to Chorus Pro, follow these steps:

  1. Go to Accounting ‣ Customers ‣ Invoices and open or create the invoice.

  2. Make sure the following fields are filled in the Other Info tab:

     * Buyer Reference: Service Exécutant in Chorus Pro

     * Contract Reference: Numéro de Marché in Chorus Pro

     * Purchase Order Reference: Engagement Juridique in Chorus Pro

  3. Confirm the invoice.

  4. Click Send & Print and, in the Send window, enable Peppol Bis Billing 3.0.

  5. Click Send & Print.




Once the invoice is sent, the Peppol status of the invoice is updated to Done.

Vedi anche

[Peppol](../accounting/customer_invoices/electronic_invoicing.html#e-invoicing-peppol)

### FEC - Fichier des Écritures Comptables¶

An FEC Fichier des Écritures Comptables audit file contains all the accounting data and entries recorded in all the accounting journals for a financial year. The entries in the file must be arranged in chronological order. Since January 2014, every French company is required to produce and transmit this file upon request by the tax authorities for audit purposes.

#### Improtazione FEC¶

[Install](../../general/apps_modules.html) the France - FEC Import (`l10n_fr_fec_import`) module to import FEC files from other software.

To enable this feature, go to Accounting ‣ Configuration ‣ Settings. In the Accounting Import section, click __ Import and Import FEC. Then, in the FEC Import window, upload the FEC file and click Import.

Nota

Importing FEC files from different years requires no particular actions or computations. However, if multiple files contain RAN Reports à Nouveaux with the starting balance for the year, these entries are automatically marked as unnecessary in Odoo and may need to be deleted.

##### Formati file¶

Nota

  * FEC files must be in CSV format, as XML format is not supported.

  * The FEC CSV file is a plain text file structured as a data table. The first line serves as the header, defining the list of fields for each entry, and each following line represents a single accounting entry without any specific order.




FEC files must comply with the following technical specifications:

  * **Encoding** : UTF-8, UTF-8-SIG and iso8859_15.

  * **Separator** : any of these: `;` or `|` or `,` or `TAB`.

  * **Line terminators** : both CR+LF (`\r\n`) and LF (`\n`) character groups are supported.

  * **Date format** : `%Y%m%d`




##### Fields description and use¶

# | Field name | Descrizione | Usa | Formatta  
---|---|---|---|---  
01 | JournalCode | Codice registro | `journal.code` and `journal.name` if `JournalLib` is not provided | Alphanumeric  
02 | JournalLib | Etichetta registro | `journal.name` | Alphanumeric  
03 | EcritureNum | Numbering specific to each journal sequence number of the entry | `move.name` | Alphanumeric  
04 | EcritureDate | Accounting entry Date | `move.date` | Date (yyyyMMdd)  
05 | CompteNum | Numero conto | `account.code` | Alphanumeric  
06 | CompteLib | Etichetta conto | `account.name` | Alphanumeric  
07 | CompAuxNum | Secondary account Number (accepts null) | `partner.ref` | Alphanumeric  
08 | CompAuxLib | Secondary account Label (accepts null) | `partner.name` | Alphanumeric  
09 | PieceRef | Document Reference | `move.ref` and `move.name` if `EcritureNum` is not provided | Alphanumeric  
10 | PieceDate | Document Date | `move.date` | Date (yyyyMMdd)  
11 | EcritureLib | Account entry Label | `move_line.name` | Alphanumeric  
12 | Dare | Debit amount | `move_line.debit` | Mobile  
13 | Avere | Credit amount (Field name «Crédit» is not allowed) | `move_line.credit` | Mobile  
14 | EcritureLet | Accounting entry cross reference (accepts null) | `move_line.fec_matching_number` | Alphanumeric  
15 | DateLet | Accounting entry date (accepts null) | unused | Date (yyyyMMdd)  
16 | ValidDate | Accounting entry validation date | unused | Date (yyyyMMdd)  
17 | Montantdevise | Currency amount (accepts null) | `move_line.amount_currency` | Mobile  
18 | Idevise | Currency identifier (accepts null) | `currency.name` | Alphanumeric  
  
These two fields appear in the same order as the others, replacing them.

12 | Montant | Importo | `move_line.debit` or `move_line.credit` | Mobile  
---|---|---|---|---  
13 | Sens | Can be «C» for Credit or «D» for Debit | determines `move_line.debit` or `move_line.credit` | Carattere  
  
##### Implementation details¶

The following accounting entities are imported from the FEC files: **Accounts, Journals, Partners** , and **Moves**. The module automatically determines the encoding, line terminator, and separator used in the file. Next, a check is performed to ensure that each line has the correct number of fields matching the header. If the check is successful, the entire file is read, stored in memory, and scanned. Accounting entities are then imported one type at a time in the following order.

###### Conti¶

Each accounting entry is associated with an account identified by the CompteNum field.

###### Code matching¶

If an account with the same code already exists, the existing one is used rather than creating a new one. In Odoo, account numbers follow the default digit length of the fiscal localization. Since the FEC module is tied to the French localization, the default account length is 6 digits. This means that trailing zeros in account codes are removed, and the comparison between the account codes in the FEC file and those already in Odoo is made based only on the first six digits of the codes.

Example

The account code `65800000` in the file is matched with an existing `658000` account in Odoo, and the existing account is used instead of creating a new one.

###### Reconcilable flag¶

An account is technically flagged as _reconcilable_ if the first line in which it appears has the EcritureLet field filled out, indicating that the accounting entry will be reconciled with another one.

Nota

The field can be left empty on the line, but the entry must still be reconciled with an unrecorded payment. The account is flagged as reconcilable once the import of the move lines requires it.

###### Account type and templates matching¶

Since the account **type** is not specified in the FEC format, **new** accounts are created with the default type Current Assets. After the import process, they are matched against the installed Chart of Account templates. The _reconcile_ flag is also determined this way.

The matching is performed by comparing the left-most digits, starting with all digits, followed by 3 digits, and then 2 digits.

Example

Nome | Codice | Full comparison | 3-digits comparison | 2-digits comparison  
---|---|---|---|---  
Modello | `400000` | `400000` | `400` | `40`  
CompteNum | `40100000` | `40100000` | `401` | `40`  
**Result** |  |  |  | Match **found**  
  
The account type is then flagged as payable and reconcilable based on the account template.

###### Registri¶

Journals are checked against the existing ones in Odoo to avoid duplicates, even when importing multiple FEC files.

If a journal with the same code already exists, the existing journal is used instead of creating a new one.

New journals have the prefix FEC- added to their name. For example, ACHATS becomes FEC-ACHATS.

Nota

Journals are _not_ archived, allowing the user to manage them as desired.

###### Journal type determination¶

The journal type is not specified in the format (similar to the accounts) and is initially created with the default type general.

At the end of the import process, the journal type is determined based on the following rules regarding related moves and accounts:

  * bank: Moves in these journals always include a line (debit or credit) impacting a liquidity account.

cash / bank can be interchanged, so bank is assigned when this condition is met.

  * sale: Moves in these journals mostly have debit lines on receivable accounts and credit lines on tax income accounts.

Sale refund journal items are debit/credit inverted.

  * purchase: Moves in these journals mostly have credit lines on payable accounts and debit lines on expense accounts.

Purchase refund journal items are debit/credit inverted.

  * general: Used for everything else.




Nota

  * A minimum of three moves is required to identify the journal type.

  * A threshold of 70% of the moves must meet the criteria for a journal type to be determined.




Example

Suppose we are analyzing the moves that share a certain journal_id.

Movimenti | Numero | Percentuale  
---|---|---  
that have a sale account line and no purchase account line | 0 | 0  
that have a purchase account line and no sale account line | 1 | 25%  
that have a liquidity account line | 3 | **75%**  
**Total** | 4 | 100%  
  
The journal type would be bank, because the bank’s move percentage (75%) exceeds the threshold (70%).

###### Contatti¶

Each contact keeps its Reference from the CompAuxNum field.

Nota

These fields are searchable based on previous FEC imports for fiscal/audit purposes.

Suggerimento

Similar and potential duplicate contacts can be merged using the Data Cleaning App.

###### Movimenti¶

Entries are posted and reconciled immediately upon submission, with the EcritureLet field used to match the entries.

The EcritureNum field represents the name of the moves, but it may sometimes be left empty. In such cases, the PieceRef field is used instead.

###### Rounding issues¶

A rounding tolerance is applied based on currency precision for debit and credit amounts (i.e., 0.01 for EUR). If the difference falls under this tolerance, a new line is added to the move, called Import rounding difference, targeting the following accounts:

  * `658000` Charges diverses de gestion courante, for added debits

  * `758000` Produits divers de gestion courante, for added credits




###### Missing move name¶

If the the EcritureNum field is not filled out and PieceRef field is not suited to determine the move name (it may be used as an accounting move line reference), it becomes impossible to identify which lines should be grouped into a single move, and effectively preventing the creation of balanced moves.

In such cases, a final attempt is made to group all lines by the same journal and date (JournalLib, EcritureDate). If this grouping generates balanced moves (sum(credit) - sum(debit) = 0), then each different combination of journal and date creates a new move.

Example

`ACH` \+ `2021/05/01` –> new move on journal `ACH` with name `20210501`.

If this attempt fails, an error message is displayed, listing all the move lines that are considered unbalanced.

###### Contact information¶

If a line includes contact information, it is copied to the accounting move itself, provided the targeted journal is of type payable or receivable.

#### FEC Export¶

To download the FEC, [install](../../general/apps_modules.html) the France - FEC Export`(`l10n_fr_fec) module, then go to Accounting ‣ Reporting ‣ FEC. In the FEC window, fill in the following fields:

  * Start Date

  * End Date

  * Test File: Enable this option to test the FEC file generation.

  * Excluded Journals




Then, click Generate.

Vedi anche

  * [Official Technical Specification (fr)](https://www.legifrance.gouv.fr/codes/article_lc/LEGIARTI000027804775)

  * [Test-Compta-Demat (Official FEC Testing tool)](https://github.com/DGFiP/Test-Compta-Demat)




## Point of sale¶

### VAT anti-fraud certification¶

Since January 2018, new anti-fraud legislation has been in effect in France and its overseas territories (DOM-TOM). This legislation establishes specific requirements for the integrity, security, storage, and archiving of sales data. Odoo complies with these legal requirements by providing a module and a downloadable certificate of conformity.

Anti-fraud cash register software, such as Odoo (CGI art. 286, I. 3° bis), is required for companies taxable in France or DOM-TOM, where some customers are private individuals (B2C). This rule applies to all company sizes, but auto-entrepreneurs exempt from VAT are unaffected.

Vedi anche

  * [Frequently Asked Questions](https://www.economie.gouv.fr/files/files/directions_services/dgfip/controle_fiscal/actualites_reponses/logiciels_de_caisse.pdf)

  * [Official Statement](http://bofip.impots.gouv.fr/bofip/10691-PGP.html?identifiant=BOI-TVA-DECLA-30-10-30-20160803)

  * [Item 88 of Finance Law 2016](https://www.legifrance.gouv.fr/affichTexteArticle.do?idArticle=JORFARTI000031732968&categorieLien=id&cidTexte=JORFTEXT000031732865)




#### Odoo certification¶

The tax administration requires all companies to provide a certificate of conformity confirming that their software complies with anti-fraud legislation. In case of non-compliance, a €7,500 fine may be imposed.

Nota

This [certificate](https://www.odoo.com/my/contract/french-certification/) is granted by Odoo SA to Odoo Enterprise users.

To get the certification, follow these steps:

  1. [Install](../../general/apps_modules.html) the France - VAT Anti-Fraud Certification for Point of Sale (CGI 286 I-3 bis) (`l10n_fr_pos_cert`) module.

  2. Set the Country field on the [company record](../../general/companies.html) to encrypt entries for the inalterability check.

  3. Download the mandatory [certificate of conformity](https://www.odoo.com/my/contract/french-certification/) delivered by Odoo SA.




#### Anti-fraud features¶

The anti-fraud module introduces the following features:

  * Inalterability

  * Security

  * Storage




##### Inalterability¶

All methods to cancel or modify key data in POS orders, invoices, and journal entries are deactivated for companies located in France or any DOM-TOM.

Nota

In a multi-company environment, only the documents of such companies are impacted.

##### Sicurezza¶

To ensure inalterability, every order or journal entry is encrypted upon validation. This number (or hash) is calculated from the document’s key data and the hash of the precedent documents. The module introduces an interface to test the data’s inalterability. The test will fail if any information is modified on a document after its validation. The algorithm recomputes all the hashes and compares them against the initial ones. In case of failure, the system points out the first corrupted document recorded in the system.

Only users with [administrator](../../general/users/access_rights.html) access rights can initiate the inalterability check:

  * For POS orders, go to Point of Sales ‣ Reporting ‣ POS Inalterability Check;

  * For invoices or journal entries, go to Invoicing/Accounting ‣ Reporting ‣ POS Inalterability Check.




##### Stoccaggio¶

The system also processes automatic sales closings daily, monthly, and annually. Such closings compute the sales total for the period and the cumulative grand totals from the very first sales entry recorded in the system.

To access closings, either go to Point of Sales ‣ Reporting ‣ Sales Closings or Invoicing/Accounting ‣ Reporting ‣ Sales Closings.

Nota

  * Closings compute the totals for journal entries of sales journals (Journal Type = Sales).

  * For multi-companies environments, such closings are performed by company.

  * POS orders are posted as journal entries at the closing of the POS session. Closing a POS session can be done anytime. To prompt users to do it daily, the module prevents them from resuming a session that was opened more than 24 hours ago. Such a session must be closed before selling again.

  * A period’s total is computed from all the journal entries posted after the previous closing of the same type, regardless of their posting date. Recording a new sales transaction for a period already closed will be counted in the very next closing.




Suggerimento

For test & audit purposes, closings can be manually generated in [developer mode](../../general/developer_mode.html#developer-mode). To do so, go to Settings ‣ Technical ‣ Scheduled Actions. In the scheduled actions list view, open the desired Sale Closing action and click Run manually.

#### Responsabilità¶

Uninstalling this module will reset the security hashes. This means the system will no longer guarantee the integrity of the past data.

Users are responsible for their Odoo system and must operate it carefully. Modifying source code responsible for ensuring data integrity is not allowed.

Odoo is not responsible for any issues with this module’s functionality if caused by uncertified third-party applications.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/fiscal_localizations/france.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](germany.html "Germania") |
  * [precedente](egypt.html "Egitto") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Francia


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
  *[FPS]: Faster Payment System
  *[ADW]: Average Daily Wage
  *[SII]: Servicio de Impuestos Internos
  *[CAFs]: Folio Authorization Code
  *[DTE]: Documentos Tributarios Electrónicos
  *[RUT]: Rol Único Tributario
  *[CAF]: Folio Authorization Code
  *[SII’s]: Servicio de Impuestos Internos
  *[PPM]: Provisional Monthly Payments rate