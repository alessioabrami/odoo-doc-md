# Marketing social — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](social_marketing/social_posts.html "Social posts") |
  * [precedente](surveys/analysis.html "Survey analysis") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Marketing](../marketing.html) »
  * Marketing social



# Marketing social¶

Odoo’s _Social Marketing_ application helps content marketers create and schedule posts, manage various social media accounts, analyze content effectiveness, and engage directly with social media followers in one, centralized location.

Vedi anche

  * [Odoo Tutorials: Marketing](https://www.odoo.com/slides/marketing-27)




#### [Social postsDiscover everything there is to know about how to create and customize social media posts using Odoo. ](social_marketing/social_posts.html)#### [Social campaignsLearn about all the different campaign and marketing tools this application has to offer. ](social_marketing/social_campaigns.html)

## Social media accounts¶

In order to create social posts and analyze content with Odoo _Social Marketing_ , social media accounts **must** be added as a _stream_ on the application’s main dashboard.

Nota

Be aware that personal profiles **cannot** be added as a stream. The main use of Odoo _Social Marketing_ is to manage and analyze business accounts on social media platforms.

Avvertimento

Odoo _Social Marketing_ has some limitations in regards to social media accounts. For example, Odoo **cannot** handle a large quantity of various pages (e.g. ~40 pages) under the same company. The same limitations are present in a multi-company environment because of how the API is constructed.

Avvertimento

In multi-company environments, if every company doesn’t activate a page at once, it will result in a permission error.

For example, if Company 1 is the only company selected from the main Odoo dashboard, and activates _Facebook Page 1_ and _Facebook Page 2_ , then those pages will be accesible on the _Social Marketing_ dashboard.

However, if on that same database, the user adds Company 2 from the company drop-down menu in the header, and attempts to add those same streams, it results in a permission error.

## Social media streams¶

To add a social media business account as a stream, navigate to Social Marketing app and select the Add A Stream button located in the upper-left corner. Doing so reveals an Add a Stream pop-up window.

In the Add a Stream pop-up window, choose to Link a new account for a business from any of the following popular social media platforms: Facebook, Instagram, LinkedIn, Twitter, and YouTube.

After clicking the desired social media outlet from the Add a Stream pop-up window, Odoo navigates directly to that specific social media outlet’s authorization page, where permission must be granted, in order for Odoo to add that particular social media account as a stream to the _Social Marketing_ application.

Once permission is granted, Odoo navigates back to the Feed on the main Social Marketing dashboard, and a new column, with that account’s posts, is added. Accounts/streams can be added at any time.

Importante

A Facebook page can be added as long as the Facebook account that grants permission is the administrator for the page. It should also be noted that different pages can be added for different streams.

Nota

Instagram accounts are added through a Facebook login because it uses the same API. This means, an Instagram account needs to be linked to a Facebook account in order for it to show up as a stream in Odoo.

## Social media page¶

Another way to quickly link social media accounts to Odoo _Social Marketing_ can be done on the Social Media page. To access the Social Media page, navigate to Social Marketing app ‣ Configuration ‣ Social Media.

On the Social Media page there is a collection of all social media options, each complete with a Link account button: Facebook, Instagram, LinkedIn, Twitter, YouTube, and Push Notifications.

## Social accounts page¶

To see a list of all social accounts and websites linked to the database, go to Social Marketing app ‣ Configuration ‣ Social Accounts. This Social Accounts display the Name, the Handle/Short Name, the Social Media platform, who it was Created by, and the Company to which it is associated.

To edit/modify any of the social accounts on this page, simply select the desired account from the list on this page, and proceed to make any adjustments necessary.

## Social streams page¶

To view a separate page with all the social media streams that have been added to the main _Social Marketing_ dashboard, navigate to Social Marketing app ‣ Configuration ‣ Social Streams.

Here, the social stream information is organized in a list with the Social Media, the Title of the stream, the Type of the stream (e.g. Posts, Keyword, etc.), who it was Created by, and the Company to which it is associated.

To modify any stream’s information, simply click the desired stream from the list, and proceed to make any necessary adjustments.

## Visitatori¶

To see a complete overview of all the people who have visited the website(s) connected to the database, navigate to Social Marketing app ‣ Visitors.

Here, Odoo provides a detailed layout of all the visitors” pertinent information in a default kanban view. If visitors already have contact information in the database, the option to send them an Email and/or an SMS is available.

This same visitor data can also be viewed as a list or a graph. Those view options are located in the upper-right corner of the Visitors page.

  * Social posts
    * Posts page
      * [Post](social_marketing/social_posts.html#posts)
      * [Create leads from comments](social_marketing/social_posts.html#create-leads-from-comments)
      * [Approfondimenti](social_marketing/social_posts.html#insights)
    * Create and post social media content
      * Post detail form
        * [Azienda](social_marketing/social_posts.html#company)
        * [Pubblica su](social_marketing/social_posts.html#post-on)
        * [Messaggio](social_marketing/social_posts.html#message)
        * [Allega immagini](social_marketing/social_posts.html#attach-images)
        * [Campagna](social_marketing/social_posts.html#campaign)
        * [Quando](social_marketing/social_posts.html#when)
        * [Opzioni di notifiche push](social_marketing/social_posts.html#push-notification-options)
  * Social marketing campaigns
    * [Campaigns page](social_marketing/social_campaigns.html#campaigns-page)
    * [Create social marketing campaigns](social_marketing/social_campaigns.html#create-social-marketing-campaigns)
    * [Edit social marketing campaigns](social_marketing/social_campaigns.html#edit-social-marketing-campaigns)
    * [Social marketing campaign templates](social_marketing/social_campaigns.html#social-marketing-campaign-templates)
    * [Add content and communications to campaigns](social_marketing/social_campaigns.html#add-content-and-communications-to-campaigns)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/marketing/social_marketing.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](social_marketing/social_posts.html "Social posts") |
  * [precedente](surveys/analysis.html "Survey analysis") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Marketing](../marketing.html) »
  * Marketing social


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
  *[FBM]: Fulfilled By Merchant
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
  *[POS]: Point Of Sale
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
  *[CTR]: click-through rate