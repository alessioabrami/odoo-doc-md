# Acconti — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](proforma.html "Fatture proforma") |
  * [precedente](invoicing_policy.html "Fatture basate su quantità ordinate o consegnate") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Invoicing Method](../invoicing.html) »
  * Acconti



# Acconti¶

A down payment is a partial payment made by the buyer when a sales contract is concluded. This implies both parties” (seller and buyer) full commitment to honor the contract.

With a down payment, the buyer pays a portion of the total amount owed while agreeing to pay the remaining amount at a later date. In turn, the seller provides goods or services to the buyer after accepting the down payment, trusting that the remaining amount will be paid later on.

## Crea fatture¶

When a sales order is confirmed, the option to create an invoice becomes available, via the Create Invoice button, located in the upper-left corner of the sales order form. When clicked, a Create invoices pop-up appears.

Nota

Le fatture vengono create automaticamente come bozze, in modo da poter essere revisionate prima della convalida.

Nel pop-up Crea fattura(e) pop-up, ci sono 3 opzioni tra cui poter scegliere nel campo Crea fattura:

  * Fattura normale

  * Anticipo (percentuale)

  * Anticipo (importo fisso)




Nota

If Regular Invoice is selected, the other fields disappear, as they only pertain to down payment configurations.

## Richiesta acconto iniziale¶

On the Create invoices pop-up form, the down payment options are:

  * Anticipo (percentuale)

  * Anticipo (importo fisso)




Once the desired down payment option is selected in the Create Invoice field on the pop-up form, designate the desired amount, either as a percentage or a fixed amount, in the Down Payment Amount field.

Then, select the appropriate income account for the down payment (only the first time a down payment is created) in the Income Account field.

Once all fields are filled in with the desired information, click the Create Draft Invoice button. Upon clicking this button, Odoo reveals the Customer Invoice Draft.

Nella scheda Righe fattura della Bozza fattura cliente, l’acconto che è stato appena configurato nel modulo pop-up Crea fatture appare come Prodotto.

Nota

When the Down payment product in the Invoice Lines tab is clicked, Odoo reveals the product form for the down payment.

By default, the Product Type of down payment products generated for invoices are set as Service, with the Invoicing Policy set to Prepaid/Fixed Price.

This product can be edited/modified at any time.

Avvertimento

If Based on Delivered Quantity (Manual) is chosen as the Invoicing Policy, an invoice will **not** be able to be created.

## Esempio: richiesta anticipo 50%¶

Nota

L’esempio seguente prevede un anticipo del 50% su un prodotto (Armadio con ante) con Quantità ordinate come Politica di fatturazione.

Vedi anche

[Fatture basate su quantità ordinate o consegnate](invoicing_policy.html)

Per prima cosa, accedi all’app Vendite ‣ Nuovo e aggiungi un Cliente al preventivo.

Successivamente, fai clic su Aggiungi un prodotto nella scheda Righe ordine e seleziona il prodotto Armadio con ante.

Quando l’ordine viene confermato (tramite il pulsante Conferma), il preventivo si trasforma in un ordine di vendita. A questo punto, è possibile creare e visualizzare la fattura facendo clic su Crea fattura.

In seguito, nella finestra Crea fatture che appare, seleziona Anticipo (percentuale) e scrivi `50` nel campo Importo acconto.

Nota

The Income Account field is _not_ a required field, and it does _not_ appear if it has already been preconfigured in previous down payment requests.

Per maggiori informazioni, consulta la documentazione sulla Modifica del conto di ricavo per gli acconti.

Infine, fai clic su Crea bozza fattura per creare e visualizzare la bozza della fattura.

Facendo clic su Crea bozza fattura, apparirà la bozza della fattura che include l’acconto come Prodotto nella scheda Righe fatture.

Da qui, la fattura può essere confermata e registrata facendo clic su Conferma. La conferma della fattura cambia lo stato da Bozza a Confermata. Inoltre, rivela una nuova serie di pulsanti nella parte superiore della pagina.

Usando i pulsanti è possibile registrare il pagamento facendo clic su Registra pagamento.

In questo modo si apre il modulo pop-up Registra pagamento, che viene popolato automaticamente con le informazioni necessarie. Conferma la correttezza delle informazioni fornite e apporta le modifiche. Una volta terminato, fai clic sul pulsante Crea pagamento.

Dopo aver fatto clic su Crea pagamento, Odoo mostra la fattura del cliente con il banner verde In pagamento nell’angolo superiore destro.

Ora, quando il cliente vuole pagare l’importo rimanente dell’ordine, è necessario creare un’altra fattura. A tal fine, è necessario tornare all’ordine di vendita, seguendo i link del percorso.

Tornando all’ordine di vendita, nella scheda Righe ordine apparirà una nuova sezione dal titolo Acconti, insieme all’acconto appena fatturato e registrato.

In seguito, fai clic sul pulsante Crea fattura.

Nella finestra pop-up Crea fatture che appare, ci sono due nuovi campi: Già fatturato e Importo da fatturare.

Se l’importo rimanente è pronto per essere pagato, seleziona l’opzione Fattura normale. Odoo creerà una fattura per l’importo esatto necessario a completare il pagamento totale, come indicato nel campo Importo da fatturare.

Una volta completata l’operazione, fai clic su Crea bozza fattura.

In questo modo, viene visualizzata un’altra pagina Bozza fattura cliente, che elenca _tutte_ le fatture per quello specifico ordine di vendita nella scheda Righe fattura. Ogni voce di fattura mostra tutte le informazioni necessarie relative a ciascuna fattura.

