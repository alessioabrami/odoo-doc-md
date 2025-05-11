# Reportistica in PDF — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](approval_rules.html "Regole di approvazione") |
  * [precedente](automated_actions/webhooks.html "Webhook") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
  * [Studio](../studio.html) »
  * Reportistica in PDF



# Reportistica in PDF¶

Grazie a Studio, è possibile modificare resoconti in PDF esistenti (ad es., fatture, preventivi, ecc.) oppure crearne di nuovi.

## Layout predefinito¶

Il layout predefinito dei resoconti non è gestito con Studio. Vai su Impostazioni, in seguito, nella sezione Aziende della pagina principale, fai clic su Configura layout documento. Le impostazioni relative al layout sono specifice per ogni azienda ma si applicano a tutti i resoconti.

Suggerimento

È possibile vedere come le diverse impostazioni influenzano il layout del resoconto nell’anteprima sul lato destro della finestra Configura layout documento. Quando si crea o si modifica un resoconto, è possibile vedere un’anteprima dello stesso facendo clic su Stampa anteprima sul lato sinistro dello schermo.

Usa le seguenti impostazioni:

  * Struttura: sono disponibili sette layout:

LightBoxedBoldStripedBubbleWaveFolder



  * Sfondo: sono disponibili i seguenti sfondi:

    * Vuoto: non viene mostrato nulla.

    * Logo demo: viene mostrato un logo demo sullo sfondo.

    * Personalizzato: carica un’immagine di sfondo.



  * Testo, sono disponibili otto font: Lato, Roboto, Open Sans, Montserrat, Oswald, Raleway, Tajawal (che supporta le scritture arabe e latine) e Fira Mono. Apri il [sito web Google Fonts](https://fonts.google.com/) per avere un’anteprima.



  * Logo azienda: fai clic sul pulsante Modifica per caricare o modificare un logo. Il logo verrà aggiunto al record dell’azienda nel modello _Azienda_ a cui puoi accedere aprendo le Impostazioni e poi facendo clic su Aggiorna info nella sezione Aziende.



  * Colori: modifica i colori primari e secondari utilizzati per strutturare i resoconti. I colori predefiniti sono generati automaticamente in base ai colori del logo.



  * Indirizzo: il nome e l’indirizzo dell’azienda vengono visualizzati nell’intestazione dei resoconti esterni. È possibile aggiungere più righe di testo.



  * Didascalia: viene visualizzata nell’intestazione dei resoconti esterni utilizzando i layout Luce, A righe, Bolla, Onda e Cartella e nel piè di pagina dei resoconti esterni che utilizzano i layout Scatola e Grassetto. Inoltre, puoi aggiungere più righe di testo.



  * Piè di pagina: questo testo viene utilizzato nel piè di pagina dei resoconti esterni. È possibile aggiungere più righe di testo. Inoltre, è possibile modificare la sezione utilizzando l”editor.



  * Formato carta: indica il formato predefinito dei resoconti. Puoi scegliere tra A4 (21 cm x 29,7 cm) e US Letter (21,59 cm x 27,54 cm). È possibile indicare il formato di ogni resoconto nel campo Formato carta in Studio.

Nota

A seconda delle applicazioni o dei moduli installati, possono essere disponibili altri formati di carta, ad esempio fogli di etichette per l’applicazione Magazzino o badge per eventi per l’applicazione Eventi.




## Creare nuovi resoconti in PDF¶

Per creare un nuovo resoconto per un [model](models_modules_apps.html), (ad es. ordini di vendita) accedi al modello, fai clic sul pulsante __( Commuta a Studio) e poi su Resoconti. Fai clic su Nuovo e nella finestra pop-up che appare, seleziona il tipo di resoconto. Viene utilizzato esclusivamente per determinare ciò che viene visualizzato nell’intestazione e nel piè di pagina:

  * Esterno:

    * L’intestazione mostra il logo dell’azienda nonché nome e indirizzo. Per i resoconti che usano i leyout Luce, A strisce, Bolla, Onda e Cartella, anche la didascalia appare nell’intestazione.

    * Il piè di pagina mostra i valori configurati nel campo Piè di pagina e il numero della pagina. Per i resoconti che usano i layout Scatola e Grassetto, la didascalia apparirà nel piè di pagina.

  * Interno: l’intestazione mostra la data e orario attuale dell’utente, il nome e indirizzo dell’azienda e il numero di pagina. Non c’è nessun piè di pagina.

  * Vuoto: non ci sono né intestazione né piè di pagina. Fai clic nell’angolo superiore sinistro della pagina per modificare il resoconto.




Una volta creato il resoconto, puoi iniziare a modificarlo.

## Modificare resoconti in PDF¶

Per accedere ai resoconti disponibili per un modello, accedi al modello stesso, fai clic sul pulsante __( Commuta a Studio) e poi fai clic su Resoconti. Seleziona un resoconto esistente per aprirlo.

In alternativa, puoi anche aprire Studio, fare clic su Resoconti e cercare un resoconto o modello specifico.

Importante

È vivamente consigiliato **duplicare** il resoconto standard e applicare modifiche alla versione duplicata. Per creare la copia di un resoconto, passa con il mouse sull’angolo in alto a destra del resoconto, fai clic sull’icona __( ellissi verticale) e poi su Duplica.

### Opzioni¶

Una volta selezionato o creato un resoconto, puoi utilizzare le opzioni nella parte sinistra dello schermo per:

  * Modifica il Nome resoconto. Il nuovo nome viene applicato ovunque (in Studio, nel menu Stampa sotto l’icona __( ingranaggio) nella vista modulo e nel nome del file PDF).

  * Modifica il Formato carta. Se non viene selezionato nessun valore, verrà utilizzato il formato indicato nel layout predefinito.

  * Mostra nel menu stampa: per aggiungere il resoconto al menu Stampa nella vista modulo.

  * Ricarica da allegato: per salvare il resoconto come allegato al record la prima volta che viene generato e ricaricare la versione originale del resoconto ogni volta che viene generato. Questa funzione è richiesta dalla legge per le fatture e viene utilizzata principalmente in questo caso.

  * Limitare visibilità ai gruppi: per limitare la disponibilità del resoconto in PDF a un [gruppo di utenti](../general/users/access_rights.html) specifico.

  * Modifica fonti: per modificare il resoconto direttamente nel file XML.

  * Resetta resoconto: per annullare tutte le modifiche apportate al resoconto e ripristinare la versione standard.

  * Stampa anteprima: per generare e scaricare un’anteprima del resoconto.




### Editor resoconti¶

L’editor di resoconti ti permette di modificare il contenuto e la formattazione del resoconto.

Suggerimento

  * È possibile Annullare o Ripristinare le modifiche utilizzando i pulsanti specifici oppure le scelte rapide da tastiera `CTRL` \+ `Z` e `CTRL` \+ `Y`.

  * Le modifiche vengono salvate automaticamente quando esci dal resoconto oppure manualmente utilizzando il pulsante Salva.

  * È possibile ripristinare il resoconto alla versione standard facendo clic sul pulsante Ripristina resoconto nella parte sinistra dello schermo.




Importante

La modifica dell’intestazione e del piè di pagina di un resoconto impatta tutti i resoconti standard e personalizzati.

#### Blocchi condizionali¶

I rettangoli tratteggiati rappresentano **blocchi condizionali** (istruzioni _if/else_). Vengono utilizzati per mostrare/nascondere contenuti in base a condizioni specifiche. Fai clic sul blocco per vedere le condizioni.

Seleziona un valore per avere l’anteprima dell’output corrispondente e modificalo se necessario.

Nota

Le condizioni possono essere modificate nel file XML.

#### Altri contenuti¶

Esistono due tipi di testo nei resoconti:

  * testo statico, ad es., il testo non evidenziato in blu, che può essere modificato direttamente nell’editor;

  * Testo dinamico, ad es., il testo evidenziato in blu, che viene sostituito dai valori del [campo](fields.html) quando viene generato il resoconto, ad esempio il numero di OdV o la data del preventivo.




Puoi aggiungere del contenuto nel resoconto (ad es. campi, elenchi, tabelle, immagini, banner, ecc.) utilizzando dei comandi. Digita `/` per aprire il [powerbox](../essentials/html_editor.html#essentials-html-editor-commands), e poi scrivi il nome del comando o selezionalo dall’elenco.

Per aggiungere del testo statico al resoconto, scrivi il testo dove vuoi che appaia.

Per modifiche più avanzate, puoi modificare direttamente il resoconto nell’XML.

##### Aggiungere un campo¶

Per aggiungere un campo, digita `/` e seleziona il comando Campo. Nell’elenco che apparirà, seleziona o cerca il campo, fai clic sulla freccia a destra accanto al nome del campo così da accedere all’elenco dei campi correlati se necessario. In seguito, specifica il valore predefinito che verrà mostrato se il campo non è completato nel record e premio `Invio`.

##### Aggiungere o modificare una tabella¶

Esistono due tipi di tabelle per i resoconti:

  * tabelle statiche, utilizzate per mostrare campi o testi statici. Per questo tipo di tabella, è necessario stabilire il numero di colonne e righe.

  * Tabelle dinamiche utilizzate per mostrare dati da [campi di relazione](fields.html#studio-fields-relational-fields). Per questo tipo di tabella, si definisce solo il numero di colonne quando si aggiunge la tabella stessa. Il numero di righe del resoconto generato sarà determinato dal numero di record del modello correlato che sono collegati al modello corrente.

Example

In un resoconto sugli ordini di vendita, viene utilizzata una tabella dinamica per mostrare le righe d’ordine relative all’ordine di vendita. Se l’ordine di vendita contiene 10 righe d’ordine, la tabella nel resoconto generato ha 10 righe. Invece, se contiene due righe d’ordine, la tabella ha due righe.




###### Aggiungere o modificare una tabella statica¶

Per aggiungere una tabella statica, digita `/` e seleziona il comando Tabella. Determina il numero di colonne e di righe della tabella stessa. Una volta aggiunta, è possibile iniziare a modificarla.

È possibile inserire, spostare ed eliminare colonne e righe utilizzando gli strumenti della tabella. Posiziona il cursore in cima alla colonna o a sinistra della riga, poi fai clic sul rettangolo viola e seleziona un’opzione.

Per ridimensionare una colonna, trascina il bordo della colonna stessa nella posizione desiderata. Ripristina tutte le colonne alla loro dimensione standard selezionando Ripristina dimensione dagli strumenti della tabella.

Aggiungi il campo che preferisci in una cella oppure aggiungi del testo statico iniziando a scrivere.

Suggerimento

Per aggiungere testo in modo strutturato senza usare una tabella, si possono usare le colonne. Per aggiungere colonne, digita `/` e seleziona il comando appropriato: 2 colonne, 3 colonne o 4 colonne.

###### Aggiungi o modifica una tabella dinamica¶

> Nota
> 
>   * Solo le relazioni di tipo `unoamolti` e `moltiamolti` possono essere mostrate come tabelle dinamiche.
> 
>   * Una tabella dinamica esistente in un resoconto standard ha una struttura più complessa di una tabella dinamica aggiunta dall’utente. Per tali tabelle è possibile inserire o eliminare colonne. Tuttavia, non è possibile spostare colonne o inserire, spostare o eliminare righe.
> 
> 


Per aggiungere una tabella dinamica, digita `/` e seleziona il comando Tabella dinamica. Nell’elenco che si apre, seleziona o cerca la relazione su cui si baserà la tabella e premi `Invio`. Una volta aggiunta la tabella, è possibile iniziare a modificarla.

È possibile inserire, spostare ed eliminare colonne utilizzando gli strumenti tabella, come per una tabella statica. È anche possibile inserire righe statiche che appariranno sopra o sotto le righe generate.

Per aggiungere un campo a una cella, elimina il testo segnaposto e aggiungi il campo desiderato. La finestra di dialogo che si apre mostra l’oggetto di origine del campo (ad esempio, il modello _Righe ordine_) e l’elenco dei campi disponibili.

Sostituisci l’etichetta Nome colonna con l’etichetta che preferisci.

Nota

La riga predefinita si ripete automaticamente sul contenuto del campo, generando una riga sul resoconto per ogni valore del campo (ad esempio, una riga per riga d’ordine).

##### Formattazione¶

Per formattare il testo nel resoconto, selezionalo e poi applica la formattazione usando le opzioni [nell’editor di testi](../essentials/html_editor.html).

> ### Modificare l’XML del resoconto¶

Avvertimento

Modificare direttamente l’XML potrebbe causare problemi durante gli [aggiornamenti](../../administration/upgrade.html). Se ciò accade, copia le modifiche dal vecchio database e aggiungile al database aggiornato.

Per modificare l’XML di un resoconto, fai clic su Modifica fonti nel pannello a sinistra.

#### Esempi¶

Modify the widget of a field

> Per modificare la presentazione dei dati nel resoconto, puoi modificare il [widget](fields.html) predefinito di un campo manualmente. Nell’esempio seguente, la data dell’ordine mostra la data e l’ora per impostazione predefinita, mentre il prezzo unitario ha una precisione predefinita di due cifre decimali.
>     
>     
>     <div class="oe_structure">
>      <span t-field="doc.date_order"/>
>      <span t-field="doc.price_unit"/>
>     </div>
>     

Utilizzando `t-options`, in questo caso l’opzione `widget`, i campi possono essere modificati per mostrare solo la data e viene applicata una precisione di quattro decimali, rispettivamente:

> 
>     <div class="oe_structure">
>      <span t-field="doc.date_order" t-options="{'widget': 'date'}"/>
>      <span t-field="doc.price_unit" t-options="{'widget': 'float', 'precision': 4}"/>
>     </div>
>     

Conditional blocks

Se vuoi mostrare/nascondere del contenuto in base a condizioni specifiche, puoi aggiungere manualmente istruzioni di controllo `if/else` nel resoconto in XML.

Ad esempio, se vuoi nascondere una tabella dati personalizzata e non ci sono tag, puoi usare l’attributo `t-if` per stabilire la condizione, che in seguito viene valutata come `Vera` o `Falsa`. La tabella non verrà mostrata se nel preventivo non sono presenti tag.
    
    
    <!-- table root element -->
    <table class="table" t-if="len(doc.tag_ids) > 0">
        <!-- thead = table header, the row with column titles -->
        <thead>
            <!-- table row element -->
            <tr>
                <!-- table header element -->
                <th>ID</th>
                <th>Name</th>
            </tr>
        </thead>
        <!-- table body, the main content -->
        <tbody>
            <!-- we create a row for each subrecord with t-foreach -->
            <tr t-foreach="doc.tag_ids" t-as="tag">
                <!-- for each line, we output the name and price as table cells -->
                <td t-out="tag.id"/>
                <td t-out="tag.name"/>
            </tr>
        </tbody>
    </table>
    

Se vuoi mostrare un altro blocco nel caso l’istruzione `t-if` venga valutata come `Falsa`, puoi specificarla utilizzando l’istruzione `t-else`. Il blocco `t-else` deve seguire direttamente il blocco `t-if` nella struttura del documento. Non è necessario specificare alcuna condizione nell’attributo `t-else`. Ad esempio, mostriamo un messaggio veloce che spiega che non ci sono tag nel preventivo:
    
    
    <!-- table root element -->
    <table class="table" t-if="len(doc.tag_ids) > 0">
        <!-- thead = table header, the row with column titles -->
        <thead>
            <!-- table row element -->
            <tr>
                <!-- table header element -->
                <th>ID</th>
                <th>Name</th>
            </tr>
        </thead>
        <!-- table body, the main content -->
        <tbody>
            <!-- we create a row for each subrecord with t-foreach -->
            <tr t-foreach="doc.tag_ids" t-as="tag">
                <!-- for each line, we output the name and price as table cells -->
                <td t-out="tag.id"/>
                <td t-out="tag.name"/>
            </tr>
        </tbody>
    </table>
    <div class="text-muted" t-else="">No tag present on this document.</div>
    

Utilizzando la scrittura `t-if/t-else`, l’editor del resoconto riconosce che queste sezioni si escludono a vicenda e dovrebbero essere mostrate come blocchi condizionali:

Puoi modificare le condizioni utilizzando l’editor per ottenere l’anteprima dell’output:

Se vuoi avere più opzioni, puoi anche utilizzare direttive `t-elif` per aggiungere condizioni intermedie. Ad esempio, ecco come cambia il titolo dei resoconti degli ordini di vendita in base alla condizione del documento sottostante.
    
    
    <h2 class="mt-4">
        <span t-if="env.context.get('proforma', False) or is_pro_forma">Pro-Forma Invoice # </span>
        <span t-elif="doc.state in ['draft','sent']">Quotation # </span>
        <span t-else="">Order # </span>
        <span t-field="doc.name">SO0000</span>
    </h2>
    

Il titolo _Fattura proforma_ , viene utilizzato in base ad alcune condizioni contestuali. Se queste condizioni non vengono rispettate e lo stato del documento è `bozza` o `inviato` allora il _Preventivo_ verrà utilizzato. Se nessuna di queste condizioni viene rispettata, il titolo del resoconto diventa _Ordine_.

Images

Lavorare con delle immagini in un resoconto può essere complesso, in quanto un controllo preciso delle dimensioni delle immagini e dei comportamenti non è sempre scontato. Puoi inserire campi immagine utilizzando l’editor di resoconti (tramite il comando campo) ma per un migliore controllo di dimensionamento e posizionamento è meglio inserirli nell’XML utilizzando la direttiva `t-field` seguita dagli attributi `t-options`.

Ad esempio, il seguente codice genera il campo `image_128` del prodotto della riga come un’immagine di 64px di larghezza (con un’altezza automatica basata sul formato dell’immagine).
    
    
    <span t-field="line.product_id.image_128" t-options-widget="image" t-options-width="64px"/>
    

Le seguenti opzioni sono disponibili per i widget immagine:

  * `width`: larghezza dell’immagine, di solito in pixel o unità di lunghezza CSS (ad es., `rem`) (lasciare vuoto per la larghezza automatica)

  * `height`: altezza dell’immagine, di solito in pixel o unità di lunghezza CSS (ad es., `rem`) (lasciare vuoto per altezza automatica).

  * `class`: classi CSS applicate al tag `img`; [Classi Bootstrap disponibili](https://getbootstrap.com/docs/5.1/content/tables).

  * `alt`: testo alternativo dell’immagine

  * `style`: attributo stile; permette di modificare gli stili in modo più libero rispetto a quanto avviene con le [classi Bootstrap](https://getbootstrap.com/docs/5.1/content/tables).




Questi attributi devono contenere stringhe come ad esempio contenuto tra due coppie di virgolette `t-options-width="'64px'"` (o in alternativa un’espressione Python valida).

Nota

Il widget immagine non può essere utilizzato in un tag `img`. Al contrario, configura la direttiva `t-field` in uno `span` (per del contenuto in riga) oppure il nodo `div` (per del contenuto in blocco).

Ad esempio, aggiungiamo una colonna con l’immagine del prodotto nella tabella del preventivo:
    
    
    <table class="table table-sm o_main_table table-borderless mt-4">
        <thead style="display: table-row-group">
            <tr>
                <th>Image</th>
                <th name="th_description" class="text-start">Description</th>
                <th>Product Category</th>
                <th name="th_quantity" class="text-end">Quantity</th>
                <th name="th_priceunit" class="text-end">Unit Price</th>
    [...]
            <t t-foreach="lines_to_report" t-as="line">
                <t t-set="current_subtotal" t-value="current_subtotal + line.price_subtotal"/>
                <tr t-att-class="'bg-200 fw-bold o_line_section' if line.display_type == 'line_section' else 'fst-italic o_line_note' if line.display_type == 'line_note' else ''">
                    <t t-if="not line.display_type">
                       <td>
                           <span t-field="line.product_template_id.image_128"
                                 t-options-widget="'image'"
                                 t-options-width="'64px'"
                                 t-options-class="'rounded-3 shadow img-thumbnail'"
                               />
                       </td>
                        <td name="td_name"><span t-field="line.name">Bacon Burger</span></td>
                        <td t-out="line.product_id.categ_id.display_name"/>
    

L’attributo `t-options-width` restringe la larghezza dell’immagine a 64 pixel e le classi Bootstrap utilizzate in `t-options-width` creano un bordo simile a una miniatura con angoli arrotondati e l’ombra.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/studio/pdf_reports.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](approval_rules.html "Regole di approvazione") |
  * [precedente](automated_actions/webhooks.html "Webhook") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
  * [Studio](../studio.html) »
  * Reportistica in PDF


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
  *[PoS]: Point of Sale
  *[FBM]: Fulfilled by Merchant
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