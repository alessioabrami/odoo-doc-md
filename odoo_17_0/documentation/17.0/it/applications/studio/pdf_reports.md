# Reportistica in PDF — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](approval_rules.html "Regole di approvazione") |
  * [precedente](automated_actions.html "Regole di automazione") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
  * [Studio](../studio.html) »
  * Reportistica in PDF



# Reportistica in PDF¶

Grazie a Studio, è possibile modificare resoconti in PDF esistenti (ad es., fatture, preventivi, ecc.) oppure crearne di nuovi.

## Layout predefinito¶

Il layout predefinito dei resoconti non è gestito con Studio. Vai su Impostazioni, in seguito, nella sezione Aziende fai clic su Configura layout documento.

Suggerimento

Puoi vedere l’impatto delle varie impostazioni sul layout dei resoconti nell’anteprima dei resoconti stessi sulla destra oppure scaricare una fattura campione in PDF facendo clic su Scarica anteprima PDF.

Usa le seguenti impostazioni:

  * Layout, sono disponibili quattro layout:

LightBoxedBoldStriped



  * Font, ne sono disponibili sette: Lato, Roboto, Open Sans, Montserrat, Oswald, Raleway e Tajawal (che supporta le scritture arabe e latine). Apri il [sito web Google Fonts](https://fonts.google.com/) per avere un’anteprima.



  * Logo azienda: fai clic sul pulsante Modifica per caricare o modificare un logo. Il logo verrà aggiunto al record dell’azienda nel modello _Azienda_ a cui puoi accedere aprendo le Impostazioni e poi facendo clic su Aggiorna info nella sezione Aziende.



  * Colori: modifica i colori primari e secondari utilizzati per strutturare i resoconti. I colori predefiniti sono generati automaticamente in base ai colori del logo.



  * Sfondo layout, sono disponibili i seguenti sfondi:

    * vuoto, non viene visualizzato nulla

    * geometrico, sullo sfondo viene visualizzata un’immagine con forme geometriche

    * personalizzato, carica un’immagine di sfondo.



  * Tagline aziendale: viene visualizzata nell’intestazione dei resoconti esterni. È possibile aggiungere più righe di testo.



  * Dettagli azienda: vengono visualizzati nell’intestazione dei resoconti esterni. È possibile aggiungere più righe di testo.



  * Piè di pagina: questo testo viene utilizzato nel piè di pagina dei resoconti esterni. È possibile aggiungere più righe di testo. Inoltre, è possibile modificare la sezione utilizzando l”editor.



  * Formato carta: per indicare il formato predefinito dei resoconti. Puoi scegliere tra A4 (21 cm x 29,7 cm), US Letter (21,59 cm x 27,54 cm), oppure pagina codice QR. È possibile indicare il formato di ogni resoconto nel campo Formato carta in Studio.




## Creare nuovi resoconti in PDF¶

Per creare un nuovo resoconto di un modello, accedi al modello, fai clic sul pulsante **Apri Studio** e poi su Resoconti. Fai clic su Nuovo e, nella finestra pop-up che si apre, scegli il tipo di resoconto. Questo processo viene utilizzato esclusivamente per determinare ciò che viene visualizzato nell’intestazione e nel piè di pagina:

  * Esterno:

    * l’intestazione mostra il logo, la tagline e i dettagli dell’azienda;

    * Il piè di pagina mostra i valori impostati nel campo Piè di pagina e il numero di pagina.

  * Interno: l’intestazione mostra la data e l’orario attuale dell’utente, il Nome azienda e il numero di pagina. Il piè di pagina non c’è.

  * Vuoto: non ci sono né intestazione né piè di pagina. Fai clic nell’angolo superiore sinistro della pagina per modificare il rapporto.




Una volta creato il resoconto, puoi iniziare a modificarlo.

## Modificare resoconti in PDF¶

Per accedere ai resoconti disponibili per un modello, accedi al modello (ad es., ordini di vendita), fai clic sul pulsante **Apri Studio** , poi su Resoconti. Seleziona un resoconto esistente per aprirlo oppure creane uno nuovo.

Suggerimento

In alternativa, puoi anche aprire Studio, fare clic su Resoconti e cercare un resoconto o modello specifico.

Importante

È vivamente consigiliato **duplicare** il resoconto standard e applicare modifiche alla versione duplicata. Per creare la copia di un resoconto, passa con il mouse sull’angolo in alto a destra del resoconto, fai clic sull’icona dell’ellissi verticale (⋮) e poi su Duplica.

### Opzioni¶

Una volta selezionato o creato un resoconto, puoi utilizzare le opzioni nella parte sinistra dello schermo per:

  * Modifica il Nome resoconto. Il nuovo nome viene applicato ovunque (in Studio, sotto il pulsante Stampa e nel nome file PDF).

  * Modifica il Formato carta. Se non viene selezionato nessun valore, verrà utilizzato il formato indicato nel layout predefinito.

  * Mostra nel menu stampa: per aggiungere il resoconto al menu Stampa disponibile dal record.

  * Ricarica da allegato: per salvare il resoconto come allegato al record la prima volta che viene generato e ricaricare la versione originale del resoconto ogni volta che viene generato. Questa funzione è richiesta dalla legge per le fatture e viene utilizzata principalmente in questo caso.

  * Limitare visibilità ai gruppi: per limitare la disponibilità del resoconto in PDF a un [gruppo di utenti](../general/users/access_rights.html) specifico.

  * Modifica fonti: per modificare il resoconto direttamente nel file XML.

  * Resetta resoconto: per annullare tutte le modifiche apportate al resoconto e ripristinare la versione standard.

  * Stampa anteprima: per generare e scaricare un’anteprima del resoconto.




### Editor resoconti¶

L’editor di resoconti ti permette di modificare la formattazione e il contenuto di un resoconto.

Suggerimento

  * È possibile Annullare o Ripristinare modifiche utilizzando i pulsanti specifici oppure le scelte rapide da tastiera `CTRL Z` e `CTRL Y`.

  * Le modifiche vengono salvate automaticamente quando esci dal resoconto oppure manualmente utilizzando il pulsante Salva.

  * È possibile ripristinare il resoconto alla versione standard facendo clic sul pulsante Ripristina resoconto nella parte sinistra dello schermo.




Importante

La modifica dell’intestazione e del piè di pagina di un resoconto impatta tutti i resoconti standard e personalizzati.

#### Blocchi condizionali¶

I rettangoli tratteggiati rappresentano **blocchi condizionali** (opzioni _if/else_). Vengono utilizzati per mostrare/nascondere contenuti in base a condizioni specifiche. Fai clic sul blocco per vedere le condizioni.

Seleziona un valore per avere l’anteprima dell’output corrispondente e modificalo se necessario,

Nota

Le condizioni possono essere modificate in XML.

#### Altri contenuti¶

Esistono due tipi di testo nei resoconti:

  * testo statico, ad es., il testo non evidenziato in blu, che può essere modificato direttamente nell’editor;

  * Testo dinamico, ad es., il testo evidenziato in blu, che viene sostituito dai valori dei campi quando viene generato il resoconto, ad esempio il numero di OdV o la data dell’offerta.




Puoi aggiungere del contenuto nel resoconto (ad es. campi, elenchi, tabelle, immagini, banner, ecc.) utilizzando dei comandi. Digita `/` per aprire il [powerbox](../productivity/knowledge/articles_editing.html#knowledge-powerbox) e poi scrivi il nome del comando o selezionalo dall’elenco.

Per aggiungere del testo statico al resoconto, scrivi il testo dove vuoi che appaia.

Per modifiche più avanzate, puoi modificare direttamente il resoconto nell’XML.

##### Aggiungere un campo¶

Per aggiungere un campo, digita `/` e seleziona il comando Campo. Nell’elenco che apparirà, seleziona o cerca il campo, fai clic sulla freccia a destra accanto al nome del campo così da accedere all’elenco dei campi correlati se necessario. In seguito, specifica il valore predefinito e fai clic su `Invia`.

##### Aggiungere una tabella dati¶

Le tabelle di dati vengono utilizzate per mostrare [campi relazionali](fields.html#studio-fields-relational-fields). Per aggiungere una tabella dati, digita `/`, seleziona il comando Tabella dinamica e seleziona la relazione da mostrare nella tabella.

Nota

Solo le relazioni di tipo `unoamolti` e `moltiamolti` possono essere mostrate come tabelle dati.

Una volta che la tabella è stata aggiunta, puoi aggiungere colonne utilizzando gli strumenti correlati. Posiziona il cursore all’inizio della colonna, fai clic sul rettangolo viola e seleziona un’opzione.

In seguito, puoi inserire nelle colonne il campo che preferisci. La finestra di dialogo che si apre mostra l’oggetto d’origine del campo (ad es., il modello _Tag_) e l’elenco di campi disponibili.

Nota

  * La riga predefinita si ripete automaticamente sul contenuto del campo, generando una riga sul resoconto per ogni valore del campo (ad esempio, una riga per tag). È possibile aggiungere righe di contenuto statico sopra o sotto le righe generate, utilizzando gli strumenti tabella.

  * Inoltre, è possibile aggiungere tabelle di dati modificando il file XML del resoconto.




##### Formattazione¶

Per formattare il testo nel resoconto, selezionalo, poi formattalo utilizzando le opzioni nel [Text editor](../productivity/knowledge/articles_editing.html#knowledge-text-editor).

> ### Modificare l’XML del resoconto¶

Avvertimento

Modificare direttamente l’XML potrebbe causare problemi durante gli [aggiornamenti](../../administration/upgrade.html). Se ciò accade, copia le modifiche dal vecchio database e aggiungile al database aggiornato.

Per modificare l’XML di un resoconto, fai clic su Modifica fonti nel pannello a sinistra.

#### Esempi¶

Modify a non-compliant table

A volte, le tabelle non vengono riconosciute in maniera appropriata a causa di strutture complesse. In quei casi, puoi ancora modificarle manualmente nel resoconto in XML. Ad esempio, nel caso di un ordine di vendita, nell’XML puoi trovare la seguente struttura (semplificata per la documentazione):

> 
>     <!-- table root element -->
>     <table>
>         <!-- thead = table header, the row with column titles -->
>         <thead>
>             <!-- table row element -->
>             <tr>
>                 <!-- table header element -->
>                 <th>Name</th>
>                 <th>Price</th>
>             </tr>
>         </thead>
>         <!-- table body, the main content -->
>         <tbody>
>             <!-- we create a row for each subrecord with t-foreach -->
>             <tr t-foreach="record.some_relation_ids" t-as="line">
>                 <!-- for each line, we output the name and price as table cells -->
>                 <td t-out="line.name"/>
>                 <td t-out="line.price"/>
>             </tr>
>         </tbody>
>     </table>
>     
> 
> Per modificare una tabella, devi essere sicuro che ogni riga abbia lo stesso numero di celle dati. Ad esempio, nel caso illustrato sopra è necessario aggiungere una cella nella sezione dell’intestazione (con ad es., il titolo della colonna) e un altro nella sezione del corpo con il contenuto del campo (di solito, con una direttiva `t-out` or `t-field`).
>     
>     
>     <table> <!-- table root element -->
>         <thead> <!-- thead = table header, the row with column titles -->
>             <tr> <!-- table row element -->
>                 <th>Name</th> <!-- table header element -->
>                 <th>Price</th>
>                 <th>Category</th>
>             </tr>
>         </thead>
>         <tbody>  <!-- table body, the main content -->
>             <tr t-foreach="record.some_relation_ids" t-as="line">  <!-- we create a row for each subrecord with t-foreach -->
>                 <td t-out="line.name"/>  <!-- for each line, we output the name and price as table cells -->
>                 <td t-out="line.price"/>
>                 <td t-out="line.category_id.display_name"/>
>             </tr>
>         </tbody>
>     </table>
>     
> 
> Nota
> 
> Le celle possono estendersi su più righe o colonne. Per maggiori informazioni, vai sul [sito web Mozilla Developer Network](https://developer.mozilla.org/en-US/docs/Learn/HTML/Tables/Basics).
> 
> Ad esempio, puoi modificare il resoconto **Preventivo/Ordine** per aggiungere una colonna e mostrare la categoria prodotto nella tabella principale:
>
>> 
>>     <table class="table table-sm o_main_table table-borderless mt-4">
>>         <!-- In case we want to repeat the header, remove "display: table-row-group" -->
>>         <thead style="display: table-row-group">
>>             <tr>
>>                 <th name="th_description" class="text-start">Description</th>
>>                 <th>Product Category</th>
>>                 <th name="th_quantity" class="text-end">Quantity</th>
>>                 <th name="th_priceunit" class="text-end">Unit Price</th>
>>     [...]
>>                 <tr t-att-class="'bg-200 fw-bold o_line_section' if line.display_type == 'line_section' else 'fst-italic o_line_note' if line.display_type == 'line_note' else ''">
>>                     <t t-if="not line.display_type">
>>                         <td name="td_name"><span t-field="line.name">Bacon Burger</span></td>
>>                         <td t-out="line.product_id.categ_id.display_name"/>
>>                         <td name="td_quantity" class="text-end">
>>                             <span t-field="line.product_uom_qty">3</span>
>>                             <span t-field="line.product_uom">units</span>
>>                             <span t-if="line.product_packaging_id">
>>     

Add a data table

Per aggiungere una tabella in XML, devi conoscere i nomi dei campi e degli oggetti a cui vuoi accedere e che vuoi mostrare. Ad esempio, aggiungiamo una tabella che illustra i tag di un ordine di vendita:
    
    
    <!-- table root element -->
    <table class="table">
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
    

Nota

Quando aggiungi tabelle manualmente, personalizzale utilizzando le [classi Bootstrap](https://getbootstrap.com/docs/5.1/content/tables),

Conditional blocks

Se vuoi mostrare/nascondere del contenuto in base a condizioni specifiche, puoi aggiungere manualmente opzioni di controllo `if/else` nel resoconto in XML.

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

Lavorare con delle immagini in un resoconto può essere complesso, in quanto un controllo preciso delle dimensioni delle immagini e dei comportamenti non è sempre scontato. Puoi inserire campi immagine utilizzando l’editor di resoconti (tramite il comando /Field (campo)) ma per un migliore controllo di dimensionamento e posizionamento è meglio inserirli nell’XML utilizzando la direttiva `t-field` seguita dagli attributi `t-options`.

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

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/studio/pdf_reports.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](approval_rules.html "Regole di approvazione") |
  * [precedente](automated_actions.html "Regole di automazione") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Documentazione Utente](../../applications.html) »
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