Per completare il flusso, fai clic su Conferma, e lo stato della fattura passa da Bozza a Confermata. Successivamente, fai clic su Registra pagamento.

Ancora una volta, apparirà la finestra Registra pagamento, con tutti i campi autopopolati con le informazioni necessarie, compreso l’importo rimanente da pagare per l’ordine.

Dopo aver confermato queste informazioni, fai clic su Crea pagamento. In questo modo viene visualizzata la Fattura cliente finale con il banner verde In pagamento nell’angolo superiore destro. Inoltre, entrambi gli acconti sono presenti nella scheda Righe fattura.

A questo punto, il flusso è stato completato.

Nota

Questo flusso è possibile anche con l’opzione Importo fisso.

Importante

Se si utilizza un acconto con un prodotto che ha una politica di fatturazione di tipo Quantità consegnate e il costo del prodotto _supera_ l’acconto del 50% (come nella maggior parte dei casi), viene creata una fattura normale.

Tuttavia, per i prodotti che costano _meno_ dell’acconto del 50%, gli acconti non potranno essere dedotti al momento della fatturazione al cliente.

Questo perché i prodotti dovrebbero essere consegnati _prima_ di creare la fattura finale, dato che Odoo non consente totali negativi per le fatture.

Se non è stato consegnato nulla, viene creata una Nota di credito, che annulla la bozza di fattura creata dopo il pagamento dell’acconto.

Per utilizzare l’opzione Nota di credito, è necessario installare l’applicazione _Magazzino_ , per confermare la consegna. Altrimenti, la quantità consegnata può essere inserita manualmente direttamente nell’ordine di vendita.

## Esempio: acconto 100% richiesto¶

Il processo di richiesta di un acconto pari al 100% è simile al processo di configurazione di un ref:`acconto del 50% <sales/invoicing/50-percent-down-payments>` ma con meno step.

Nota

Un acconto del 100% non equivale a un pagamento completo dell’ordine di vendita.

Un ordine di vendita pagato tramite il normale processo di fatturazione non consentirà di generare ulteriori fatture e **non** verrà mostrato il pulsante _Crea fattura_ sull’ordine di vendita.

Seguendo questo esempio, il pulsante _Crea fattura_ _verrà_ visualizzato sull’ordine di vendita. Questo perché Odoo si aspetta che venga creata un’altra fattura dopo l’acconto per completare il pagamento dell’ordine di vendita.

In questo esempio, viene utilizzato il prodotto _Installazione pannello solare_.

Per configurare un acconto del 100%, inizia accedendo al modulo Vendite ‣ Nuovo e aggiungi un Cliente al preventivo.

Successivamente, fai clic su Aggiungi un prodotto nella scheda Righe ordine e seleziona il prodotto `Installazione pannello solare`.

Dopo aver fatto clic sul pulsante Conferma, il preventivo si trasforma in ordine di vendita. A questo punto, è possibile creare una fattura facendo clic su Crea fattura nell’angolo in alto a sinistra.

On the Create invoices pop-up window that appears, select Down payment (percentage), and type `100` in the Down Payment Amount field. Then, if desired, select an Income Account.

Nota

The Income Account and Customer Taxes fields are _not_ required fields, and they will _not_ appear if they’ve already been preconfigured in previous down payment requests.

Per maggiori informazioni, consulta la documentazione sulla Modifica del conto di ricavo per gli acconti.

Next, click Create Draft Invoice to create an invoice draft. This will also bring the draft invoice into view, which includes the Down payment as a Product in the Invoice Lines tab. The taxes on the down payment invoices are broken down in proportion of the sales order lines taxes.

La fattura ora può essere confermata e registrata facendo clic su Conferma. La conferma della fattura cambia lo stato da Bozza a Confermata. Inoltre, rivela una nuova serie di pulsanti nella parte superiore della pagina.

Il pagamento può essere registrato facendo clic sul pulsante Registra pagamento.

In questo modo si apre il modulo pop-up Registra pagamento, che viene popolato automaticamente con le informazioni necessarie. Conferma la correttezza delle informazioni fornite e apporta le modifiche. Una volta terminato, fai clic sul pulsante Crea pagamento.

Dopo aver fatto clic su Crea pagamento, Odoo mostra la fattura del cliente con il banner verde In pagamento nell’angolo superiore destro.

Il processo ora è completo e l’acconto del 100% è stato applicato con successo.

## Modifica conto di ricavo per acconti¶

Per modificare o sistemare il conto di ricavo collegato alla pagina del prodotto Acconto, è **necessario** installare l’applicazione _Contabilità_.

Accedi alla pagina Prodotti (app Vendite ‣ Prodotti ‣ Prodotti), cerca il prodotto `Anticipo` nella barra relativa e selezionalo per visualizzare la pagina con tutti i dettagli.

Dopo aver installato l’app _Contabilità_ , la scheda Contabilità diventa disponibile nella pagina prodotto.

Nella scheda Contabilità, è possibile modificare il conto di ricavo nel campo Conto di ricavo nella sezione Crediti.

Vedi anche

[Fatture basate su quantità ordinate o consegnate](invoicing_policy.html)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales/sales/invoicing/down_payment.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](proforma.html "Fatture proforma") |
  * [precedente](invoicing_policy.html "Fatture basate su quantità ordinate o consegnate") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Vendite](../../../sales.html) »
  * [Vendite](../../sales.html) »
  * [Invoicing Method](../invoicing.html) »
  * Acconti


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