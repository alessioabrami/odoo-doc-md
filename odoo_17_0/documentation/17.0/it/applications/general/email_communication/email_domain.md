# Configurare record DNS per inviare e-mail in Odoo — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](azure_oauth.html "Collegare Microsoft Outlook 365 a Odoo utilizzando Azure OAuth") |
  * [precedente](email_servers_outbound.html "Gestire messaggi in uscita") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Impostazioni generali](../../general.html) »
  * [Comunicazione in Odoo via e-mail](../email_communication.html) »
  * Configurare record DNS per inviare e-mail in Odoo



# Configurare record DNS per inviare e-mail in Odoo¶

La documentazione presenta tre protocolli di autenticazione complementari (SPF, DKIM e DMARC) utilizzati per dimostrare la legittimità di un mittente. La mancata osservanza di questi protocolli ridurrà notevolmente le possibilità che le e-mail arrivino a destinazione.

I database **Odoo online** e **Odoo.sh** che utilizzano l”**indirizzo del sottodominio di Odoo predefinito** (ad es., `@company-name.odoo.com`) sono preconfigurati per **inviare e-mail autenticate** conformi ai protocolli SPF, DKIM e DMARC.

Se scegli di utilizzare un **dominio personalizzato** , una **corretta configurazione dei record SPF e DKIM è fondamentale** per evitare che le e-mail vengano contrassegnate come spam o non consegnate ai destinatari.

