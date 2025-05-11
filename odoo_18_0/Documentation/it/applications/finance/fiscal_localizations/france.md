# Francia — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](germany.html "Germania") |
  * [precedente](egypt.html "Egitto") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Francia



# Francia¶

Vedi anche

[Documentation on e-invoicing’s legality and compliance in France](../accounting/customer_invoices/electronic_invoicing/france.html)

## FEC - Fichier des Écritures Comptables¶

An FEC Fichier des Écritures Comptables audit file contains all the accounting data and entries recorded in all the accounting journals for a financial year. The entries in the file must be arranged in chronological order.

Since January 1st, 2014, every French company is required to produce and transmit this file upon request by the tax authorities for audit purposes.

### FEC import¶

To make the onboarding of new users easier, Odoo Enterprise’s French [fiscal localization package](../fiscal_localizations.html#fiscal-localizations-packages) includes the **FEC Import** feature (module name: `l10n_fr_fec_import`), which enables the import of existing FEC files from older software.

To enable this feature, go to Accounting ‣ Configuration ‣ Settings ‣ Accounting Import, enable **FEC Import** , and _Save_.

Next, go to Accounting ‣ Configuration ‣ FEC Import, upload your FEC file, and click on _Import_.

Nota

Importing FEC files from different year takes no particular action or computation.

Should multiple files contain any «Reports à Nouveaux» (RAN) with the starting balance of the year, you might need to cancel those entries in the User Interface. Odoo makes those entries (RAN) useless.

#### Formati file¶

FEC files can only be in CSV format, as the XML format is not supported.

Nota

The FEC CSV file has a plain text format representing a data table, with the first line being a header and defining the list of fields for each entry, and each following line representing one accounting entry, in no predetermined order.

Our module expects the files to meet the following technical specifications:

  * **Encoding** : UTF-8, UTF-8-SIG and iso8859_15.

  * **Separator** : any of these: `;` or `|` or `,` or `TAB`.

  * **Line terminators** : both CR+LF (`\r\n`) and LF (`\n`) character groups are supported.

  * **Date format** : `%Y%m%d`




#### Fields description and use¶

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
  
These two fields can be found in place of the others in the sence above.

12 | Montant | Importo | `move_line.debit` or `move_line.credit` | Mobile  
---|---|---|---|---  
13 | Sens | Can be «C» for Credit or «D» for Debit | determines `move_line.debit` or `move_line.credit` | Carattere  
  
#### Implementation details¶

The following accounting entities are imported from the FEC files: **Accounts, Journals, Partners** , and **Moves**.

Our module determines the encoding, the line-terminator character, and the separator that are used in the file.

A check is then performed to see if every line has the correct number of fields corresponding to the header.

If the check passes, then the file is read in full, kept in memory, and scanned. Accounting entities are imported one type at a time, in the following order.

##### Conti¶

Every accounting entry is related to an account, which should be determined by the field `CompteNum`.

##### Code matching¶

Should a similar account code already be present in the system, the existing one is used instead of creating a new one.

Accounts in Odoo generally have a number of digits that are default for the fiscal localization. As the FEC module is related to the French localization, the default number of relevant digits is 6.

This means that the account codes the trailing zeroes are right-trimmed, and that the comparison between the account codes in the FEC file and the ones already existing in Odoo is performed only on the first six digits of the codes.

Example

The account code `65800000` in the file is matched against an existing `658000` account in Odoo, and that account is used instead of creating a new one.

##### Reconcilable flag¶

An account is technically flagged as _reconcilable_ if the first line in which it appears has the `EcritureLet` field filled out, as this flag means that the accounting entry is going to be reconciled with another one.

Nota

In case the line somehow has this field not filled out, but the entry still has to be reconciled with a payment that hasn’t yet been recorded, this isn’t a problem anyway; the account is flagged as reconcilable as soon as the import of the move lines requires it.

##### Account type and templates matching¶

As the **type** of the account is not specified in the FEC format, **new** accounts are created with the default type _Current Assets_ and then, at the end of the import process, they are matched against the installed Chart of Account templates. Also, the _reconcile_ flag is also computed this way.

The match is done with the left-most digits, starting by using all digits, then 3, then 2.

Example

Nome | Codice | Full comparison | 3-digits comparison | 2-digits comparison  
---|---|---|---|---  
Modello | `400000` | `400000` | `400` | `40`  
CompteNum | `40100000` | `40100000` | `401` | `40`  
**Result** |  |  |  | Match **found**  
  
The type of the account is then flagged as _payable_ and _reconcilable_ as per the account template.

##### Registri¶

Journals are also checked against those already existing in Odoo to avoid duplicates, also in the case of multiple FEC files imports.

Should a similar journal code already be present in the system, the existing one is used instead of creating a new one.

New journals have their name prefixed by the string `FEC-`.

Example

`ACHATS` -> `FEC-ACHATS`

The journals are _not_ archived, the user is entitled to handle them as he wishes.

##### Journal type determination¶

The journal type is also not specified in the format (as per the accounts) and therefore it is at first created with the default type `general`.

At the end of the import process, the type is determined as per these rules regarding related moves and accounts:

  * `bank`: Moves in these journals always have a line (debit or credit) impacting a liquidity account.

`cash` / `bank` can be interchanged, so `bank` is set everywhere when this condition is met.

  * `sale`: Moves in these journals mostly have debit lines on receivable accounts and credit lines on tax income accounts.

Sale refund journal items are debit/credit inverted.

  * `purchase`: Moves in these journals mostly have credit lines on payable accounts and debit lines on expense accounts.

Purchase refund journal items are debit/credit inverted.

  * `general`: for everything else.




Nota

  * A minimum of three moves is necessary for journal type identification.

  * A threshold of 70% of moves must correspond to a criteria for a journal type to be determined.




Example

Suppose we are analyzing the moves that share a certain `journal_id`.

Movimenti | Numero | Percentuale  
---|---|---  
that have a sale account line and no purchase account line | 0 | 0  
that have a purchase account line and no sale account line | 1 | 25%  
that have a liquidity account line | 3 | **75%**  
**Total** | 4 | 100%  
  
The journal `type` would be `bank`, because the bank moves percentage (75%) exceeds the threshold (70%).

##### Partner¶

Each partner keeps its `Reference` from the field `CompAuxNum`.

Nota

These fields are searchable, in line with former FEC imports on the accounting expert’s side for fiscal/audit purposes.

Suggerimento

Users can merge partners with the Data Cleaning App, where Vendors and Customers or similar partner entries may be merged by the user, with assistance from the system that groups them by similar entries.

##### Movimenti¶

Entries are immediately posted and reconciled after submission, using the `EcritureLet` field to do the matching between the entries themselves.

The `EcritureNum` field represents the name of the moves. We noticed that sometimes it may not be filled out. In this case, the field `PieceRef` is used.

##### Rounding issues¶

There is a rounding tolerance with a currency-related precision on debit and credit (i.e., 0.01 for EUR). Under this tolerance, a new line is added to the move, named _Import rounding difference_ , targeting the accounts:

  * `658000` Charges diverses de gestion courante, for added debits

  * `758000` Produits divers de gestion courante, for added credits




##### Missing move name¶

Should the `EcritureNum` not be filled out, it may also happen that the `PieceRef` field is also not suited to determine the move name (it may be used as an accounting move line reference) leaving no way to actually find which lines are to be grouped in a single move, and effectively impeding the creation of balanced moves.

One last attempt is made, grouping all lines from the same journal and date (`JournalLib`, `EcritureDate`). Should this grouping generate balanced moves (sum(credit) - sum(debit) = 0), then each different combination of journal and date creates a new move.

Example

`ACH` \+ `2021/05/01` –> new move on journal `ACH` with name `20210501`.

Should this attempt fail, the user is prompted an error message with all the move lines that are supposedly unbalanced.

##### Partner information¶

If a line has the partner information specified, the information is copied to the accounting move itself if the targeted Journal is of type _payable_ or _receivable_.

### Esporta¶

If you have installed the French [fiscal localization package](../fiscal_localizations.html#fiscal-localizations-packages), you should be able to download the FEC. To do so, go to Accounting ‣ Reporting ‣ France ‣ FEC.

Suggerimento

If you do not see the submenu **FEC** , go to Apps, remove the _Apps_ filter, then search for the module named **France-FEC** and make sure it is installed.

Vedi anche

  * [Official Technical Specification (fr)](https://www.legifrance.gouv.fr/codes/article_lc/LEGIARTI000027804775)

  * [Test-Compta-Demat (Official FEC Testing tool)](https://github.com/DGFiP/Test-Compta-Demat)




## French accounting reports¶

If you have installed the French Accounting, you will have access to some accounting reports specific to France:

  * Bilan comptable

  * Compte de résultats

  * Plan de Taxes France




## Liasse fiscale¶

The _liasse fiscale_ (tax returns) is a collection of standardized financial documents that businesses must submit annually to the tax authorities. It comprehensively summarizes the company’s financial activities and determines corporate taxes.

[Teledec](https://www.teledec.fr/) is a platform used to prepare and submit tax returns using data from accounting records. To synchronize your accounting data stored in Odoo with Teledec and electronically send your company’s _liasse fiscale_ to the DGFiP (Direction Générale des Finances Publiques), follow these steps:

  1. Teledec account creation

  2. Company registration and fiscal year information

  3. Odoo synchronization




### Teledec account creation¶

To create a Teledec account, access the [Teledec account creation page](https://www.teledec.fr/s-enregistrer) and fill in the Adresse e-mail field with an email address. Choose a secure password, accept the general terms and conditions by checking the box, and click S’enregistrer to save. Then, enter the SIREN number of the company.

Nota

If the account has already been created, click Déjà enregistré? (Already registered).

### Company registration and fiscal year information¶

To register the company on Teledec, go to Vos entreprises (Your companies) and click Enregistrer votre entreprise (Register your company). Make sure to fill in the following company information in the Coordonnées de l’entreprise (Company’s details) and Représentant légal (Legal representative) sections:

  * Nom de l’entreprise: Company’s name.

  * Forme juridique: Select the company’s legal form.

  * Les comptes sont clôturés le: Closing date.

  * Régime d’imposition, choix de la liasse: Select the Tax scheme and tax return option.

  * Adresse du siège social: Head office address.

  * Nom du représentant légal: Legal representative’s name.

  * Agissant en qualité de: Legal representative’s function.

  * Numéro de téléphone: Phone number.




Click Sauvegarder (Save) to display the next step Informations générales sur l’exercice déclaré (General information about the declared fiscal year). Then, fill in information on the financial year, such as the fiscal year start and end dates or the closing date and duration of the previous fiscal period. After saving, the list of documents included in the _liasse fiscale_ is displayed, including both standard tax forms and those customized for the company’s tax return.

Suggerimento

  * The Etat (Status) column shows the progress of the document filing.

  * Click Compléter to fill out a document, then Sauvegarder to save.

  * To print a blank version of the declaration, click Imprimer la déclaration and select the Imprimer la déclaration avec les notices option.




### Odoo synchronization¶

To enable Odoo to automatically fill in the data for the Liasse fiscale, click Autres actions (Other actions) in the top-right corner and select Synchroniser avec un logiciel tiers (Synchronize with third-party software), then Synchroniser cette liasse avec Odoo (Synchronize this _liasse_ with Odoo).

In the Synchroniser cette liasse avec Odoo window, fill in the following information to complete the synchronization:

  * Nom / URL complète de la base de données ODOO: Odoo database name or URL. To provide the full URL of the database, enable Je voudrais donner une url complète hors .odoo.com option.

  * Nom de l’utilisateur: User name associated with the Odoo account.

  * Clé API: [API key](../../../developer/reference/external_api.html#api-external-api-keys) generated by the Odoo instance.




Next, click Importer to synch data from Odoo. In the Confirmation de la synchronisation de liasse avec Odoo window, review the amounts and make any necessary changes. Then click Importer la balance to confirm the synchronization of the _liasse fiscale_ with Odoo and import the balance.

Importante

Clicking Importer la balance may overwrite or alter any manual updates made previously.

To make payment and send the declaration to the tax authorities, click Paiement & envoi de la déclaration.

## Get the VAT anti-fraud certification with Odoo¶

As of January 1st 2018, a new anti-fraud legislation comes into effect in France and DOM-TOM. This new legislation stipulates certain criteria concerning the inalterability, security, storage and archiving of sales data. These legal requirements are implemented in Odoo, version 9 onward, through a module and a certificate of conformity to download.

### Is my company required to use anti-fraud software?¶

Your company is required to use an anti-fraud cash register software like Odoo (CGI art. 286, I. 3° bis) if:

  * You are taxable (not VAT exempt) in France or any DOM-TOM,

  * Some of your customers are private individuals (B2C).




This rule applies to any company size. Auto-entrepreneurs are exempted from VAT and therefore are not affected.

### Get certified with Odoo¶

Getting compliant with Odoo is very easy.

Your company is requested by the tax administration to deliver a certificate of conformity testifying that your software complies with the anti-fraud legislation. This certificate is granted by Odoo SA to Odoo Enterprise users [here](https://www.odoo.com/my/contract/french-certification/). If you use Odoo Community, you should [upgrade to Odoo Enterprise](../../../administration/on_premise/community_to_enterprise.html) or contact your Odoo service provider.

In case of non-conformity, your company risks a fine of €7,500.

To get the certification, just follow the following steps:

  * If you use **Odoo Point of Sale** , [install](../../general/apps_modules.html#general-install) the **France - VAT Anti-Fraud Certification for Point of Sale (CGI 286 I-3 bis)** module by going to Apps, removing the _Apps_ filter, then searching for _l10n_fr_pos_cert_ , and installing the module.

  * Make sure a country is set on your company, otherwise your entries won’t be encrypted for the inalterability check. To edit your company’s data, go to Settings ‣ Users & Companies ‣ Companies. Select a country from the list; Do not create a new country.

  * Download the mandatory certificate of conformity delivered by Odoo SA [here](https://www.odoo.com/my/contract/french-certification/).




Nota

  * To install the module in any system created before December 18th 2017, you should update the modules list. To do so, activate the [developer mode](../../general/developer_mode.html#developer-mode). Then go to the _Apps_ menu and press _Update Modules List_ in the top-menu.

  * In case you run Odoo on-premise, you need to update your installation and restart your server beforehand.

  * If you have installed the initial version of the anti-fraud module (prior to December 18th 2017), you need to update it. The module’s name was _France - Accounting - Certified CGI 286 I-3 bis_. After an update of the modules list, search for the updated module in _Apps_ , select it and click _Upgrade_. Finally, make sure the following module _l10n_fr_sale_closing_ is installed.




### Anti-fraud features¶

The anti-fraud module introduces the following features:

  * **Inalterability** : deactivation of all the ways to cancel or modify key data of POS orders, invoices and journal entries;

  * **Security** : chaining algorithm to verify the inalterability;

  * **Storage** : automatic sales closings with computation of both period and cumulative totals (daily, monthly, annually).




#### Inalterability¶

All the possible ways to cancel and modify key data of paid POS orders, confirmed invoices and journal entries are deactivated, if the company is located in France or in any DOM-TOM.

Nota

If you run a multi-companies environment, only the documents of such companies are impacted.

#### Sicurezza¶

To ensure inalterability, every order or journal entry is encrypted upon validation. This number (or hash) is calculated from the key data of the document as well as from the hash of the precedent documents.

The module introduces an interface to test the data inalterability. If any information is modified on a document after its validation, the test will fail. The algorithm recomputes all the hashes and compares them against the initial ones. In case of failure, the system points out the first corrupted document recorded in the system.

Users with _Manager_ access rights can launch the inalterability check. For POS orders, go to Point of Sales ‣ Reporting ‣ French Statements. For invoices or journal entries, go to Invoicing/Accounting ‣ Reporting ‣ French Statements.

#### Stoccaggio¶

The system also processes automatic sales closings on a daily, monthly and annual basis. Such closings distinctly compute the sales total of the period as well as the cumulative grand totals from the very first sales entry recorded in the system.

Closings can be found in the _French Statements_ menu of Point of Sale, Invoicing and Accounting apps.

Nota

  * Closings compute the totals for journal entries of sales journals (Journal Type = Sales).

  * For multi-companies environments, such closings are performed by company.

  * POS orders are posted as journal entries at the closing of the POS session. Closing a POS session can be done anytime. To prompt users to do it on a daily basis, the module prevents from resuming a session opened more than 24 hours ago. Such a session must be closed before selling again.

  * A period’s total is computed from all the journal entries posted after the previous closing of the same type, regardless of their posting date. If you record a new sales transaction for a period already closed, it will be counted in the very next closing.




Suggerimento

  * For test & audit purposes such closings can be manually generated in the [developer mode](../../general/developer_mode.html#developer-mode).

  * Then go to Settings ‣ Technical ‣ Automation ‣ Scheduled Actions.




### Responsabilità¶

Do not uninstall the module! If you do so, the hashes will be reset and none of your past data will be longer guaranteed as being inalterable.

Users remain responsible for their Odoo instance and must use it with due diligence. It is not permitted to modify the source code which guarantees the inalterability of data.

Odoo absolves itself of all and any responsibility in case of changes in the module’s functions caused by 3rd party applications not certified by Odoo.

### More information¶

You can find more information about this legislation in the following official documents.

Vedi anche

  * [Frequently Asked Questions](https://www.economie.gouv.fr/files/files/directions_services/dgfip/controle_fiscal/actualites_reponses/logiciels_de_caisse.pdf)

  * [Official Statement](http://bofip.impots.gouv.fr/bofip/10691-PGP.html?identifiant=BOI-TVA-DECLA-30-10-30-20160803)

  * [Item 88 of Finance Law 2016](https://www.legifrance.gouv.fr/affichTexteArticle.do?idArticle=JORFARTI000031732968&categorieLien=id&cidTexte=JORFTEXT000031732865)




[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/finance/fiscal_localizations/france.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](germany.html "Germania") |
  * [precedente](egypt.html "Egitto") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
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
  *[SIREN]: Système d'identification du répertoire des entreprises, Business Directory Identification System