# E-mail di riepilogo — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](email_template.html "Modelli e-mail") |
  * [precedente](../companies.html "Aziende") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Impostazioni generali](../../general.html) »
  * [Aziende](../companies.html) »
  * E-mail di riepilogo



# E-mail di riepilogo¶

_Le e-mail di riepilogo_ sono riassunti che gli utenti di un’organizzazione ricevono via e-mail e che includono informazioni importanti sulle prestazioni dell’azienda.

Per iniziare ad inviare e-mail di riepilogo, vai su Impostazioni ‣ Sezione statistiche, attiva la funzionalità E-mail di riepilogo e fai clic su Salva.

È possibile configurare una serie di impostazioni per le e-mail di riepiloogo come ad esempio:

  * decidere quali KPI sono condivisi nelle e-mail di riepilogo;

  * determinare la frequenza di invio;

  * scegliere chi riceverà le e-mail in azienda;

  * creare modelli personalizzati;

  * aggiungere KPI aggiuntivi (App _Studio_ richiesta).




Nota

La funzionalità E-mail di riepilogo viene attivata per impostazione predefinita. Il Riepilogo periodico di Odoo rappresenta il modello principale che include tutti i valori KPI del database Odoo e viene inviato ogni giorno agli amministratori.

Avvertimento

Quando crei duplicati dei database dai quali è possibile inviare e-mail (ovvero non in modalità di test), le e-mail di riepilogo continueranno ad essere inviate anche dal database duplicato a meno che non vengano disattivate.

Per disattivare le e-mail di riepilogo, vai su Impostazioni ‣ sezione Statistiche. In seguito, disattiva la funzionalità E-mail di riepilogo deselezionando la casella e fai clic su Salva. Consulta la sezione Disattivare e-mail di riepilogo.

## Personalizzare e-mail di riepilogo predefinite¶

Per personalizzare l’e-mail di riepilogo predefinita (_Riepilogo periodico Odoo_), vai su Impostazioni ‣ sezione Statistiche ‣ campo e-mail di riepilogo. In seguito, seleziona Riepilogo periodico Odoo personale e fai clic sull’icona ↗️ (link esterno) accanto al menu di selezione a discesa.

Apparirà una finestra pop-up con una serie di impostazioni modificabili tra cui:

  * Nome riepilogo: il nome dell’e-mail di riepilogo;

  * Periodicità: controlla la frequenza di invio delle e-mail (Giornaliera, Settimanale, Mensile o Trimestrale).

  * Data prossima e-mail: la data in cui verrà inviata di nuovo l’e-mail di riepilogo;

  * Scheda ICP: seleziona/deseleziona ogni ICP calcolato che appare nelle e-mail di riepilogo. Se una casella è spuntata ciò vuol dire che l” ICP è attivo per l’e-mail di riepilogo. Consulta la sezione ICP.

  * Scheda Destinatari: aggiungi/rimuovi utenti che ricevono le e-mail di riepilogo. Consulta la sezione Destinatari.




Nota

Gli ICP possono essere personalizzati utilizzando Odoo _Studio_. Vengono sostenuti i costi aggiuntivi relativi all’abbonamento del database se è necessario installare _Studio_. Consulta la sezione ICP personalizzati con Odoo Studio.

## Disattivare le e-mail di riepilogo¶

Per disattivare manualmente una singola e-mail di riepilogo, vai su Impostazioni ‣ sezione Statistiche e fai clic su Configura e-mail di riepilogo. In seguito, seleziona l’e-mail di riepilogo desiderata dall’elenco.

Successivamente, fai clic su DISATTIVA PER TUTTI per disattivare o ANNULLA ISCRIZIONE per eliminare l’utente collegato dalla lista di distribuzione. I pulsanti si trovano nel menu in alto, al di sopra del campo Titolo riepilogo.

## Inviare e-mail di riepilogo manualmente¶

Per inviare manualmente e-mail di riepilogo, apri l’app Impostazioni ‣ sezione Statistiche`e fai clic su :guilabel:`Configura e-mail di riepilogo. In seguito, seleziona l’e-mail di riepilogo desiderata e fai clic su INVIA ORA. Il pulsante si trova nel menu in alto, sopra il Titolo riepilogo.

## KPI¶

È possibile aggiungere ICP preimpostati all’e-mail di riepilogo dalla scheda ICP presente sul modulo dell’e-mail stessa,

Per prima cosa, apri l’app Impostazioni ‣ sezione Statistiche e fai clic su Configura e-mail di riepilogo.

In seguito, seleziona l’e-mail di riepilogo desiderata e apri la scheda ICP.

Per aggiungere un ICP all’e-mail di riepilogo, spunta la casella accanto all’indicatore ICP desiderato. Dopo aver aggiunto (o deselezionato) tutti gli ICP desiderati, fai clic su Salva.

I seguenti ICP sono disponibili nella scheda ICP di un modello e-mail di riepilogo di Odoo:

Generale
    

  * Utenti collegati

  * Messaggi



Progetto
    

  * Lavori aperti



Assunzioni
    

  * Dipendenti



CRM
    

  * Nuovi lead/opportunità

  * Opportunità vinte



Vendite
    

  * Tutte le vendite

  * Vendite e-commerce



Punto Vendita
    

  * Vendite POS



Chat dal vivo
    

  * % di soddisfazione

  * Conversazion gestite

  * Tempo per rispondere (sec)



Helpdesk
    

  * Ticket chiusi