Se utilizzi il [server e-mail Odoo predefinito per inviare e-mail da un dominio personalizzato](email_servers_outbound.html#email-outbound-custom-domain-odoo-server), i record SPF e DKIM devono essere configurati come illustrato di seguito. Se utilizzi un server e-mail in uscita, è necessario utilizzare i record SPF e DKIM specifici per quel servizio di posta elettronica e un dominio personalizzato.

Nota

I fornitori di servizi e-mail applicano regole diverse alle e-mail in entrata. Un e-mail potrebbe essere classificata come spam anche se ha superato i controlli SPF e DKIM.

## SPF (Sender Policy Framework)¶

Il protocollo Sender Policy Framework (SPF) consente al proprietario di un nome di dominio di specificare quali server possono inviare e-mail da quel dominio. Quando un server riceve un e-mail in entrata, verifica se l’indirizzo IP del server mittente è presente sull’elenco degli indirizzi IP consentiti secondo il record SPF del mittente.

In Odoo, il **test SPF viene eseguito sull’indirizzo di rimbalzo** indicato nel campo Alias di dominio presente nelle Impostazioni generali del database. Se utilizzi un dominio personalizzato come Alias di dominio, è necessario che sia conforme allo SPF.

La politica SPF di un dominio viene configurata utilizzando un record TXT. Il modo per creare o modificare il record dipende dal fornitore host della zona DNS del nome di dominio.

Se il nome di dominio non ha ancora un record SPF, creane uno utilizzando il seguente input:
    
    
    v=spf1 include:_spf.odoo.com ~all
    

Se il nome di dominio **ha già un record SPF, il record deve essere aggiornato**. Non crearne uno nuovo, perché un dominio deve avere solo un record SPF.

Example

Se il record TXT corrisponde a `v=spf1 include:_spf.google.com ~all`, modificalo per aggiungere `include:_spf.odoo.com`: `v=spf1 include:_spf.odoo.com include:_spf.google.com ~all`

Verifica il record SPF utilizzando uno strumento come [MXToolbox SPF Record Check](https://mxtoolbox.com/spf.aspx). Il processo per creare o modificare un record SPF dipende dal fornitore host della zona DNS del nome di dominio. I fornitori più comuni e la relativa documentazione sono elencati di seguito.

## DKIM (DomainKeys Identified Mail)¶

Il DomainKeys Identified Mail (DKIM) permette a un utente di autenticare le e-mail con la firma digitale.

Al momento dell’invio di un e-mail, il server e-mail Odoo include una firma DKIM unica nell’intestazione. Il server del destinatario decifra questa firma utilizzando il record DKIM nel nome di dominio del database. Se la firma e la chiave contenuta nel record corrispondono, il messaggio è autentico e non è stato alterato durante il trasporto.

L’abilitazione del DKIM è **richiesta** durante l’invio di e-mail **da un dominio personalizzato** che utilizza il server di posta di Odoo.

Per attivare il DKIM, aggiungi un record CNAME alla zona DNS del nome di dominio:
    
    
    odoo._domainkey IN CNAME odoo._domainkey.odoo.com.
    

Suggerimento

Se il nome di dominio corrisponde a `company-name.com`, assicurati di creare un sottodominio `odoo._domainkey.company-name.com` il cui nome canonico è `odoo._domainkey.odoo.com.`.

Il modo per creare o modificare un record CNAME dipende dal fornitore host della zona DNS del nome di dominio. I fornitori più comuni e la relativa documentazione sono elencati di seguito.

Verifica che il record DKIM sia valido utilizzando uno strumento come [MXToolbox DKIM Record Lookup](https://mxtoolbox.com/dkim.aspx). Scrivi `example.com:odoo` nello strumento di ricerca DKIM, specificando che il selettore che si sta testando è `odoo` per il dominio personalizzato `example.com`.

## DMARC (Domain-based Message Authentication, Reporting and Conformance)¶

Il record DMARC è un protocollo che unifica lo SPF e il DKIM.

Nota

Lo scopo di questa documentazione è di aiutare a **capire l’impatto del DMARC sulla consegna delle e-mail** , invece di fornire istruzioni precise per creare un record DMARC. Consulta la pagina [DMARC.org](https://dmarc.org/) per configurare il record DMARC.

Ci sono tre policy DMARC:

  * `p=none`

  * `p=quarantine`

  * `p=reject`




`p=quarantine` e `p=reject` danno istruzioni al server che riceve un’e-mail per mettere in quarantena l’e-mail o ignorarla se il controllo SPF o DKIM non riesce.

Nota

**Per superare il controllo DMARC, è necessario superare la verifica DKIM o SPF** e i domini devono essere allineati. Se il tipo di hosting è Odoo online, la configurazione DKIM sul dominio di invio è necessaria per superare il DMARC.

In generale, superare il DMARC significa che l’e-mail verrà inviata con successo. Tuttavia, è importante notare che **altri fattori come filtri spam possono rifiutare o mettere in quarantena un messaggio**.

`p=none` viene utilizzato affinché il proprietario del dominio riceva resoconti sulle entità che utilizzano il dominio. Non dovrebbe avere un impatto sulla consegna.

Example

`_dmarc IN TXT “v=DMARC1; p=none; rua=mailto:postmaster@example.com”` significa che resoconti DMARC aggregati verranno inviati a `postmaster@example.com`.

## Documentazione SPF, DKIM e DMARC di fornitori comuni¶

  * [OVH DNS](https://docs.ovh.com/us/en/domains/web_hosting_how_to_edit_my_dns_zone/)

  * [GoDaddy TXT record](https://www.godaddy.com/it/help/aggiunta-di-un-record-txt-19232)

  * [GoDaddy CNAME record](https://www.godaddy.com/it/help/aggiunta-di-un-record-cname-19236)

  * [NameCheap](https://www.namecheap.com/support/knowledgebase/article.aspx/317/2237/how-do-i-add-txtspfdkimdmarc-records-for-my-domain/)

  * [CloudFlare DNS](https://support.cloudflare.com/hc/en-us/articles/360019093151)

  * [Squarespace DNS records](https://support.squarespace.com/hc/en-us/articles/360002101888-Adding-custom-DNS-records-to-your-Squarespace-managed-domain)

  * [Azure DNS](https://learn.microsoft.com/it-it/azure/dns/dns-getstarted-portal)




Per testare al 100% la configurazione, utilizza lo strumento [Mail-Tester](https://www.mail-tester.com/) che offre una panoramica completa del contenuto e della configurazione per un’e-mail inviata. Il Mail-Tester può essere utilizzato anche per configurare i record per altri fornitori meno conosciuti.

Vedi anche

[Utilizzare Mail-Tester per configurare record SPF per corrieri specifici](https://www.mail-tester.com/spf/)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/general/email_communication/email_domain.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](azure_oauth.html "Collegare Microsoft Outlook 365 a Odoo utilizzando Azure OAuth") |
  * [precedente](email_servers_outbound.html "Gestire messaggi in uscita") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Impostazioni generali](../../general.html) »
  * [Comunicazione in Odoo via e-mail](../email_communication.html) »
  * Configurare record DNS per inviare e-mail in Odoo


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
  *[DNS]: Domain Name System
  *[SMTP]: Simple Mail Transfer Protocol
  *[SSL]: Secure Sockets Layer
  *[TLS]: Transport Layer Security
  *[SPF]: Sender Policy Framework
  *[DKIM]: DomainKeys Identified Mail
  *[DMARC]: Domain-based Message Authentication, Reporting, & Conformance
  *[CNAME]: nome canonico