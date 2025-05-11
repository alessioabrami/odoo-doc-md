# Referral dipendenti — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](referrals/share_jobs.html "Share job positions") |
  * [precedente](recruitment/team_performance.html "Team performance reporting") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
  * [Human resources](../hr.html) »
  * Referral dipendenti



# Referral dipendenti¶

Odoo’s _Referrals_ application is a centralized place where all information regarding referrals is housed - from points earned, coworkers hired, and rewards selected. Users can recommend people they know for job positions, and then earn referral points as those people progress through the recruitment pipeline. Once enough referral points are earned, they can be exchanged for prizes. The _Referrals_ application integrates with the _Employees_ , _Recruitment_ , and _Website_ applications, all of which must be installed in order for the _Referrals_ application to function.

The only configurations needed for the _Referrals_ application _after_ it has been installed, are related to the [rewards](referrals/rewards.html); everything else is pre-configured when Odoo _Referrals_ is installed.

Users with either Referral User, Officer, or Administrator access rights for the _Recruitment_ application have access to the _Referrals_ application. Only users with Administrator access rights for the _Recruitment_ application have access to the [reporting](referrals/reporting.html) and configurations menus. For more information on users and access rights, refer to these documents: [Utenti](../general/users.html) and [Diritti di accesso](../general/users/access_rights.html).

## Inserimento lavorativo¶

When opening the _Referrals_ application for the first time, a pre-configured onboarding script appears. This is in the form of four slides, each explaining the different parts of the _Referrals_ application. At the top of the dashboard, the following message is displayed throughout all the onboarding slides: GATHER YOUR TEAM! Job Referral Program. Behind this main message is an image, and beneath it some more explanatory text.

Each of the onboarding slides has a corresponding image and message that is displayed. After reading each message, click the Next button to advance to the next slide.

The text that appears on each slide is as follows:

  1. Oh no! Villains are lurking the city! Help us recruit a team of superheroes to save the day!

  2. Browse through open job positions, promote them on social media, or refer friends.

  3. Collect points and exchange them for awesome gifts in the shop.

  4. Compete against your colleagues to build the best justice league!




Nota

The onboarding slides will appear every time the _Referrals_ application is opened, until all the slides have been viewed and the Start Now button has been clicked. If the onboarding is exited at any point, or if the Start Now button has _not_ been clicked, the onboarding slides will begin again when the _Referrals_ application is opened. Once the Start Now button has been clicked, the onboarding slides will not be seen again, and the main dashboard will load when the _Referrals_ application is opened from that point on.

At any point during onboarding, the Skip button may be clicked. This exits the onboarding, and the main _Referrals_ dashboard loads. If Skip is clicked, onboarding slides will not load anymore when opening the _Referrals_ application.

Nota

If there are any candidates hired that the user had referred prior to opening the Referrals app (meaning the onboarding slides have not appeared before), when Start Now is clicked at the end of onboarding, instead of going to the main dashboard, a hired screen appears instead.

### Modifying onboarding slides¶

Onboarding slides can be modified if desired. Only users with Administrator rights for the _Recruitment_ application can modify onboarding slides. To edit a slide, navigate to Referrals app ‣ Configuration ‣ Onboarding. Each line displays the text for the individual onboarding slide. To edit an onboarding slide, click on an individual slide line to open the slide’s onboarding form.

Make any changes to the message in the Text field. A Company may be selected, as well. However, if this field is populated, that slide is _only_ displayed for that particular company.

Nota

The Company field only appears when in a multi-company database.

The image can be modified, as well. Hover over the image thumbnail in the top-right corner of the form. A ✏️ (pencil) icon and 🗑️ (garbage can) icon appear. Click the ✏️ (pencil) icon to change the image. A file navigator window loads. Navigate to the desired image, select it, then click Open. The new image appears in the thumbnail. To delete an image, click the 🗑️ (garbage can) icon, then select a new image using the ✏️ (pencil) icon.

The sequence in which the slides appear can be changed from the _Onboarding_ dashboard. Click the (six small gray boxes) icon to the left of the the slide text, and drag the slide to the desired position.

## Hired referrals¶

When a candidate that has been referred by a user is hired, the user «grows their superhero team» and adds superhero avatars to their Referrals dashboard.

After a referral has been hired, when the user next opens the Referrals app, instead of the main dashboard, a hired page loads. The text (Referral Name) has been hired! Choose an avatar for your new friend! appears.

Below this message are five avatar thumbnails to choose from. If an avatar has already been assigned to a referral, the thumbnail is grayed out, and the name that the avatar has been chosen for appears beneath the avatar. Click on an available avatar to select it.

If more than one referral was hired since opening the _Referrals_ application, after selecting the first avatar, the user is prompted to select another avatar for the subsequent hired referral. Once all avatars have been selected, the dashboard loads and all the avatars are now visible. Mouse over each avatar and their name is displayed above them.

### Modify friends¶

Friend avatars are able to be modified in the same manner that levels are modified. Only users with Administrator rights for the _Recruitment_ application can make modifications to friends. The pre-configured friends can be seen and modified by navigating to Referrals app ‣ Configuration ‣ Friends. Each friend avatar appears in the Dashboard Image column, and the corresponding name appears in the Friend Name column. The default images are a motley group of hero characters, ranging from robots to dogs.

To modify a friend’s dashboard image, thumbnail, name, or position, click on an individual friend to open the referral friend form. Click Edit to make modifications. Type the name in the Friend Name field. The name is solely to differentiate the friends in the configuration menu; the friend’s name is not visible anywhere else in the _Referrals_ application.

