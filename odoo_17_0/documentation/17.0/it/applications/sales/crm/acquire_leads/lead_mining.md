# Estrarre lead — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../track_leads.html "Assegnare e tracciare i contatti") |
  * [precedente](send_quotes.html "Creare e inviare preventivi") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Acquisire nuovi contatti](../acquire_leads.html) »
  * Estrarre lead



# Estrarre lead¶

La funzione _Estrazione lead_ consente agli utenti del _CRM_ di generare nuovi lead direttamente nel proprio database Odoo. Per garantire la qualifica dei lead, l’output dell’estrazione di lead viene determinato da una serie di criteri di filtraggio, come il Paese, le dimensioni dell’azienda e il settore.

## Configurazione¶

Per iniziare, accedi all’app CRM ‣ Configurazione ‣ Impostazioni e seleziona la casella di controllo Estrazione lead per attivare la funzione. In seguito, fai clic su Salva.

## Generare lead¶

Dopo aver attivato l’impostazione _Estrazione lead_ , nell’angolo in alto a sinistra della _Pipeline_ del _CRM_ è disponibile un nuovo pulsante chiamato _Genera lead_ (CRM ‣ Vendite ‣ La mia pipeline).

Le richieste di estrazione di lead sono disponibili anche seguendo il percorso app CRM ‣ Configurazione ‣ Richieste estrazione lead, oppure tramite app CRM ‣ Lead ‣ Lead, dove è disponibile anche il pulsante Genera lead.

Facendo clic sul pulsante Genera lead, si apre una finestra pop-up che offre una serie di criteri per la generazione dei lead.

Scegli di generare lead per Aziende per ottenere solo informazioni sull’azienda, oppure scegli Companies and their Contacts per ottenere informazioni sull’azienda e sui contatti dei singoli dipendenti.

Nota

Quando scegli Companies and their Contacts, sono disponibili opzioni aggiuntive per filtrare i contatti in base al Ruolo o all”Anzianità.

Le opzioni di filtraggio aggiuntive includono le seguenti:

  * Paesi: filtra i contatti in base al Paese (o ai Paesi) in cui si trovano

  * Stati: filtra ulteriormente i contatti in base allo Stato in cui si trovano, se applicabile

  * Settori: filtra i contatti in base al settore specifico in cui lavorano

  * Filtro dimensione: seleziona questa casella di controllo per specificare il numero di dipendenti dell’azienda. Questo genera un campo denominato Dimensione. Compila gli spazi vuoti per creare un intervallo per le dimensioni dell’azienda desiderata

  * Team vendite: scegli a quale team di vendita assegnare i lead

  * Addetto vendite: scegli a quale membro del team vendite assegnare i lead

  * Tag predefiniti: scegli quali tag applicare direttamente ai lead una volta trovati




Importante

Assicurati di essere al corrente delle ultime normative UE quando ricevi informazioni di contatto. Ulteriori informazioni sul Regolamento generale sulla protezione dei dati sono disponibili su [Odoo GDPR](https://www.odoo.com/it_IT/gdpr).

### Visualizzare lead¶

Una volta generati, i lead vengono assegnati all’addetto vendite e al team designato. Per visualizzare ulteriori informazioni sul lead, selezionane uno dall’elenco e fai clic per aprirlo.

Nel thread del chatter per il lead, vengono fornite ulteriori informazioni. Queste possono includere il numero di dipendenti, la tecnologia utilizzata dall’azienda, il fuso orario e le informazioni di contatto diretto.

Nota

Se la funzione Lead **non** viene attivata per il database, i lead vengono generati come _opportunità_ e aggiunti alla pipeline per il venditore designato.

Per attivare la funzionalità _lead_ , apri l’app CRM ‣ Configurazione ‣ Impostazioni e spunta la casella Lead. Infine, fai clic su Salva.

## Tariffazione¶

L’estrazione di lead è una funzione _acquisti in app_ e ogni lead generato costa un [credito](../../../essentials/in_app_purchase.html#in-app-purchase-credits).

Importante

La generazione di Companies and their Contacts costa un credito aggiuntivo per ogni contatto generato. Per maggiori informazioni sulle tariffe, onsulta la sezione: [Generazione lead tramite IAP Odoo](https://iap.odoo.com/iap/in-app-services/167?).

Per comprare crediti, apri l’app CRM ‣ Configurazione ‣ Impostazioni. Nella sezione Generazione lead, sotto la funzionalità Estrazione lead, fai clic su Compra crediti.

I crediti possono essere acquistati anche accedendo all’applicazione Impostazioni. Nella sezione Contatti, sotto la funzione IAP Odoo, fai clic su Vedi i miei servizi.

Nota

Gli utenti di Odoo Enterprise con un abbonamento valido ricevono crediti gratuiti per testare le funzionalità IAP prima acquistare più crediti per il database inclusi database demo/di formazione, database educativi e database con un’app gratuita.

Vedi anche

[Acquisti in-app (IAP)](../../../essentials/in_app_purchase.html)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/crm/acquire_leads/lead_mining.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../track_leads.html "Assegnare e tracciare i contatti") |
  * [precedente](send_quotes.html "Creare e inviare preventivi") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Acquisire nuovi contatti](../acquire_leads.html) »
  * Estrarre lead


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