# Gestire le opportunità perse — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](merge_similar.html "Unire lead e opportunità simili") |
  * [precedente](../pipeline.html "Organizzare il flusso") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Organizzare il flusso](../pipeline.html) »
  * Gestire le opportunità perse



# Gestire le opportunità perse¶

Not every opportunity results in a successful sale. To keep the pipeline up-to-date, _lost_ opportunities need to be identified. Specifying why an opportunity was lost provides additional insight that can prove useful for future opportunities.

## Contrassegnare un’opportunità come persa¶

To mark an opportunity as lost, first open the CRM app, and select an opportunity from the pipeline, by clicking on its corresponding Kanban card. Doing so reveals that opportunity’s detail form.

In seguito, fai clic su Persa, nella parte in alto del modulo con i dettagli dell’opportunità.

This opens the Mark Lost pop-up window. From the Lost Reason drop-down menu, choose an existing lost reason. If no applicable reason is available, create a new one by entering it into the Lost Reason field, and clicking Create.

È possibile aggiungere note e commenti extra al motivo della perdita nel campo Nota di chiusura.

Suggerimento

Nella finestra pop-up Imposta a persa, non sono necessari né il campo Motivo perdita né il campo Nota di chiusura. Tuttavia, ti consigliamo di includere queste informazioni per motivi di tracciabilità, responsabilità e rendicontazione.

Una volta aggiunte tutte le informazioni desiderate nella finestra pop-up Imposta a persa, fai clic sul pulsante Imposta a persa.

Dopo aver fatto clic su Imposta a persa, un banner rosso dal titolo Persa verrà aggiunto nell’angolo in alto a destra dell’opportunità.

Nota

Per contrassegnare un’opportunità _non attiva_ (archiviata) come persa, inserisci il valore `0` percento nel campo Probabilità.

## Creare/modificare motivi perdita¶

Per creare un nuovo motivo di perdita o modificarne uno esistente, accedi all’app CRM ‣ Configurazione ‣ Motivi perdita.

To edit an existing lost reason:

  1. Click on the reason to be edited to highlight it.

  2. Change the selected lost reason by editing the Description field.

  3. When finished, click Save in the upper-left corner.




To create a new lost reason:

  1. Click New in the upper-left corner of the Lost Reasons page.

  2. In the new blank line, click in the Description field, then type the new lost reason.

  3. When finished, click Save.




## Visualizzare opportunità perse¶

To retrieve lost opportunities in Odoo _CRM_ , open the CRM app. On the main Pipeline dashboard, click into the Search… bar at the top of the page, and remove all of the default filters.

Open the Filters drop-down menu, by clicking the 🔻(triangle pointed down) icon to the right of the Search… bar to open the drop-down menu containing Filters, Group By, and Favorites options, designated into respective columns.

Seleziona l’opzione the Persa dalla sezione Filtri. Dopo aver selezionato Persa, solo le opportunità contrassegnate come `Perse` appariranno nella pagina Pipeline.

### Organizzare le opportunità per motivo perdita¶

To filter opportunities by a specific lost reason, click the 🔻(triangle pointed down) icon to the right of the Search… bar again to open the drop-down menu. In addition to the Lost filter, under the Filters column, click Add Custom Filter, which opens an Add Custom Filter pop-up window.

On the Add Custom Filter pop-up window, click in the first field, and type `Lost Reason` in the Search… bar, or scroll to search through the list to locate it. Then, click into the next field, and select = from the drop-down menu. Click into the third field, and select a lost reason from the drop-down menu. Finally, click Add.

Suggerimento

Per visualizzare i risultati per più di un motivo di smarrimento, seleziona l’operatore è in nel secondo campo del filtro personalizzato nella finestra pop-up Aggiungi filtro personalizzato. La scelta di questo operatore consente di selezionare più motivi di perdita nel terzo campo.

## Ripristinare le opportunità perse¶

To restore a lost opportunity, open the CRM app to reveal the Pipeline dashboard. Or, navigate to CRM app ‣ Sales ‣ My Pipeline. From here, click the 🔻(triangle pointed down) icon to the right of the Search… bar to open the drop-down menu that contains Filters, Group By, and Favorites columns.

