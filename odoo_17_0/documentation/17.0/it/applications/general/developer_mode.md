# Modalità sviluppatore (modalità di debug) — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../administration.html "Gestire i database") |
  * [precedente](integrations/google_translate.html "Google Traduttore") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Impostazioni generali](../general.html) »
  * Modalità sviluppatore (modalità di debug)



# Modalità sviluppatore (modalità di debug)¶

La modalità sviluppatore, conosciuta anche come modalità di debug, sblocca l’accesso a strumenti e impostazioni avanzati in Odoo.

Avvertimento

Esplora la modalità con cautela in quanto alcuni strumenti di sviluppo e impostazioni tecniche sono considerati avanzati e potrebbero avere rischi associati. Utilizzali solo se sei al corrente delle implicazioni e sicuro delle tue azioni.

Nota

La modalità sviluppatore è disponibile anche con [asset](../../developer/reference/frontend/framework_overview.html#frontend-framework-assets-debug-mode) utilizzati per il debug del codice JavaScript e con [asset di prova](../../developer/reference/frontend/framework_overview.html#frontend-framework-tests-debug-mode) che vengono utilizzati per eseguire i tour di prova.

## Attivazione¶

Per attivarla, apri l’applicazione Impostazioni, vai alla sezione Strumenti di sviluppo e fai clic su Attiva modalità sviluppatore.

Una volta attivata, sarà disponibile l’opzione Disattiva modalità sviluppatore.

Per attivare la modalità sviluppatore **da qualsiasi punto del database** , aggiungi `?debug=1` all’URL dopo `/web` (ad es., `https://example.odoo.com/web?debug=1#action=menu&cids=1`). Per disattivarla, utilizza `?debug=0`.

Utilizza `?debug=assets` per attivare la modalità sviluppatore con asset e `?debug=tests` per attivarla senza asset.

Suggerimento

Apri il **riquadro comandi** premendo `Ctrl + K` o `Cmd ⌘ + K` ed in seguito digita `debug` per attivare la modalità sviluppatore con asset o per disattivarla.

Estensione browser

L’estensione browser [Odoo Debug](https://github.com/Droggol/OdooDebug) aggiunge un’icona per attivare o meno la modalità sviluppatore dalla barra degli strumenti del browser stesso. È disponibile nel [Web Store di Chrome](https://chromewebstore.google.com/detail/odoo-debug/hmdmhilocobgohohpdpolmibjklfgkbi) e tra i [Componenti aggiuntivi di Firefox](https://addons.mozilla.org/firefox/addon/odoo-debug/).

## Strumenti di sviluppo e menu tecnico¶

Una volta attivata la modalità sviluppatore, è possibile accedere agli strumenti di sviluppo facendo clic sull’icona __(coccinella). Il menu contiene strumenti utili per comprendere o modificare dati tecnici come i campi, i filtri o le azioni di una vista. Le opzioni disponibili dipendono dal punto di accesso al menu.

Gli amministratori del database possono accedere al menu tecnico dall’applicazione Impostazioni. Il menu contiene impostazioni avanzate relative al database come quelle legate a struttura, sicurezza, azioni, ecc,

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/general/developer_mode.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../administration.html "Gestire i database") |
  * [precedente](integrations/google_translate.html "Google Traduttore") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Impostazioni generali](../general.html) »
  * Modalità sviluppatore (modalità di debug)


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