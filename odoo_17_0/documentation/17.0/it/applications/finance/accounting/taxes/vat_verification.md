# Verifica numero partita IVA (VIES) — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](fiscal_positions.html "Posizioni di bilancio \(mappatura fiscale e contabile\)") |
  * [precedente](retention.html "Imposte alla fonte") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Imposte](../taxes.html) »
  * Verifica numero partita IVA (VIES)



# Verifica numero partita IVA (VIES)¶

Il [sistema di scambio di informazioni sull’IVA](https://ec.europa.eu/taxation_customs/vies/#/vat-validation), o **VIES** , è uno strumento fornito dalla Commissione europea che consente di verificare la validità dei numeri di partita IVA delle aziende registrate nell’Unione europea.

La funzione di convalida dell’IVA di Odoo utilizza il VIES per verificare i numeri di partita IVA dei contatti direttamente dall’interfaccia di Odoo.

Nota

Indipendentemente dal fatto che la funzione Verifica numeri partita IVA sia abilitata o meno, Odoo controlla il formato dell’IVA di un contatto rispetto al [formato previsto per i numeri IVA](https://en.wikipedia.org/wiki/VAT_identification_number) di quel Paese.

## Verifica numero partita IVA VIES¶

Per attivare questa funzione, vai su Contabilità ‣ Configurazione ‣ Impostazioni. Nella sezione Imposte, attiva la funzione Verifica numeri partita IVA e fai clic su Salva.

Una volta abilitata la funzione Verifica numeri partita IVA, se il campo Partita IVA del contatto è popolato _e_ il suo Paese è diverso da quello dell’azienda, Odoo mostra la casella di controllo Intracomunitaria valida. Odoo verifica il numero di partita IVA attraverso il VIES e seleziona o deseleziona automaticamente la casella Intracomunitaria valida a seconda della validità del numero di partita IVA.

Importante

È possibile sovrascrivere manualmente il campo Valida intracomunitaria di un contatto nel caso in cui il controllo automatico del VIES sia errato (ad esempio, se l’azienda è stata creata di recente e la sua partita IVA non è ancora presente nel VIES). Questa modifica viene registrata nelle chat per trasparenza.

Nota

Odoo può [applicare automaticamente le posizioni di bilancio](fiscal_positions.html#fiscal-positions-automatic). Se la funzione Verifica numeri partita IVA è abilitata, tutte le posizioni di bilancio con l’obbligo di IVA abilitata richiederanno numeri partita IVA intracomunitari validi per essere applicate automaticamente.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/accounting/taxes/vat_verification.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](fiscal_positions.html "Posizioni di bilancio \(mappatura fiscale e contabile\)") |
  * [precedente](retention.html "Imposte alla fonte") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Imposte](../taxes.html) »
  * Verifica numero partita IVA (VIES)


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
  *[API]: application programming interface
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
  *[sportello unico OSS]: One-Stop Shop