The Position can be set to either Front or Back. This determines the position of the friend in relation to the user’s super hero avatar. Click the radio button next to the desired selection, and the friend will appear either in front of or behind the user’s avatar when activated.

If desired, both the thumbnail Image and the Dashboard Image can be modified. Hover over the image being replaced to reveal a ✏️ (pencil) icon and 🗑️ (garbage can) icon. Click the ✏️ (pencil) icon, and a file explorer window appears. Navigate to the desired image file, then click Open to select it.

The referral friend form automatically saves, but can be saved manually at any time by clicking the _Save manually_ option, represented by a (cloud upload) icon, located in the top-left corner. To cancel any changes made, click the ✖️ (Discard all changes) icon to delete any changes, and revert to the original content.

Avvertimento

It is not advised to edit the images. An image file must have a transparent background in order for it to render properly. Only users with knowledge about transparent images should attempt adjusting any images in the _Referrals_ application.

Once an image is changed and the friend is saved, it is **not possible** to revert to the original image. To revert to the original image, the _Referrals_ application must be _uninstalled then reinstalled._

## Livelli¶

The _Referrals_ application has pre-configured levels that are reflected in the user’s avatar on the Referrals dashboard. As a user refers potential employees and earns points, they can _level up_ , much like in a video game.

Levels have no functional impact on the performance of the application. They are solely used for the purpose of adding achievement tiers for participants to aim for, gamifying referrals for the user.

The user’s current level is displayed at the top of the main _Referrals_ application dashboard, directly beneath their photo, in a Level: X format. In addition, a colored ring appears around the user’s photo, indicating how many points the user currently has, and how many additional points they need to level up. The cyan colored portion of the ring represents points earned, while the white colored portion represents the points still needed before they can level up.

### Modify levels¶

Only users with Administrator rights for the _Recruitment_ application can modify levels. The pre-configured levels can be seen and modified by navigating to Referrals app ‣ Configuration ‣ Levels. Each avatar appears in the Image column, and the corresponding level number appears in the Level Name column. The default images are of Odoo superheroes, and each level adds an additional element to their avatar, such as capes and shields.

To modify a level’s image, name, or points required to reach the level, click on an individual level in the list to open the level form, then make modifications.

Type in the name (or number) of the level in the Level Name field. What is entered is displayed beneath the user’s photo on the main dashboard when they reach that level. Enter the number of referral points needed to reach that level in the Requirements field. The points needed to level up are the total accumulated points earned over the lifetime of the employee, not additional points from the previous level that must be earned.

If desired, the Image can also be modified. Hover over the image to reveal a ✏️ (pencil) icon and 🗑️ (garbage can) icon. Click the ✏️ (pencil) icon, and a file explorer window appears. Navigate to the desired image file, then click Open to select it.

The level form saves automatically, but can be saved manually at any time by clicking the _save manually_ option, represented by a (cloud upload) icon, located in the top-left corner. To cancel any changes made, click the ✖️ (Discard all changes) icon to delete any changes, and revert to the original content.

Avvertimento

It is not advised to edit the images. An image file must have a transparent background in order for it to render properly. Only users with knowledge about transparent images should attempt adjusting any images in the _Referrals_ application.

Once an image is changed and the level is saved, it is **not possible** to revert to the original image. To revert to the original image, the _Referrals_ application must be _uninstalled then reinstalled._

### Level up¶

Once enough points have been accumulated to level up, the circle around the user’s photo is completely filled in with a cyan color, a large image stating Level up! appears above the photo, and the phrase Click to level up! appears beneath the user’s photo and current level.

Click on either the LEVEL UP! graphic, the user’s photo, or the text Click to level up! beneath the user’s photo to level up the user. The user’s avatar changes to the current level, and the ring around the photo is updated to indicate the current amount of points.

Leveling up does not cost the user any points, the user simply needs to earn the specified amount of points required.

Nota

Once a user has reached the highest configured level, they will continue to accrue points that can be redeemed for rewards, but they are no longer able to level up. The ring around their photo remains solid cyan.

Vedi anche

  * [Share job positions](referrals/share_jobs.html)

  * [Referral points](referrals/points.html)

  * [Premi](referrals/rewards.html)

  * [Avvisi](referrals/alerts.html)

  * [Rendiconto](referrals/reporting.html)




  * Share job positions
    * [Vedi lavori](referrals/share_jobs.html#view-jobs)
    * [Refer friends](referrals/share_jobs.html#refer-friends)
    * Share a job
      * [Collega](referrals/share_jobs.html#link)
      * [Facebook](referrals/share_jobs.html#facebook)
      * [X (formerly Twitter)](referrals/share_jobs.html#x-formerly-twitter)
      * [LinkedIn](referrals/share_jobs.html#linkedin)
      * [Invia e-mail a un amico](referrals/share_jobs.html#email-a-friend)
  * Referral points
    * My referrals
      * [Punti](referrals/points.html#points)
  * Premi
    * [Create rewards](referrals/rewards.html#create-rewards)
    * [Redeem rewards](referrals/rewards.html#redeem-rewards)
  * Avvisi
    * [Create an alert](referrals/alerts.html#create-an-alert)
    * [Dismiss an alert](referrals/alerts.html#dismiss-an-alert)
  * Rendiconto
    * Employees referral analysis report
      * [Use case: hired referrals](referrals/reporting.html#use-case-hired-referrals)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/hr/referrals.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](referrals/share_jobs.html "Share job positions") |
  * [precedente](recruitment/team_performance.html "Team performance reporting") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
  * [Human resources](../hr.html) »
  * Referral dipendenti


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-App Purchase
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
  *[API]: application programming interfaces
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
  *[POS]: Punto vendita
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