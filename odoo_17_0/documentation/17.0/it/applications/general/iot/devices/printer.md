# Collegare una stampante — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](scale.html "Collegare una bilancia") |
  * [precedente](footswitch.html "Collegare un sensore a pedale") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Impostazioni generali](../../../general.html) »
  * [Internet delle cose (IoT)](../../iot.html) »
  * [Dispositivi](../devices.html) »
  * Collegare una stampante



# Collegare una stampante¶

L’installazione della stampante può essere eseguita in pochi semplici passaggi. La stampante può essere utilizzata per stampare ricevute, etichette, ordini o anche resoconti dalle diverse applicazioni di Odoo. Inoltre, le azioni della stampante possono essere assegnate come _azione su un trigger_ durante il processo di produzione, o aggiunte a un punto di controllo qualità o a un controllo qualità.

Avvertimento

Il **solo** metodo per collegare una stampante direttamente a un database Odoo è attraverso l’utilizzo di un sistema IoT. Senza uno di questi, la stampa può avvenire ma verrà gestita dalla stampante stessa che non è il processo consigliato.

## Connessione¶

I sistemi IoT supportano stampanti collegate via USB, connessione di rete o Bluetooth. Le [stampanti supportate](https://www.odoo.com/page/iot-hardware) vengono individuate automaticamente e appaiono nell’elenco Dispositivi dell’app _IoT_.

Nota

Le stampanti possono impiegare fino a due minuti per apparire nell’elenco di Dispositivi dell’app IoT.

## Collegare una stampante¶

### Collegare ordini di lavoro a una stampante¶

Gli ordini di lavoro possono essere collegati alle stampanti, tramite un punto di controllo qualità, per stampare le etichette dei prodotti fabbricati.

Nell’app [Qualità](../../../inventory_and_mrp/quality.html), è possibile impostare un dispositivo su un punto di controllo qualità. Per farlo, apri l’app Qualità ‣ Controllo qualità ‣ Punti controllo e apri il punto di controllo desiderato.

Importante

Per far sì che il campo Tipo permetta di selezionare l’opzione Stampa etichetta, è necessario collegare un’operazione di produzione e di ordine di lavoro al punto controllo qualità.

Da qui, modifica il punto di controllo selezionando il campo Tipo e fai clic su Stampa etichetta dal menu a discesa. Apparirà un campo chiamato Dispositivo dove potrai selezionare il dispositivo desiderato.

La stampante può ora essere utilizzata con il punto di controllo qualità selezionato. Quando il punto di controllo qualità viene raggiunto durante il processo di produzione, il database presenta l’opzione di stampa per le etichette per un prodotto specifico.

Suggerimento

È possibile accedere ai punti di controllo qualità anche dall’app IoT ‣ Dispositivi e poi seleziona il dispositivo. Apri la scheda Punti controllo qualità per aggiungerli al dispositivo.

Nota

Su un [modulo controllo qualità](../../../inventory_and_mrp/quality/quality_management/quality_checks.html), è possibile impostare anche il Tipo di controllo per la Stampa etichetta.

Vedi anche

  * [Quality control points](../../../inventory_and_mrp/quality/quality_management/quality_control_points.html)

  * [Quality alerts](../../../inventory_and_mrp/quality/quality_management/quality_alerts.html)




### Collegare resoconti a una stampante¶

È possibile collegare vari tipi di resoconti a una stampante specifica. Per farlo:

  1. vai su IoT ‣ Dispositivi e seleziona la stampante desiderata;

  2. accedi alla scheda Resoconti stampante e fai clic su Aggiungi riga;

  3. nella finestra pop-up che appare, seleziona i tipi di resoconti che vuoi collegare alla stampante e fai clic su Seleziona;




Suggerimento

I resoconti possono essere configurati [attivando la modalità sviluppatore](../../developer_mode.html#developer-mode) e andando su Impostazioni ‣ Funzioni tecniche ‣ Resoconti. Seleziona il resoconto desiderato dall’elenco e configura un Dispositivo IoT.

La prima volta che selezioni un resoconto collegato per la stampa, apparirà una finestra pop-up dal titolo Seleziona stampanti. Spunta la casella accanto alla stampante corretta per il resoconto e poi clicca su Stampa.

#### Cancella la cache della stampante del dispositivo¶

Dopo aver collegato una stampante per stampare un resoconto, l’impostazione viene salvata nella cache del browser. Ciò significa che un utente può avere diversi dispositivi salvati nella cache per diversi resoconti, in base al dispositivo che utilizza per accedere a Odoo. Ciò significa anche che utenti diversi possono far stampare automaticamente un resoconto da stampanti diverse, in base alle preferenze.

Per scollegare un resoconto da una stampante, apri l’app IoT ‣ Configurazione Deseleziona dispositivi ‣ Ripristina stampanti collegate. Verrà generato un elenco di resoconti collegati a una stampante nel dispositivo attuale. Fai clic sul pulsante Scollega accanto a ogni resoconto per eliminare il collegamento.

Importante

Questo passaggio impedisce **solo** che il resoconto venga stampato automaticamente dalla stampante elencata dal browser corrente. Il resoconto è ancora collegato al dispositivo, sotto la scheda Resoconti stampante.

Vedi anche

[Stampare ordini dal Punto vendita](../../../sales/point_of_sale/restaurant/kitchen_printing.html)

## Potenziali problemi¶

### La stampante non viene individuata¶

Se una stampante non appare nell’elenco dei dispositivi vai sulla pagina principale della [box IoT](../iot_box.html#iot-iot-box-homepage) oppire del servizio [Windows virtual IoT](../windows_iot.html#iot-windows-iot-homepage), fai clic su Mostra nella sezione Dispositivi e assicurati che la stampante appaia nell’elenco.

Se la stampante non appare nella pagina principale del sistema IoT, fai clic su Server stampante, poi su Amministrazione e Aggiungi stampante. Se la stampante non è nell’elenco, potrebbe non essere connessa in modo corretto.

### La stampante emette un testo casuale¶

Per la maggior parte delle stampanti, il driver corretto dovrebbe essere rilevato e selezionato automaticamente. Tuttavia, in alcuni casi, il meccanismo di rilevamento automatico potrebbe non essere sufficiente e, se non viene trovato alcun driver, la stampante potrebbe stampare caratteri casuali.

La soluzione consiste nel selezionare manualmente il driver corrispondente. Nella pagina principale del sistema IoT, fai clic su Server stampante, vai su Stampanti e seleziona la stampante nell’elenco. Nel menu a tendina Amministrazione, fai clic su Modifica stampante. Segui gli step e seleziona il _make_ e _model_.

Nota

Le stampanti di ricevute Epson e le stampanti di etichette Zebra non hanno bisogno di un driver per funzionare. Assicurati che non sia selezionato alcun driver per queste stampanti.

### La stampante viene individuata ma non riconosciuta correttamente¶

Se né Odoo né il sistema IoT riconoscono correttamente la stampante, vai su IoT ‣ Dispositivi, fai clic sulla scheda del dispositivo per accedere al modulo e configura il campo Sottotipo selezionando l’opzione appropriata: Stampante ricevuta, Stampante etichetta o Stampante ufficio.

#### Casi speciali configurazione Epson¶

La maggior parte delle stampanti Epson supportano la stampa di ricevute nel Punto vendita Odoo utilizzando il comando `GS v 0`. Tuttavia, le seguenti stampanti Epson non supportano il comando:

  * TM-U220

  * TM-U230

  * TM-P60

  * TMP-P60II




Per aggirare il problema, è possibile configurare la stampante per l’utilizzo del comando `ESC *`.

Per prima cosa, consulta il sito web Epson per la compatibilità dei comandi [GS v 0](https://download4.epson.biz/sec_pubs/pos/reference_en/escpos/gs_lv_0.html) ed [ESC *](https://download4.epson.biz/sec_pubs/pos/reference_en/escpos/esc_asterisk.html).

Se la stampante non è compatiile con `GS v 0` ma supporta `ESC *`, configura il sistema IoT per utilizzare il comando come segue:

  1. Accedi alla pagina principale della [box IoT](../iot_box.html#iot-iot-box-homepage) oppure della [Windows virtual IoT](../windows_iot.html#iot-windows-iot-homepage).

  2. fai clic sul pulsante Server stampante e poi fai clic su Amministrazione sulla pagina CUPS.

  3. fai clic su Aggiungi stampante nella sezione Stampanti, seleziona la stampante e fai clic su Continua.

Suggerimento

Se il nome della stampante non è ancora certom segui questi step;

     1. prendi nota delle stampanti elencate nella pagina CUPS;

     2. Spegni la stampante e ricarica la pagina:

     3. confronta con il primo elenco per vedere quale stampante è scomparsa;

     4. Riaccendi la stampante e ricarica la pagina;

     5. Controlla di nuovo l’elenco per vedere se appare la stampante;

     6. la stampante scomparsa che riappare nell’elenco delle stampanti è il nome della stampante in questione. Può avere il nome Sconosciuta nella sezione Stampanti locali.

  4. Nella pagina Aggiungi stampante, specifica il Nome della stampante utilizzando la seguente convenzione: `<printer_name>__IMC_<param_1>_<param_2>_..._<param_n>__`, dove:

     * `printer_name` è il nome della stampante. Può contenere qualsiasi carattere eccetto `_`, `/`, `#` o ` ` (carattere spazio).

     * `IMC`: ovvero _Image Mode Column_ nome semplificato per `ESC *`).

     * `param_1`: parametro specifico:

       * `SCALE<X>`: scala dell’immagine (con lo stesso rapporto di aspetto). `X` dovrebbe essere un intero che descrive la percentuale della scala da utilizzare. Ad esempio, `100` è la dimensione originale, `50` corrisponde alla metà e `200` al doppio.

       * `LDV`: _Low Density Vertical_ (verrà impostata su _High Density Vertical_ se non specificato).

       * `LDH`: _Low Density Horizontal_ (verrà impostata su _High Density Horizontal_ se non specificato).

Nota

       * Potrebbe essere necessario configurare i parametri relativi alla _densità_ in un modo particolare in base al modello di stampante.

       * Consulta la [documentazione `ESC * di Epson](https://download4.epson.biz/sec_pubs/pos/reference_en/escpos/esc_asterisk.html) per capire se la stampante richiede la configurazione dei parametri.

> Example
> 
> Di seguito alcuni esempi di nomi formattati in modo giusto e sbagliato.
> 
> Formattazione nome giusta:
> 
>      * `EPSONTMm30II__IMC__`
> 
>      * `EPSON_TM_U220__IMC_LDV_LDH_SCALE80__`
> 
> Formattazione nome errata (non impedirà la stampa ma il risultato potrebbe non essere quello desiderato):
> 
>      * `EPSON TMm 30II`: il nome non può contenere spazi
> 
>      * `EPSONTMm30II`: il nome è corretto ma non utilizzerà `ESC *`
> 
>      * `EPSONTMm30II__IMC`: il nome manca della fine `__`
> 
>      * `EPSONTMm30II__IMC_XDV__`: il parametro `XDV` non corrisponde a nessuno dei parametri esistenti
> 
>      * `EPSONTMm30II__IMC_SCALE__`: il parametro `SCALE` manca il valore della scala

  5. Una volta che il nome della stampante è stato definito utilizzando la convenzione di denominazione appropriata, fai clic su Continua.

  6. in seguito, configura il valore Make impostandolo su Raw e per il valore Model scegli Raw Queue (en);

  7. fai clic su Aggiungi stampante. Se tutto è stato fatto correttamente, la pagina dovrebbe reindirizzare alla pagina _Banner_ ;

  8. aspetta alcuni minuti per far sì che il sistema individui la stampante e si sincronizzi con il server Odoo;

  9. [accedi alle impostazioni del POS](../../../sales/point_of_sale/configuration.html#configuration-settings) e seleziona il tuo POS oppure fai clic sul pulsante a forma di ellissi verticale (⋮) di una scheda e clicca su Modifica. Scorri in basso fino alla sezione Dispositivi collegati, attiva la Box IoT e seleziona la stampante nel campo Stampante ricevuta. Fai clic su Salva.




Nota

Se la stampante è stata configurata in modo errato (ad esempio, continua a stampare testo a caso o la ricevuta stampata è troppo grande o troppo piccola), non è possibile modificarla tramite il nome della stampante in CUPS. Occorre invece configurare una nuova stampante da zero con i parametri modificati, seguendo i passi precedenti.

Example

Di seguito è riportato un esempio del processo di risoluzione dei problemi per un modello di stampante TM-U220B utilizzando il comando `ESC *`. La ricevuta illustrata di seguito è un esempio di ricevuta che viene stampata correttamente grazie alla formattazione corretta (in teoria):

La stampa immediata di questa ricevuta senza una formattazione adeguata non funzionerà, poiché il modello di stampante TM-U220B non supporta il comando `GS v 0`. Verranno stampati caratteri casuali:

Per configurare in modo appropriato la formattazione per il modello stampante Epson TM-U220B segui questi step:

  1. Dopo aver consultato il sito web Epson per la compatibilità con i comandi [GS v 0](https://download4.epson.biz/sec_pubs/pos/reference_en/escpos/gs_lv_0.html) ed [ESC *](https://download4.epson.biz/sec_pubs/pos/reference_en/escpos/esc_asterisk.html), la stampante TM-U220B non è compatibile con il comando `GS v 0` ma supporta `ESC *`.

  2. Quando aggiungi la stampante, il sistema CUPS mostra l’elenco di stampanti disponibili:

In questo caso, la stampante è collegata tramite USB quindi non sarà parte delle Stampanti di rete scoperte. Al contrario, farà parte della selezione Sconosciuta nella sezione Stampanti locali. Scollegando il cavo USB della stampante dal sistema IoT e ricaricando la pagina, la stampante Sconosciuta scomparirà. Ricollegandola, la stampante riappare, quindi si può dire che si tratta della stampante in questione.

  3. Per la convenzione di denominazione, dato che la stampante deve stampare utilizzando il comando `ESC *`, è imperativo aggiungere `__IMC`.

Per questo particolare modello, TM-U220, `m` deve essere pari a 0 o 1. Facendo riferimento alla tabella Descrizione sul [sito web Epson’s ESC *](https://download4.epson.biz/sec_pubs/pos/reference_en/escpos/esc_asterisk.html), i valori `m` potrebbero essere 0, 1, 32 o 33. Quindi, nel caso della stampante, il valore `m` ***non*** può essere 32 o 33 (altrimenti verranno stampati caratteri casuali).

La tabella include i valori numerici 32 e 33, entrambi appaiono se il Numero di bit per dati verticali è impostato su 24 ovvero è un _High Vertical Density_. Nel caso della configurazione della Epson TM-U220, il valore _Low Vertical Density_ dovrà essere forzato perché questo modello di stampante non supporta il _High Vertical Density_ per il comando `ESC *`.

Per aggiungere un _Low Vertical Density_ , aggiungi il parametro `LDV` alla convenzione di denominazione.

  4. Fai clic su Continua per procedere. In seguito, configura il valore Make impostandolo su Raw e per il valore Model scegli Raw Queue (en).

Tuttavia, quando provi a stampare con la convenzione di denominazione `EpsonTMU220B__IMC_LDV__`, la ricevuta viene stampata ma è troppo grande e fuori dai margini. Per risolvere il problema, aggiungi una nuova stampante (e convenzione di denominazione) con il parametro `SCALE<X>` per adattarlo alla dimensione della ricevuta.

Ecco alcuni esempi:

Convenzione di denominazione stampante | `EpsonTMU220B__IMC_LDV__` | `EpsonTMU220B__IMC_LDV_SCALE75__` | `EpsonTMU220B__IMC_LDV_LDH__` | `EpsonTMU220B__IMC_LDV_LDH_SCALE35__`  
---|---|---|---|---  
|  |  |  |   



### Problema di stampa DYMO LabelWriter¶

La stampante DYMO LabelWriter presenta un problema noto nella stampa con i sistemi IoT. Il server CUPS OpenPrinting installa la stampante utilizzando i driver Local RAW Printer. Per poter stampare qualsiasi cosa, è necessario impostare la corretta Marca e modello, in modo che venga fatto riferimento al driver corretto quando si utilizza il dispositivo.

Inoltre, è necessario aggiungere una nuova stampante per ridurre il ritardo di stampa che si verifica dopo l’aggiornamento del driver.

Importante

La stampante DYMO LabelWriter 450 DUO è la stampante DYMO consigliata per l’utilizzo con i sistemi Odoo e IoT. Questo dispositivo combina due stampanti: una stampante di etichette e una stampante a nastro. Al momento della configurazione dei seguenti processi, è essenziale selezionare il modello corretto (DYMO LabelWriter 450 DUO Label (en) o DYMO LabelWriter 450 DUO Tape (en)). Per coerenza, le procedure descritte illustrano le fasi di configurazione per il modello DYMO LabelWriter 450 DUO Label (en). La scelta del modello dipende dalle necessità.

#### DYMO LabelWriter non stampa¶

Se la DYMO LabelWriter non stampa, installa un nuovo driver:

  1. accedi alla pagina principale del sistema IoT e fai clic su Server stampante per aprire la console CUPS OpenPrinting.

  2. fai clic su Stampanti nel menu in alto e poi fai clic sulla stampante nell’elenco

  3. seleziona Manutenzione nel primo menu a tendina.

  4. seleziona Modifica stampante nel secondo menu a tendina-

  5. Seleziona la connessione di rete/stampante specifica su cui deve essere effettuata la modifica e fai clic su Continua.

  6. nella pagina successiva, fai clic su Continua e poi seleziona DYMO dall’elenco a discesa Make

  7. fai clic su Continua e imposta il Model su DYMO LabelWriter 450 DUO Label (en) (o qualsiasi modello di stampante DYMO in utilizzo)

  8. fai clic su Modifica stampante per impostare nuovi driver, apparirà una pagina di conferma

  9. fai clic su Stampanti nel menu in alto e appariranno tutte le stampanti installate sul server OpenPrinting CUPS compresa la DYMO LabelWriter 450 DUO Label aggiornata di recente (o qualsiasi modello di stampante DYMO utilizzata).

  10. fai clic sulla stampante appena aggiornata, poi fai clic sul menu a discesa Manutenzione e seleziona Stampa pagina di prova per stampare un’etichetta di prova. L’etichetta di prova viene stampata dopo pochi secondi se l’aggiornamento del driver è avvenuto con successo




Per ridurre il ritardo, aggiungi una nuova stampante utilizzando la procedura descritta di seguito.

#### Ritardo stampa DYMO LabelWriter¶

Suggerimento

Se la stampante DYMO LabelWriter 450 DUO non stampa oppure non viene riconosciuta (ovvero ha un tipo di driver RAW), aggiorna i driver sul dispositivo.

Per risolvere il problema legato al ritardo dopo aver modificato il driver, installa di nuovo la stampante:

  1. accedi alla pagina principale del sistema IoT e fai clic su Server stampante per aprire la console CUPS OpenPrinting.

  2. fai clic su Amministrazione nel menu in alto, poi fai clic su Aggiungi stampante.

  3. nella pagina successiva, nella sezione Stampanti locali, seleziona la stampante preinstallata DYMO LabelWriter 450 DUO Label (DYMO LabelWriter 450 DUO Label) (o qualsiasi altro modello di stampante DYMO in uso). Fai clic su Continua

  4. nella schermata successiva, aggiorna il Nome in qualcosa di riconoscibile, dato che la stampante originale sarà ancora nell’elenco. In seguito, fai clic su Continua

  5. imposta il Modello selezionando DYMO LabelWriter 450 DUO Label (en) (o qualsiasi modello di stampante DYMO utilizzato) e infine, fai clic su Aggiungi stampante per completare l’installazione

  6. fai clic su Stampanti nel menu in alto e fai clic sulla stampante appena installata DYMO LabelWriter 450 DUO Label (o qualsiasi modello di stampante DYMO in uso) nell’elenco

  7. fai clic sull’elenco a discesa Manutenzione e seleziona Stampa pagina di prova per stampare un’etichetta di prova. L’etichetta di prova dovrebbe essere stampata immediatamente oppure dopo un paio di secondi.




### La stampante Zebra non stampa nulla¶

Le stampanti Zebra sono abbastanza sensibili al formato del codice del linguaggio di programmazione di Zebra (ZPL) che viene stampato. Se non esce nulla dalla stampante o vengono stampate etichette bianche, prova a cambiare il formato del resoconto inviato alla stampante. Per farlo, attiva la [modalità sviluppatore](../../developer_mode.html#developer-mode), vai su Impostazioni ‣ Funzioni tecniche ‣ Interfaccia utente ‣ Viste e cerca il modello corrispondente.

Vedi anche

Istruzioni di Zebra sulla stampa di file ZPL <<https://supportcommunity.zebra.com/s/article/Print-a-zpl-file-using-the-Generic-Text-Printer>?language=it`_.

## Problemi lettore codici a barre¶

### I caratteri letti dal lettore di codici a barre non corrispondono al codice a barre¶

Per impostazione predefinita, la maggior parte dei lettori di codici a barre sono configurati in formato US QWERTY. Se il lettore di codici a barre usa un layout diverso, apri l’app IoT ‣ Dispositivi e fai clic sulla scheda del dispositivo per i codici a barre. In seguito, seleziona la lingua corretta nel campo Layout tastiera.

Nota

Il Layout tastiera è specifico per ogni lingua e le opzioni disponibili variano a seconda del dispositivo e della lingua del database (ad es.: English (UK), English (US), ecc.).

### Non accade nulla al momento della scansione di un codice a barre¶

Assicurati di selezionare il dispositivo corretto nelle [impostazioni del Punto vendita](../../../sales/point_of_sale/configuration/pos_iot.html) (se possibile) e di aver configurato il codice a barre per inviare il carattere `ENTER` (keycode 28) alla fine di ogni codice a barre.

### Il lettore di codici a barre viene rilevato come tastiera¶

Importante

Alcuni lettori di codici a barre vengono identificati come tastiere USB invece che lettori e non vengono riconosciuti dai sistemi IoT.

Per modificare il tipo di dispositivo manualmente, vai su IoT ‣ Dispositivi e fai clic sulla scheda del dispositivo codici a barre. In seguito, attiva È scanner.

### Il lettore di codici a barre elabora i caratteri del codice singolarmente¶

Quando utilizzi la versione mobile di Odoo da un dispositivo mobile o tablet abbinato al lettore di codici a barre tramite un sistema IoT, il lettore potrebbe interpretare ogni carattere in un codice a barre come una scansione diversa. Per risolvere il problema, vai su

Nota

Il Layout tastiera è specifico per ogni lingua e le opzioni disponibili variano a seconda del dispositivo e della lingua del database (ad es.: English (UK), English (US), ecc.).

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/general/iot/devices/printer.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](scale.html "Collegare una bilancia") |
  * [precedente](footswitch.html "Collegare un sensore a pedale") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Documentazione Utente](../../../../applications.html) »
  * [Impostazioni generali](../../../general.html) »
  * [Internet delle cose (IoT)](../../iot.html) »
  * [Dispositivi](../devices.html) »
  * Collegare una stampante


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
  *[Cc]: Copia carbone
  *[LAN]: Local Area Network
  *[SSH]: secure shell protocol
  *[HTTPS]: Hypertext Transfer Protocol Secure
  *[UUID]: Universal Unique Identifier
  *[POS]: Punto vendita