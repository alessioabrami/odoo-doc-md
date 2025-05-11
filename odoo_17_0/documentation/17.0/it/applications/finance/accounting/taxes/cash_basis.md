# Imposte per cassa — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](retention.html "Imposte alla fonte") |
  * [precedente](../taxes.html "Imposte") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Imposte](../taxes.html) »
  * Imposte per cassa



# Imposte per cassa¶

Le imposte basate sul principio di cassa sono dovute al momento del pagamento, a differenza delle imposte standard che sono dovute al momento della conferma della fattura. In alcuni Paesi e a determinate condizioni è obbligatorio dichiarare al governo le entrate e le uscite in base al metodo di cassa.

Example

Vendi un prodotto nel 1° trimestre dell’anno fiscale e il pagamento viene ricevuto nel 2° trimestre. In base al metodo di cassa, l’imposta da pagare è quella del 2° trimestre.

## Configurazione¶

Apri l’applicazione Contabilità ‣ Configurazione ‣ Impostazioni e nella sezione Imposte, attiva Per cassa.

In seguito, definisci il Registro imposte per cassa. Fai clic sul pulsante di collegamento esterno accanto al registro per aggiornare le proprietà predefinite come Nome registro, Tipo oppure Codice breve.

Nota

Per impostazione predefinita, le registrazioni contabili del registro Imposte con criterio di cassa vengono nominato utilizzando il codice di abbreviazione CABA.

Una volta fatto, apri l’app Contabilità ‣ Configurazione ‣ Contabilità: imposte per configurare le imposte che preferisci. È possibile creare una nuova imposta oppure aggiornare un’imposta esistente facendo clic su di essa.

La colonna Conto corrisponde ai conti transitori appropriati per registrare le imposte fino alla registrazione del pagamento.

Nella scheda Opzioni avanzate, scegli il tipo di Esigibilità fiscale. Seleziona Basata su pagamento così l’imposta verrà versata al momento della ricezione del pagamento della fattura. In seguito, puoi anche definire il Conto di transizione di cassa dove viene registrato l’importo dell’imposta purché la fattura originale non sia stata riconciliata.

## Impatto delle imposte con criterio di cassa sulla contabilità¶

Per illustrare l’impatto delle imposte con criterio di cassa sulle transazioni contabili, facciamo un esempio con le vendite di un prodotto che costa 1.000 $, con un’imposta di cassa del 15%.

Nella contabilità sono state create le seguenti voci e il resoconto fiscale è attualmente vuoto.

**Registro cliente (INV)**  
---  
**Debito** | **Credito**  
Credito 1.150 $ |   
| Reddito 1.000 $  
| Conto fiscale temporaneo 150 $  
  
Una volta ricevuto il pagamento, avverrà la registrazione:

**Registro banca (BANCA)**  
---  
**Debito** | **Credito**  
Banca 1.150 $ |   
| Credito 1.150 $  
  
Nota

Una volta registrato il pagamento, è possibile utilizzare il pulsante Registrazioni basate sulla contabilità di cassa sulla fattura per accedervi direttamente.

Infine, al momento della riconciliazione della fattura con il pagamento, viene creata automaticamente la registrazione sottostante:

**Registro imposte per cassa (Caba)**  
---  
**Debito** | **Credito**  
Conto di ricavo 1.000 $ |   
Conto fiscale temporaneo 150 $ |   
| Conto di ricavo 1.000 $  
| Imposte riscosse 150 $  
  
I movimenti contabili Conto di ricavo vs. Conto di ricavo sono neutre, ma sono necessarie per garantire rapporti fiscali corretti in Odoo con importi fiscali di base accurati.

Si consiglia di utilizzare un Conto imposte imponibili ricevute predefinito, in modo che il saldo sia pari a zero e il conto di ricavo non sia inquinato da movimenti contabili non necessari. A tal fine, accedi al menu Configurazione ‣ Impostazioni ‣ Imposte e seleziona un Conto imposte imponibili ricevute sotto Per cassa.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance/accounting/taxes/cash_basis.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](retention.html "Imposte alla fonte") |
  * [precedente](../taxes.html "Imposte") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Finanza](../../../finance.html) »
  * [Contabilità e fatturazione](../../accounting.html) »
  * [Imposte](../taxes.html) »
  * Imposte per cassa


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