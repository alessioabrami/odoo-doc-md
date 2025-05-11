# Comunicazione in Odoo via e-mail — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](email_communication/email_servers_inbound.html "Gestire messaggi in entrata") |
  * [precedente](iot/devices/scale.html "Collegare una bilancia") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Impostazioni generali](../general.html) »
  * Comunicazione in Odoo via e-mail



# Comunicazione in Odoo via e-mail¶

In Odoo, la comunicazione relativa a record come opportunità nel CRM, ordini di vendita e fatture avviene tramite un thread chiamato **chatter** , spesso posizionato a destra del record stesso.

Nel chatter, puoi inviare direttamente e-mail oppure notifiche Odoo ai follower di un documento (in base alle preferenze impostate per le notifiche), registrare note interne, inviare messaggi WhatsApp o SMS e pianificare attività.

Se un follower risponde a un messaggio, la risposta appare nel chatter e Odoo la trasmette ai follower come notifica. Tutte le e-mail, sia in entrata che in uscita, appaiono nello stesso chatter.

## Utenti Odoo online e Odoo.sh¶

Su Odoo online e Odoo.sh, le e-mail in entrata e in uscita sono automatiche, **non devi fare nulla**. Tutto è già configurato nel sottodominio.

Per impostazione predefinita, le e-mail in uscita utilizzano il seguente [indirizzo e-mail di notifica](email_communication/email_servers_outbound.html#email-outbound-notifications) `notifications@company-name.odoo.com`.

### Utilizzare un altro dominio¶

Se preferisci non inviare e-mail con il sottodominio di Odoo `@company-name.odoo.com` ma al contrario vuoi utilizzare [il tuo dominio](email_communication/email_servers_outbound.html#email-outbound-custom-domain), **sarà necessario configurare ulteriori impostazioni** nel dominio e in Odoo. Ciò introduce un ulteriore livello di complessità e richiede conoscenze tecniche (soprattutto per quanto riguarda i protocolli DNS e di posta).

Per aggiungere un dominio e configurare i diritti di accesso dell’amministrazione, puoi anche accedere alla pagina [nuovo alias dominio](email_communication/email_servers_outbound.html#email-outbound-alias-domain) per configurare gli alias delle tue aziende. Se configuri solo un dominio, quest’ultimo verrà condiviso da tutte le aziende sul database.

Se vuoi continuare a utilizzare il server e-mail di Odoo, devi [configurare lo SPF e il DKIM](email_communication/email_domain.html#email-domain-spf).

Se [vuoi utilizzare il tuo server e-mail](email_communication/email_servers_outbound.html#email-outbound-custom-domain-smtp-server), dovrai seguire la documentazione specifica del forntiore del server e-mail.

Per le e-mail in entrata, dopo aver aggiunto il proprio dominio, [le risposte dei clienti saranno indirizzate al tuo dominio](email_communication/email_servers_inbound.html#email-inbound-custom-domain) e dovrai utilizzare uno dei tre modi possibili per fare arrivare di nuovo le e-mail in Odoo (utilizzando il [server e-mail in entrata](email_communication/email_servers_inbound.html#email-inbound-custom-domain-incoming-server), il [reindirizzamento/inoltro](email_communication/email_servers_inbound.html#email-inbound-custom-domain-redirections) o il [record DNS MX](email_communication/email_servers_inbound.html#email-inbound-custom-domain-mx)). Tutto viene spiegato nella [documentazione relativa alla gestione dei messaggi in entrata](email_communication/email_servers_inbound.html).

## Utenti on-premise¶

Se utilizzi Odoo on-premise, dovrai configurare completamente le e-mail in entrata e in uscita:

  * per le e-mail in uscita, devi [utilizzare un server SMTP e un dominio personalizzato](email_communication/email_servers_outbound.html#email-outbound-custom-domain-odoo-server);

  * Per le e-mail in entrata, configura una frequenza di recupero delle nuove e-mail sufficientemente bassa per garantire la reattività, ma sufficientemente alta per non sovraccaricare il sistema o il provider. Per questo motivo e per la semplicità di questa configurazione, di solito consigliamo di utilizzare server di posta in entrata. Per utilizzare un server SMTP, leggi la documentazione [«Utilizzare un dominio personalizzato per i messaggi in entrata»](email_communication/email_servers_inbound.html#email-inbound-custom-domain).




## Utilizzare un server e-mail fornito da terze parti¶

La documentazione di Odoo copre anche diversi server e-mail popolari. Poiché richiedono autorizzazioni e configurazioni specifiche, aggiungono un livello di complessità. Per questo motivo, si consiglia di utilizzare il server e-mail in uscita di Odoo.

  * [Documentazione Outlook](email_communication/azure_oauth.html)

  * [Documentazione Gmail](email_communication/google_oauth.html)

  * [Documentazione Mailjet](email_communication/mailjet_api.html)




Nota

Ogni fornitore ha le proprie limitazioni. Cerca il fornitore desiderato _prima_ di configurarlo. Ad esempio, Outlook e Gmail potrebbero non essere adatti a campagne di marketing più grandi.

Vedi anche

  * [Attività](../essentials/activities.html)

  * [App Comunicazioni](../productivity/discuss.html)

  * [E-mail di riepilogo](companies/digest_emails.html)

  * [App E-mail marketing](../marketing/email_marketing.html)

  * [Modelli e-mail](companies/email_template.html)

  * [Creazione nota spesa con alias e-mail](../finance/expenses/log_expenses.html#expenses-email-expense)

  * [Creazione ticket helpdesk con alias e-mail](../services/helpdesk/overview/receiving_tickets.html#helpdesk-receiving-tickets-email-alias)

  * [Creazione lead con alias e-mail](../sales/crm/acquire_leads/email_manual.html#crm-configure-email-alias)

  * [Creazione lavoro progetto con alias e-mail](../services/project/tasks/task_creation.html#task-creation-email-alias)

  * [Gateway e-mail tecnico per utenti on-premise](../../administration/on_premise/email_gateway.html)

  * [Avvio tecnico del database di Odoo con un server e-mail in uscita configurato dall’interfaccia a riga di comando](../../developer/reference/cli.html#reference-cmdline-server-emails)




  * [Gestire messaggi in entrata](email_communication/email_servers_inbound.html)
  * [Gestire messaggi in uscita](email_communication/email_servers_outbound.html)
  * [Configurare record DNS per inviare e-mail in Odoo](email_communication/email_domain.html)
  * [Collegare Microsoft Outlook 365 a Odoo utilizzando Azure OAuth](email_communication/azure_oauth.html)
  * [Collegare Gmail a Odoo utilizzando Google OAuth](email_communication/google_oauth.html)
  * [API Mailjet](email_communication/mailjet_api.html)
  * [Problemi e-mail comuni e soluzioni](email_communication/faq.html)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/general/email_communication.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](email_communication/email_servers_inbound.html "Gestire messaggi in entrata") |
  * [precedente](iot/devices/scale.html "Collegare una bilancia") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Impostazioni generali](../general.html) »
  * Comunicazione in Odoo via e-mail


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
  *[API]: Application Programming Interface
  *[IVA]: imposta sul valore aggiunto
  *[MRR]: Monthly Recurring Revenue
  *[ARR]: Annual Recurring Revenue
  *[USB]: Universal Serial Bus
  *[IoT]: Internet of Things
  *[OS]: Operating System
  *[SO]: sales order
  *[MRP]: Material Requirement Planning