Nella colonna Filtri, seleziona Persa. Così facendo, nella pagina Pipeline, verranno svelate tutte le opportunità perse.

Suggerimento

To see all opportunities in the database, remove the default My Pipeline filter from the Search… bar.

Then, click on the Kanban card of the desired lost opportunity to restore, which opens that opportunity’s detail form.

Dal modulo con i dettagli dell’opportunità persa, fai clic su Ripristina nell’angolo in alto a sinistra. Il banner rosso Persa scomparirà dal modulo dell’opportunità.

### Ripristinare più opportunità perse in una volta¶

Per ripristinare più opportunità perse in una volta, accedi alla dashboard principale della pipeline nell’app _CRM_ , apri il menu a tendina Filtri e seleziona l’opzione Persa.

Next, select the list view option, represented by the ≣ (list) icon in the upper-right corner. Doing so places all the opportunities from the Pipeline page in a list view. With the list view chosen, select the checkbox to the left of each opportunity to be restored.

Once the desired opportunities have been selected, click the ⚙️ Actions drop-down menu at the top of the Pipeline page. From the ⚙️ Actions drop-down menu, select Unarchive.

In questo modo si rimuovono le opportunità selezionate dalla pagina Pipeline perché non rientrano più nei criteri del filtro Persa. Elimina il filtro Persa dalla barra di ricerca per visualizzare le opportunità appena ripristinate.

## Gestire lead persi¶

If _Leads_ are enabled on a database, they can be marked as _lost_ in the same manner as opportunities. Leads use the same lost reasons as opportunities.

Nota

To enable leads, navigate to CRM app ‣ Configuration ‣ Settings and check the Leads checkbox. Then, click Save. This adds a new Leads menu to the header menu bar at the top of the page.

### Segnare un contatto come perso¶

To mark a lead as lost, navigate to CRM app ‣ Leads, and select a lead from the list. Doing so reveals that lead’s detail form.

In seguito, fai clic su Persa nella parte alta del modulo.

This opens the Mark Lost pop-up window. From the Lost Reason drop-down menu, choose an existing lost reason. If no applicable reason is available, create a new one by entering it into the Lost Reason field, and clicking Create.

È possibile aggiungere ulteriori note e commenti sotto il motivo della perdita indicato nel campo Note di chiusura.

Una volta aggiunte tutte le informazioni desiderate nella finestra pop-up Imposta a persa, fai clic sul pulsante Imposta a persa.

### Ripristinare lead persi¶

To restore a lost lead, navigate to CRM app ‣ Leads, then click the 🔻 (triangle pointed down) icon to the right of the Search… bar to open the drop-down menu that contains the Filters, Group By, and Favorites columns.

Nella colonna Filtri, seleziona Persa. Così facendo, tutti i lead persi verranno mostrati nella pagina Lead.

In seguito, fai clic sul lead perso che vuoi ripristinare, per aprire con i moduli del lead.

Dal modulo con i dettagli del lead perso, fai clic su Ripristina nell’angolo in alto a sinistra. Il banner rosso Persa scomparirà dal modulo del lead.

### Ripristinare più lead alla volta¶

Per ripristinare più lead in una sola volta, apri il modulo CRM ‣ Lead, apri il menu a tendina Filtri e seleziona l’opzione Perso. Seleziona la casella di controllo a sinistra di ogni lead da ripristinare.

Once the desired leads have been selected, click the ⚙️ Actions drop-down menu at the top of the Leads page. From the ⚙️ Actions drop-down menu, select Unarchive.

Doing so removes those selected leads from the Leads page because they no longer fit the Lost filter criteria. Delete the Lost filter from the Search… bar to reveal these newly-restored leads.

Vedi anche

[Analisi del flusso](../performance/win_loss.html)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/crm/pipeline/lost_opportunities.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](merge_similar.html "Unire lead e opportunità simili") |
  * [precedente](../pipeline.html "Organizzare il flusso") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [CRM](../../crm.html) »
  * [Organizzare il flusso](../pipeline.html) »
  * Gestire le opportunità perse


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
  *[FBM]: Fulfilled By Merchant
  *[FBA]: Fulfilled by Amazon
  *[API]: Application Programming Interface