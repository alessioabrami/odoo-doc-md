# Arricchimento lead — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../sales.html "Vendite") |
  * [precedente](utilize_activities.html "Utilizzare attività per i team di vendita") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Ottimizzare il lavoro quotidiano](../optimize.html) »
  * Arricchimento lead



# Arricchimento lead¶

_Il lead enrichment_ è un servizio che fornisce informazioni commerciali per un contatto collegato a un lead. Il lead enrichment è un acquisto in app (IAP) che richiede crediti per essere utilizzato ed è disponibile per i lead esistenti in un database Odoo.

Le informazioni fornite dal lead enrichment possono comprendere informazioni generali sull’azienda (compresi il nome completo e il logo della stessa), account dei social media, Tipo di azienda, informazioni sulla Fondazione, Settori, numero di Dipendenti, Entrate previste, numero di Telefono, Fuso orario e Tecnologie utilizzate.

Nota

Gli utenti di Odoo Enterprise con un abbonamento valido ricevono crediti gratuiti per testare le funzionalità IAP prima di scegliere se acquistare più crediti per il database inclusi database demo/di formazione, database educativi e database con un “app gratuita.

Importante

La funzionalità _lead_ **deve** essere attivata nelle impostazioni del _CRM_ così da poter usare il lead enrichment. Per accedere alle impostazioni del _CRM_ , apri l’app CRM ‣ Configurazione ‣ Impostazioni. Nella sezione CRM, attiva l’opzione Lead e fai clic su Salva.

## Configurare la funzione di lead enrichment¶

Per configurare il lead enrichment nell’applicazione _CRM_ , accedi al modulo CRM ‣ Configurazione ‣ Impostazioni. In seguito, nella sezione Generazione lead, spunta la casella accanto a Lead enrichment e scegli Arricchire i lead solo su richiesta oppure Arricchire automaticamente tutti i lead. Fai clic sul pulsante Salva per attivare le modifiche.

## Arricchire lead¶

L’arricchimento dei lead si basa sul dominio dell’indirizzo e-mail del cliente impostato sul lead. Esistono due modi diversi per arricchire un lead: _automaticamente_ o _manualmente_.

### Arricchire lead automaticamente¶

Durante la configurazione, se selezioni Arricchire automaticamente tutti i lead nella pagina Impostazioni del _CRM_ , non è necessario che l’utente compia alcuna azione per arricchire il lead. Un’azione programmata viene eseguita automaticamente, ogni sessanta minuti, e l’arricchimento avviene sui lead, dopo aver contattato un database remoto.

Suggerimento

Per accedere al cron che viene eseguito per effettuare l’arricchimento dei lead automaticamente, attiva la [modalità sviluppatore](../../../general/developer_mode.html#developer-mode) e accedi all’app Impostazioni ‣ menu Funzioni tecniche ‣ sezione Automazione ‣ Azioni programmate. Nella barra Ricerca…, scrivi `CRM`. Fai clic sul risultato dal nome CRM: arricchisci lead (IAP) ed effettua le modifiche necessarie. Nel campo Eseguire ogni e inserisci un valore maggiore o pari a cinque minuti.

Example

Di seguito è riportato un esempio di dati di arricchimento del lead che sono stati autocompilati con successo:

### Arricchire lead manualmente¶

Se l’opzione Arricchire lead solo su richiesta è stata selezionata nella pagina Impostazioni del _CRM_ , quando si attiva Arricchimento lead, ogni lead che un utente desidera arricchire **deve** essere arricchito manualmente. Questo si ottiene facendo clic sul pulsante Arricchisci nel menu superiore del lead.

Le stesse informazioni saranno recuperate allo stesso costo di credito IAP (uno per arricchimento). Questo metodo di arricchimento è utile quando non è necessario arricchire ogni lead o quando il costo è un problema.

Suggerimento

Arricchisci manualmente lead in gruppo usando la vista _elenco_. Per prima cosa, accedi all’app CRM ‣ Lead e fai clic sul pulsante vista elenco (icona ☰ (tre righe orizzontali)). Successivamente, spunta le caselle dei lead che dovrebbero essere arricchiti manualmente. Infine, fai clic sull’icona ⚙️ Azione e seleziona Arricchisci dal menu a discesa risultante. L’azione può essere eseguita anche dalla pagina _La mia pipeline_. Per farlo, apri il modulo _CRM_ , oppure segui il percorso app CRM ‣ Vendite ‣ La mia pipeline. Entrambi i percorsi mostrano lead e opportunità nella pagina Pipeline.

## Tariffazione¶

L’arricchimento dei lead è una funzione In-App Purchase (IAP) e ogni lead arricchito costa un credito.

Nota

Scopri di più sulle tariffe consultando la pagina: [Generazione lead da Odoo IAP](https://iap.odoo.com/iap/in-app-services/273).

Per comprare crediti, apri l’app CRM ‣ Configurazione ‣ Impostazioni. Nella sezione Generazione lead, sotto la funzionalità Arricchimento lead, fai clic su Compra crediti.

Crediti e saldi possono essere acquistati anche accedendo all’applicazione Impostazioni. Nella sezione Contatti, sotto la funzione IAP Odoo, fai clic su Vedi i miei servizi.

Vedi anche

[Acquisti in-app (IAP)](../../../essentials/in_app_purchase.html)

Importante

Quando raccogli le informazioni di contatto di un’azienda, assicurati di conoscere le norme europee più recenti. Per maggiori informazioni sul Regolamento generale sulla protezione dei dati, consulta la pagina [Odoo GDPR](http://odoo.com/gdpr).

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/crm/optimize/lead_enrichment.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../sales.html "Vendite") |
  * [precedente](utilize_activities.html "Utilizzare attività per i team di vendita") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Ottimizzare il lavoro quotidiano](../optimize.html) »
  * Arricchimento lead


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-App Puchase
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