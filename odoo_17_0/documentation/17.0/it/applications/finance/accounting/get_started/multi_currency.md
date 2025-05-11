# Sistema multi valuta — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](avg_price_valuation.html "Prezzo medio sulla merce resa") |
  * [precedente](chart_of_accounts.html "Piano dei conti") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Esordiente](../get_started.html) »
  * Sistema multi valuta



# Sistema multi valuta¶

Odoo consente di emettere fatture, ricevere fatture e registrare transazioni in valute diverse da quella principale configurata per l’azienda. È anche possibile impostare conti bancari in altre valute ed eseguire report sulle attività in valuta estera.

Vedi anche

  * [Gestire un conto bancario in una valuta straniera](../bank/foreign_currency.html)




## Configurazione¶

### Valuta principale¶

La **valuta principale** è definita per impostazione predefinita in base al paese dell’azienda. È possibile modificarla andando in Contabilità ‣ Configurazione ‣ Impostazioni ‣ Valute e cambiando la valuta nell’impostazione Valuta principale.

### Abilita le valute straniere».¶

Andare in Contabilità ‣ Configurazione ‣ Valute e abilitare le valute che si desidera utilizzare selezionando il pulsante Attiva.

### Tassi di cambio¶

#### Aggiornamento manuale¶

Per creare e impostare manualmente un tasso di cambio, andare su Contabilità ‣ Configurazione ‣ Valute, fare clic sulla valuta che si desidera modificare e, nella scheda Tassi, fare clic su Aggiungi una riga per creare un nuovo tasso.

#### Aggiornamento automatico¶

Quando si attiva una seconda valuta per la prima volta, Tassi di valuta automatici appare sotto Dashboard Contabilità ‣ Configurazione ‣ Impostazioni ‣ Valute. Per impostazione predefinita, è necessario fare clic sul pulsante **Aggiorna ora** (🗘) per aggiornare i tassi.

Odoo può aggiornare le tariffe a intervalli regolari. Per farlo, cambiare Intervallo da Manualmente a Giornalmente, Settimanalmente o Mensile. È anche possibile selezionare il servizio web dal quale si desidera recuperare i tassi di cambio più recenti facendo clic sul campo Servizio.

### Voci di differenza di cambio¶

Odoo registra automaticamente le voci relative alle differenze di cambio su conti dedicati, in un giornale dedicato.

È possibile definire quale giornale e quali conti utilizzare per **registrare le voci relative alle differenze di cambio** andando in Contabilità ‣ Configurazione ‣ Impostazioni ‣ Conti predefiniti e modificando Giornale, Conto guadagni e Conto perdite.

Example

Se si riceve un pagamento per una fattura di un cliente un mese dopo la sua emissione, è probabile che il tasso di cambio sia cambiato da allora. Pertanto, questa fluttuazione implica un profitto o una perdita dovuti alla differenza di cambio, che Odoo registra automaticamente nel giornale predefinito **Differenza di cambio**.

### Piano dei conti¶

ogni conto può avere una valuta impostata. In questo modo, tutti i movimenti relativi al conto sono obbligati ad avere la valuta di quel conto

Per farlo, apri l’app Contabilità Contabilità ‣ Configurazione ‣ Piano dei conti e seleziona una valuta nel campo Valuta conto. Se vuoto, verranno gestite tutte le valute attive e non solo una.

### Registri¶

Se viene impostata una valuta per un **registro** , questo registro gestirà solo transazioni nella valuta scelta.

Per farlo, apri l’app Contabilità ‣ Configurazione ‣ Registri, apri il registro che vuoi modificare e seleziona una valuta per il campo Valuta corrispondente.

## Contabilità multi valuta¶

### Fatture cliente, fornitore e altri documenti¶

Per tutti i documenti, è possibile selezionare la valuta e il registro da utilizzare per la transazione sul documento stesso.

### Registrare un pagamento¶

Per registrare un pagamento in una valuta diversa dalla valuta principale dell’azienda, fai clic sul pulsante Registra pagamento del documento e nella finestra pop-up, seleziona una **valuta** nel campo Importo.

### Operazioni bancarie¶

Al momento della creazione o dell’importazione di operazioni bancarie, l’importo apparirà nella valuta principale dell’azienda. Per inserire una **valuta estera** , seleziona una valuta nel campo Valuta estera. Una volta selezionata, inserisci un Importo nella tua valuta principale per convertirla automaticamente nella valuta estera nel campo Importo in valuta.

Durante la riconciliazione, Odoo mostra sia l’importo in valuta estera che l’importo equivalente nella valuta principale dell’azienda.

### Tasso di cambio registrazioni contabili¶

Per vedere la **differenza di cambio delle registrazioni contabili** , accedi alla dashboard del modulo Contabilità ‣ Contabilità ‣ Registri: Varie.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/accounting/get_started/multi_currency.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](avg_price_valuation.html "Prezzo medio sulla merce resa") |
  * [precedente](chart_of_accounts.html "Piano dei conti") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Esordiente](../get_started.html) »
  * Sistema multi valuta


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
  *[CTR]: Click through rate
  *[LIFO]: Last-In, First-Out
  *[SAQ]: Self-Assessment Questionnaire
  *[VAT]: Value Added Tax
  *[SMP]: Service Metadata Publisher
  *[AVCO]: Average Cost Valuation
  *[OdA]: Ordine di acquisto