Fatturazione
    

  * Ricavi

  * Movimenti banca e cassa




## Destinatari¶

I destinatari dell’e-mail di riepilogo vengono aggiunti nella scheda Destinatari nel modulo dell’e-mail di riepilogo.

Per aggiungere un destinatario, apri l’app Impostazioni ‣ sezione Statistiche e fai clic su Configura e-mail di riepilogo. In seguito, seleziona l’e-mail di riepilogo desiderata e apri la scheda Destinatari.

Per aggiungere un destinatario, fai clic su Aggiungi riga e apparirà la finestra Aggiungi destinatari con tutti gli utenti disponibili da aggiungere.

Nella finestra a comparsa, spunta le caselle accanto al Nome dell’utente e fai clic sul pulsante Seleziona.

Per eliminare un utente dai destinatari, fai clic sull’icona ❌ (elimina) a destra dell’utente elencato nella scheda Destinatari.

Fai clic su Salva per salvare le modifiche.

## Creare e-mail di riepilogo¶

Per creare una nuova e-mail di riepilogo vai su Impostazioni ‣ sezione Statistiche e fai clic su Configura e-mail di riepilogo. In seguito, fai clic su Crea per creare una nuova e-mail di riepologo.

Apparirà una pagina separata con un modello di e-mail di riepilogo vuoto e una serie di impostazioni modificabili, tra cui:

  * Nome riepilogo: il nome dell’e-mail di riepilogo;

  * Periodicità: controlla la frequenza di invio delle e-mail (Giornaliera, Settimanale, Mensile o Trimestrale).

  * Data prossima e-mail: la data in cui verrà inviata di nuovo l’e-mail di riepilogo;

  * Scheda ICP: seleziona/deseleziona ogni ICP calcolato che appare nelle e-mail di riepilogo. Se una casella è spuntata ciò vuol dire che l” ICP è attivo per l’e-mail di riepilogo. Consulta la sezione ICP.

  * Scheda Destinatari: aggiungi/rimuovi utenti che ricevono le e-mail di riepilogo. Consulta la sezione Destinatari.




Da qui, dai un Titolo, specifica la Periodicità, scegli gli ICP e aggiungi Destinatari.

Dopo aver fatto clic su Salva, la nuova e-mail di riepilogo personalizzata sarà disponibile per la selezione nel campo E-mail di riepilogo, che trovi in Impostazioni ‣ sezione Statistiche.

## ICP personalizzati con Odoo Studio¶

Gli ICP presenti nel modulo di un e-mail di riepilogo, nella scheda ICP, possono essere personalizzati utilizzando Odoo _Studio_.

Avvertimento

Se è necessario installare Odoo _Studio_ , potrebbero essere addebitati costi aggiuntivi all’abbonamento relativo al database in uso.

Per iniziare, fai clic sull’icona 🛠️ (strumenti) nella parte in alto a destra dello schermo. Di seguito, il link all’applicazione _Studio_.

Per creare campi aggiuntivi, crea due campi nell’oggetto del riepilogo:

  1. crea un campo booleano chiamato `kpi_myfield` e mostralo nella scheda ICP.

  2. Crea un campo calcolato chiamato `kpi_myfield_value` che calcola gli ICP personalizzati.

  3. Seleziona gli ICP nella scheda ICP.




Suggerimento

Di seguito, il [codice sorgente](https://github.com/odoo/odoo/blob/15.0/addons/digest/models/digest.py) per il file `digest.py` che guida il programmatore nella codifica del campo calcolato.

Vedi anche

Gli utenti possono anche fare clic sulla scheda Destinatari e poi sul menu con i tre punti verticali (kebab) per modificare la vista. È possibile sia fare clic su MODIFICA VISTA ELENCO oppure su MODIFICA VISTA MODULO per modificare la scheda.

### Tabella di riferimento valori calcolati¶

ETICHETTA | VALORE  
---|---  
Utenti collegati | `kpi_res_users_connected_value`  
Messaggi inviati | `kpi_mail_message_total_value`  
Nuove Lead | `kpi_crm_lead_created_value`  
Opportunità vinte | `kpi_crm_opportunities_won_value`  
Apertura lavori | `kpi_project_task_opened_value`  
Ticket chiusi | `kpi_helpdesk_tickets_closed_value`  
% di soddisfazione | `kpi_livechat_rating_value`  
Conversazioni gestite | `kpi_livechat_conversations_value`  
Tempo per rispondere (sec.) | `kpi_livechat_response_value`  
Tutte le vendite | `kpi_all_sale_total_value`  
Vendite e-commerce | `kpi_website_sale_total_value`  
Ricavi | `kpi_account_total_revenue_value`  
Movimenti banca e cassa | `kpi_account_bank_cash_value`  
Vendite POS | `kpi_pos_total_value`  
Nuovi dipendenti | `kpi_hr_recruitment_new_colleagues_value`  
  
[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/general/companies/digest_emails.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](email_template.html "Modelli e-mail") |
  * [precedente](../companies.html "Aziende") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Impostazioni generali](../../general.html) »
  * [Aziende](../companies.html) »
  * E-mail di riepilogo


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
  *[POS]: Punto vendita
  *[URL]: Uniform Resource Locator
  *[2FA]: two-factor authentication
  *[QR]: Quick Response
  *[LDAP]: Lightweight Directory Access Protocol
  *[KPI]: Indicatori di Prestazione Chiave
  *[ICP]: Indicatori Chiave di Prestazione