# Arricchire i contatti con l’autocompletamento del partner — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](gamification.html "Gamification CRM") |
  * [precedente](../optimize.html "Ottimizzare il lavoro quotidiano") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Ottimizzare il lavoro quotidiano](../optimize.html) »
  * Arricchire i contatti con l’autocompletamento del partner



# Arricchire i contatti con l’autocompletamento del partner¶

Il _completamento automatico dei partner_ arricchisce il database dei contatti con dati aziendali. In qualsiasi modulo, inserisci il nome della nuova azienda nel campo Cliente (campo tecnico `partner_id`) e seleziona una delle aziende suggerite nel menu a discesa. Ottieni immediatamente informazioni aziendali preziose e ricche di dati difficili da trovare per un’azienda specifica.

Importante

Un’azienda non può essere già inserita manualmente nell’applicazione _Contatti_ prima di arricchirla di dati.

Le informazioni fornite dal completamento automatico del partner possono comprendere informazioni generali sull’azienda (compresi il nome completo e il logo della stessa), account dei social media, Tipo di azienda, informazioni sulla Fondazione, Settori, numero di Dipendenti, Entrate previste, numero di Telefono, Fuso orario e Tecnologie utilizzate.

Importante

Quando ottieni le informazioni di contatto di un’azienda, assicurati di conoscere le norme europee più recenti. Per maggiori informazioni sul Regolamento generale sulla protezione dei dati, consulta la pagina [Odoo GDPR](http://odoo.com/gdpr). In Odoo, le informazioni di contatto individuali non possono essere ricercate con la funzione di completamento automatico dei partner.

## Configurazione¶

Accedi al modulo Impostazioni ‣ sezioni Contatti. In seguito, attiva la funzionalità Autocompletamento partner spuntando la relativa casella e fai clic su Salva.

## Arricchire contatti con dati aziendali¶

Da qualsiasi modulo, mentre l’utente digita il nome di un nuovo contatto aziendale, Odoo rivela un ampio menu a tendina di suggerimenti di potenziali corrispondenze. Se ne viene selezionato uno, il contatto viene popolato con i dati aziendali relativi a quella specifica selezione.

Ad esempio, dopo aver digitato `Odoo`, verranno mostrate le seguenti informazioni:

Nella chat, dopo aver fatto clic sul contatto desiderato, vengono visualizzate le seguenti informazioni sull’azienda:

Suggerimento

La funzione di completamento automatico del partner funziona anche se viene inserito il numero di partita IVA al posto del nome dell’azienda.

## Tariffazione¶

Il _completamento automatico dei partner_ è un servizio _In-App Purchase (IAP)_ che richiede crediti prepagati per essere utilizzato. Ogni richiesta consuma un credito.

Per acquistare crediti, accedi al modulo Impostazioni ‣ sezione Contatti. Quindi, individua la funzione Completamento automatico partner e fai clic su Acquista crediti, oppure individua la funzione Odoo IAP e fai clic su Vedi i miei servizi. Dalla pagina risultante, seleziona il pacchetto desiderato.

Nota

Se il database esaurisce i crediti, le uniche informazioni popolate quando fai clic sull’azienda suggerita saranno il link al sito web e il logo.

Scopri di più sulla [Informativa sulla privacy](https://iap.odoo.com/privacy).

Nota

Gli utenti di Odoo Enterprise con un abbonamento valido ricevono crediti gratuiti per testare le funzionalità IAP prima di scegliere se acquistare più crediti per il database inclusi database demo/di formazione, database educativi e database con un “app gratuita.

Vedi anche

[Acquisti in-app (IAP)](../../../essentials/in_app_purchase.html)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/crm/optimize/partner_autocomplete.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](gamification.html "Gamification CRM") |
  * [precedente](../optimize.html "Ottimizzare il lavoro quotidiano") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Ottimizzare il lavoro quotidiano](../optimize.html) »
  * Arricchire i contatti con l’autocompletamento del partner


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