# Odoo Online — Odoo 17.0 documentazione

### Navigazione

  * [indice](../genindex.html "Indice generale")
  * [moduli](../py-modindex.html "Indice del modulo Python") |
  * [successivo](odoo_sh.html "Odoo.sh") |
  * [precedente](hosting.html "Hosting") |
  * [Odoo 17.0 documentazione](../index-2.html) »
  * [Gestire i database](../administration.html) »
  * Odoo Online



# Odoo Online¶

[Odoo Online](https://www.odoo.com/trial) fornisce database privati che sono completamente gestiti e ospitati da Odoo. Può essere utilizzato per una produzione a lungo termine o per provare Odoo a fondo, comprese personalizzazioni che non richiedono codice.

Nota

Odoo Online non è compatibile con moduli personalizzati o con l’App Store Odoo.

I database Odoo Online sono accessibili utilizzando qualsiasi browser web e non richiedono un’installazione locale.

Per testare velocemente Odoo, sono disponibili risorse condivise [demo](https://demo.odoo.com/). Non è richiesta nesuna registrazione ma ogni istanza è attiva solo per poche ore.

## Gestire i database¶

Per gestire un database, vai su [manager database](https://www.odoo.com/my/databases) ed effettua l’accesso come amministratore del database.

Le principali opzioni di gestione del database sono disponibili facendo clic sul nome del database stesso, ad eccezione dell’opzione di aggiornamento alla quale si può accedere facendo clic sull’icona **freccia nel cerchio** accanto al nome del database. Viene visualizzata solo se vi sono aggiornamenti disponibili.

  * Aggiorna

  * Duplica

  * Rinomina

  * Scarica

  * Nomi di dominio

  * Etichette

  * Elimina

  * Contattaci

  * Invitare/rimuovere utenti

  * Web Services




## Aggiorna¶

Attiva un aggiornamento del database.

Vedi anche

Per maggiori informazioni sul processo di aggiornamento, consulta la [documetazione sull’aggiornamento di Odoo Online](upgrade.html#upgrade-request-test).

## Duplica¶

Crea una copia esatta del database che può essere utilizzata per eseguire test senza compromettere le operazioni giornaliere.

Importante

  * Selezionando l’opzione A scopo di test tutte le azioni esterne (e-mail, pagamenti, ordini di consegna, ecc.) sono disabilitate per impostazione predefinita nel database duplicato.

  * I database duplicati scadono automaticamente dopo 15 giorni.

  * È possibile creare un massimo di cinque duplicati per database. In circostanze eccezionali, contatta il [supporto](https://www.odoo.com/help) per aumentare il limite.




## Rinomina¶

Rinomina il database e l’URL corrispondente.

## Scarica¶

Scarica un file XIP contenente il backup del database.

Nota

Il backup dei database viene eseguito giornalmente come previsto dall’accordo [SLA sull’hosting cloud di Odoo](https://www.odoo.com/cloud-sla).

## Nomi di dominio¶

Utilizza un [nome di dominio](../applications/websites/website/configuration/domain_names.html) personalizzato per accedere al database via un altro URL.

Suggerimento

È possibile [registrare un nome di dominio gratuitamente](../applications/websites/website/configuration/domain_names.html#domain-name-register).

## Etichette¶

Aggiungi tag per individuare e ordinare facilmente i tuoi database-

Suggerimento

È possibile cercare i tag nella barra di ricerca.

## Elimina¶

Elimina un database all’istante.

Pericolo

Eliminare un database significa che tutti i dati verranno persi per sempre. L’eliminazione è immediata e si applica a tutti gli utenti. È consigliato creare un backup del database prima di eliminarlo.

Leggi attentamente il messaggio di avviso e procedi solo se le implicazioni relative alla rimozione del database sono chiare al 100%.

Nota

  * Solo un amministratore può eliminare un database.

  * Il nome del database viene reso visibile immediatamente a chiunque.

  * Non è possibile eliminare un database scaduto o collegato ad un abbonamento. In quel caso, contatta il [Supporto Odoo](https://www.odoo.com/help).




## Contattaci¶

Accedi alla [pagina di supporto Odoo.com](https://www.odoo.com/help) con tutti i dati del database precompilati

## Invitare/rimuovere utenti¶

Per invitare utenti, inserisci l’indirizzo e-mail del nuovo utente e fai clic su Invita. Per aggiungere più utenti, fai clic su Aggiungi più utenti.

Per eliminare degli utenti, selezionali e fai clic su Rimuovi.

Vedi anche

  * [Utenti](../applications/general/users.html)

  * [Account odoo.com](odoo_accounts.html)




## Web Services¶

In order to programmatically retrieve the list of the databases displayed in the [database manager](https://www.odoo.com/my/databases), call the method `list` of the model `odoo.database` via a [Web Service](../developer/howtos/web_services.html) call.

Inspired from the examples provided in the [Web Services](../developer/howtos/web_services.html) section, this is how to retrieve this list with the library `xmlrpc.client`:
    
    
    import xmlrpc.client
    
    USER = 'user@domain.tld'
    APIKEY = 'your_apikey'
    
    root = 'https://www.odoo.com/xmlrpc/'
    uid = xmlrpc.client.ServerProxy(root + 'common').login('openerp', USER, APIKEY)
    sock = xmlrpc.client.ServerProxy(root + 'object')
    databases_list = sock.execute('openerp', uid, APIKEY, 'odoo.database', 'list')
    

And here is the equivalent example with JSON-RPC:
    
    
    import json
    import random
    import urllib.request
    
    USER = 'user@domain.tld'
    APIKEY = 'your_apikey'
    
    def json_rpc(url, method, params):
        data = {
            'jsonrpc': '2.0',
            'method': method,
            'params': params,
            'id': random.randint(0, 1000000000),
        }
        req = urllib.request.Request(url=url, data=json.dumps(data).encode(), headers={
            "Content-Type": "application/json",
        })
        reply = json.loads(urllib.request.urlopen(req).read().decode('UTF-8'))
        if reply.get('error'):
            raise Exception(reply['error'])
        return reply['result']
    
    def call(url, service, method, *args):
        return json_rpc(url, 'call', {'service': service, 'method': method, 'args': args})
    
    url = 'https://www.odoo.com/jsonrpc'
    uid = call(url, 'common', 'login', 'openerp', USER, APIKEY)
    databases_list = call(url, 'object', 'execute', 'openerp', uid, APIKEY, 'odoo.database', 'list')
    

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/administration/odoo_online.rst)

### Navigazione

  * [indice](../genindex.html "Indice generale")
  * [moduli](../py-modindex.html "Indice del modulo Python") |
  * [successivo](odoo_sh.html "Odoo.sh") |
  * [precedente](hosting.html "Hosting") |
  * [Odoo 17.0 documentazione](../index-2.html) »
  * [Gestire i database](../administration.html) »
  * Odoo Online


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
  *[MPS]: Master Production Schedule
  *[OEE]: overall equipment effectiveness
  *[RFQ]: request for quotation
  *[RfQ]: Request for Quotation
  *[RfQs]: Requests for Quotation
  *[IU]: Interfaccia Utente
  *[UoM]: Unit of Measure
  *[PoS]: Point of Sale
  *[FBM]: Fulfilled By Merchant
  *[FBA]: Fulfilled by Amazon
  *[API]: Application Programming Interface
  *[IVA]: imposta sul valore aggiunto
  *[MRR]: monthly recurring revenue
  *[ARR]: Annual Recurring Revenue
  *[USB]: Universal Serial Bus
  *[IoT]: Internet of Things
  *[OS]: Operating System
  *[SO]: sales order
  *[MRP]: Material Requirement Planning
  *[DNS]: Domain name System
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
  *[POS]: Point of Sale
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
  *[LIFO]: Last In, First Out
  *[SAQ]: Self-Assessment Questionnaire
  *[VAT]: Value-Added Tax Identification
  *[SMP]: Service Metadata Publisher
  *[AVCO]: Average Costing
  *[OdA]: Ordine di acquisto
  *[sportello unico OSS]: One-Stop Shop
  *[IAPs]: in-app purchases
  *[SOs]: Sales Orders
  *[SRI]: servicio de rentas internas
  *[ATS]: Anexo Transaccional Simplificado
  *[FPS]: Service Public Federal Finances
  *[ADW]: Average Daily Wage
  *[SII]: Servicio de Impuestos Internos
  *[CAFs]: Folio Authorization Code
  *[DTE]: Documentos Tributarios Electrónicos
  *[RUT]: Registro único tributario
  *[CAF]: Folio Authorization Code
  *[SII’s]: Servicio de Impuestos Internos
  *[PPM]: Provisional Monthly Payments rate
  *[IFRS]: International Financial Reporting Standards
  *[PCMN]: Plan Comptable Minimum Normalisé
  *[FDM]: Fiscal Data Module
  *[VSC]: VAT signing card
  *[TSS]: Technical Security System
  *[DSFinV-K]: Digitale Schnittstelle der Finanzverwaltung für Kassensysteme
  *[PCGE]: Plan Contable General Empresarial
  *[SUNAT]: Superintendencia Nacional de Aduanas y de Administración Tributaria
  *[GRE]: Guía de Remisión Electrónica
  *[OTP]: One-time Password
  *[GAAP]: Generally Acceptable Accounting Practices
  *[AR]: Accounts Receivable
  *[AP]: Accounts Payable
  *[CoA]: chart of accounts
  *[SEC]: Securities and Exchange Commission
  *[CFS]: Cash Flow Statement
  *[ACH]: automated clearing house
  *[NACHA]: National Automated Clearing House Association
  *[DBA]: Danish Bookkeeping Act
  *[IRBM]: Inland Revenue Board of Malaysia
  *[ETA]: Egyptian Tax Authority
  *[FACe]: General Entrance for Electronic Invoices
  *[DIAN]: Dirección de Impuestos y Aduanas Nacionales
  *[UID-Nummer]: Umsatzsteueridentifikationsnummer
  *[AFIP]: Administración Federal de Ingresos Públicos
  *[DGI]: Dirección General Impositiva
  *[CAEs]: Constancia de Autorización de Emisión
  *[CUI]: Codul Unic de Inregistrare
  *[CIF]: *Codul de identificare fiscală*
  *[SLS]: Summary List of Sales
  *[SLP]: Summary List of Purchases
  *[TPAR]: Taxable Payments Annual Report
  *[AdE]: Agenzia Delle Entrate
  *[SdI]: Sistema di Interscambio
  *[PA]: Public Administration
  *[CUU]: Codice Univoco Ufficio
  *[CIG]: Codice Identificativo Gara
  *[CUP]: Codice Unico di Progetto
  *[HSM]: Hardware Security Module
  *[Ri.Ba.]: Ricevuta Bancaria
  *[NIC]: National Informatics Centre
  *[IRN]: Invoice Reference Number
  *[CGST]: Central Goods and Services Tax
  *[SGST]: State Goods and Service Tax
  *[IGST]: Integrated Goods and Services Tax
  *[ITC]: Income Tax Credit
  *[SAT]: Servicio de Administración Tributaria
  *[DIOT]: Declaración Informativa de Operaciones con Terceros
  *[RFC]: Registro Federal de Contribuyentes
  *[PAC]: Proveedor Autorizado de Certificación / Authorized Certification Provider
  *[PUE]: Pago en una Sola Exhibición/Payment in a Single Exhibition
  *[PPD]: Pago en Parcialidades o Diferido/Payment in Installements or Deferred
  *[CFDI]: Comprobante Fiscal Digital por Internet
  *[OSCU]: Online Sales Control Unit
  *[BOM]: bill of materials
  *[Bacs]: Bankers' Automated Clearing Services
  *[RCM]: Reverse Charge Mechanism
  *[PDT]: Payment Data Transfer
  *[ECO]: Engineering Change Order
  *[ECOs]: Engineering Change Orders
  *[BoMs]: Bills of Materials
  *[MOs]: Manufacturing Orders
  *[QCP]: Quality Control Point
  *[QCPs]: Quality Control Points
  *[RO]: Repair Order
  *[POs]: Purchase Orders
  *[PLM]: Product Lifecycle Management
  *[PO]: Purchase Order
  *[MTO]: Make to Order
  *[SVLs]: stock valuation layers
  *[SP]: Scrap Order
  *[DO]: Delivery Order
  *[RFQs]: Requests for Quotation
  *[EORI]: Economic Operators' Registration and Identification
  *[ZPL]: Zebra Programming Language
  *[DOs]: Delivery Orders
  *[FIFO]: First In, First Out
  *[FEFO]: First Expiry, First Out
  *[UoMs]: Units of Measure
  *[MTBF]: Mean Time Between Failure
  *[MTTR]: Mean Time To Repair
  *[EAN]: European Article Number
  *[UPC]: Universal Product Code
  *[GTIN]: Global Trade Item Number
  *[GTINs]: Global Trade Item Numbers
  *[A.I.]: Application Identifier
  *[CSV]: comma separated value
  *[SLAs]: Service Level Agreements
  *[SLA]: Service Level Agreement
  *[UTM]: Urchin Tracking Module
  *[GTM]: Google Tag Manager
  *[CDN]: Content Delivery Network
  *[CORS]: Cross-Origin Resource Sharing
  *[HTML]: HyperText Markup Language
  *[UI]: user interface
  *[ToS]: Terms of Service
  *[NRR]: non-recurring revenue
  *[VoIP]: Voice over Internet Protocol
  *[SIP]: Session Initiation Protocol
  *[US]: United States
  *[MP3]: MPEG Audio Layer 3
  *[WAV]: Waveform Audio File Format