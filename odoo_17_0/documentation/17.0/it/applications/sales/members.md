# Iscritti — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](members/members_analysis.html "Analisi iscritti") |
  * [precedente](rental.html "Noleggio") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Vendite](../sales.html) »
  * Iscritti



# Iscritti¶

L’applicazione _Iscritti_ è il luogo in cui è possibile configurare e gestire tutte le operazioni relative agli abbonamenti. L’applicazione _Iscritti_ si integra con le applicazioni _Vendite_ e _Contabilità_ per vendere e fatturare gli abbonamenti direttamente ai clienti.

## Prodotti iscrizione¶

Per creare un nuovo prodotto iscrizione, accedi al modulo Iscritti ‣ Configurazione ‣ Prodotti iscrizione e fai clic su Nuovo per aprire un record prodotto vuoto.

Completa il modulo vuoto con le informazioni necessarie compresa la Durata iscrizione.

Nota

I prodotti iscrizione richiedono una data di inizio e di fine, in quanto vengono usati per stabilire lo stato iscrizione. I prodotti iscrizione possono essere venduti _prima_ della data di inizio.

I prodotti iscrizione possono essere aggiunti a un ordine di vendita e fatturati come prodotti normali o abbonamenti.

## Attivare un’iscrizione¶

Per attivare un’iscrizione dall’applicazione _Contatti_ , accedi al modulo Contatti e fai clic su un contatto per aprire il modulo di dettaglio di quel contatto specifico.

Dal modulo di contatto risultante, apri la scheda Iscrizione e fai clic su Aggiungi iscrizione.

Nella finestra pop-up Effettua iscrizione che appare, seleziona un Iscritto dal menu a discesa. Successivamente, configura un Prezzo socio.

Fai clic su Fattura l’iscrizione quando entrambi i campi sono stati compilati. In questo modo si apre la pagina Fattura di iscrizione, dove le fatture possono essere confermate e completate.

In alternativa, per offrire un’iscrizione gratuita, spunta la casella Iscritto non pagante nella scheda Iscrizione del modulo contatto.

## Stato iscrizione¶

Lo stato attuale dell’iscrizione viene elencato nella scheda Iscrizione di ogni record contatto:

  * Non iscritto: un partner che **non** ha richiesto l’iscrizione.

  * Iscritto cancellato: un iscritto che ha annullato la propria iscrizione.

  * Vecchio iscritto: la data di scadenza dell’iscrizione è passata.

  * Iscritto in attesa: un membro che ha richiesto l’iscrizione ma la fattura non è stata ancora creata.

  * Iscritto con fattura: un membro la cui fattura è stata creata ma non ancora pagata.

  * Iscritto con pagamento: un membro che ha pagato la tassa di iscrizione.




## Pubblicare l’elenco degli iscritti¶

Per pubblicare un elenco di membri attivi sul sito web, è necessario [installare](../general/apps_modules.html#general-install) l’applicazione _Elenco iscritti online_. Dopo aver installato il modulo, aggiungi la pagina `/membri` al menu del sito web [modificando il menu del sito](../websites/website/pages/menus.html).

### Pubblicare singoli membri¶

Torna all’applicazione CRM ‣ Vendite ‣ Clienti e fai clic sulla scheda Kanban di un iscritto. Sul modulo cliente che appare, fai clic sul pulsante Vai al sito web nella parte superiore della pagina per aprire la pagina web dell’iscritto.

Fai clic sul pulsante __ Modifica per svelare la barra laterale di strumenti di modifica. Dopo aver apportato tutte le modifiche necessarie alla pagina, fai clic su Salva. Nella parte alta della pagina, fai scorrere il pulsante Non pubblicato per attivarlo e passare a Pubblicato.

Ripeti gli step per tutti gli iscritti desiderati.

  * [Analisi iscritti](members/members_analysis.html)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/members.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](members/members_analysis.html "Analisi iscritti") |
  * [precedente](rental.html "Noleggio") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Vendite](../sales.html) »
  * Iscritti


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-app purchases
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