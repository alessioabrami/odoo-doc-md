# Italia — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](jordan.html "Giordania") |
  * [precedente](indonesia.html "Indonesia") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Italia



# Italia¶

## Configurazione¶

[Installa](../../general/apps_modules.html#general-install) i seguenti moduli per ottenere tutte le funzionalità della localizzazione italiana:

Nome | Nome tecnico | Descrizione  
---|---|---  
Italia - Contabilità | `l10n_it` | [Pacchetto localizzazione fiscale predefinito](../fiscal_localizations.html#fiscal-localizations-packages)  
Italia - Fatturazione Elettronica | `l10n_it_edi` | Implementazione fatturazione elettronica  
Italia-Fatturazione elettronica (ritenuta) | `l10n_it_edi_withholding` | Ritenuta d’acconto fatturazione elettronica  
Italia - Rendiconti Contabili | `l10n_it_reports` | Rendiconti specifici del Paese  
Italia - DDT stock | `l10n_it_stock_ddt` | Documento di Trasporto (DDT)  
  
Vedi anche

[Documentation on e-invoicing’s legality and compliance in Italy](../accounting/customer_invoices/electronic_invoicing/italy.html)

### Informazioni aziendali¶

La configurazione delle informazioni aziendali consente di impostare il database contabile in maniera appropriata. Per aggiungere informazioni, vai su Impostazioni ‣ Impostazioni generali e fai clic su Aggiorna informazioni nella sezione Aziende. Da qui, riempi i seguenti campi:

  * Indirizzo: l’indirizzo dell’azienda;

  * Partita IVA: partita IVA dell’azienda;

  * Codice Fiscale: codice fiscale dell’azienda;

  * Regime fiscale: regime fiscale dell’azienda.




### Configurazione delle imposte¶

Molte delle funzionalità della fatturazione elettronica sono state implementate utilizzando il regime fiscale di Odoo. In quanto tali, le imposte devono essere configurate in maniera appropriata per generare fatture nel modo corretto e gestire altri utilizzi per la fatturazione.

La localizzazione **italiana** contiene **esempi** predefiniti di imposte per vari scopi.

#### Esenzione fiscale¶

Le autorità italiane richiedono l’utilizzo di imposte sulle vendite pari allo **zero percento** (0%) per tenere traccia del Tipo di esenzione fiscale (Natura) e del Riferimento giuridico che giustifica l’esenzione attuata sulla riga di una fattura.

Example

In Europa l’imposta sulle esportazioni può essere utilizzata come riferimento (`0% EU`, etichetta fattura `00eu`). Può essere trovata seguendo il percorso Contabilità ‣ Configurazione ‣ Imposte. Le esportazioni sono esenti dall’IVA e quindi richiedono l’inserimento del tipo di Esenzione e del `Riferimento giuridico`.

Vedi anche

Esistono molti codici sia per il Tipo di esenzione fiscale (Natura) che per il Riferimento giuridico. Assicurati di aver consultato l’utlima versione disponibile per ottenere le informazioni più aggiornate:

  * [Documentazione autorità italiane](https://www.agenziaentrate.gov.it/portale/web/guest/aree-tematiche/fatturazione-elettronica)

  * [Guida ufficiale esenzione fiscale](https://www.agenziaentrate.gov.it/portale/documents/20143/451259/Guida_compilazione-FE-Esterometro-V_1.9_2024-03-05.pdf/67fe4c2d-1174-e8de-f1ee-cea77b7f5203)




Nota

Nel caso debba utilizzare un altro tipo di esenzione vai su Contabilità ‣ Configurazione ‣ Imposte, seleziona un’imposta simile e poi fai clic sull’icona a forma di ingranaggio e seleziona Duplica. Nella scheda relativa alle Opzioni avanzate aggiungi l”Esenzione ed il Riferimento giuridico. Per confermare, fai clic su Salva.

Suggerimento

**Rinomina** le imposte dal campo Nome secondo il tipo di Sgravio per differenziarle facilmente.

## Inversione contabile¶

Per **inversione contabile** si intende una regola relativa all’IVA che trasferisce la responsabilità del pagamento dell’IVA dal fornitore al cliente. I clienti pagano **autonomamente** l’IVA all”AdE. Esistono due tipi:

  * Inversione contabile interna (per vendite nazionali)

La responsabilità dell’IVA viene trasferita all’acquirente per alcune categorie di prodotti e servizi.

  * Inversione contabile esterna (per vendite all’interno dell’UE)

È necessario pagare l’IVA nel Paese di consegna o nel Paese nel quale viene fornito il servizio. Quando l’acquirente rappresenta allo stesso tempo un’azienda italiana, l’UE offre un meccanismo che consente al venditore di trasferire la propria responsabilità all’acquirente.




### Fatture¶

Le fatture del cliente per le quali è stata adottata l”**inversione contabile** non mostrano l’importo dell’IVA ma l”AdE richiede al venditore di specificare il motivo dell”Esenzione fiscale e il Riferimento giuridico che abilita il meccanismo dell’inversione contabile. Odoo fornisce un insieme di imposte speciali allo 0% che possono essere applicate ad ogni riga della fattura per le quali è stato adottato il meccanismo rapprensentando le configurazioni utilizzate più comunemente.

### Fatture fornitore¶

Le aziende italiane soggette all’inversione contabile devono inviare le informazioni contenute nella fattura all”AdE.

Nota

I file XML relativi all’IVA autodichiarati devono essere scaricati e inviati all”AdE per le fatture alle quali è stata applicata l’inversione contabile.

Al momento della creazione di una fattura fornitore, le imposte dell”**inversione contabile** sono disponibili per essere aggiunte nel campo Imposte. È possibile verificare quali imposte sono disponibili andando su Contabilità ‣ Configurazione ‣ Imposte. Noterai che le imposte 10% beni e 22% servizi sono state attivate. Quest’ultime vengono attivate automaticamente nell’elenco grazie alla configurazione automatica della posizione di bilancio italiana.

### Griglie imposte¶

La localizzazione italiana ha la sezione specifica [griglia imposta](../accounting/reporting/tax_returns.html#tax-returns-tax-grids) per le imposte relative all” **inversione contabile**. Le griglie sono individuabili grazie all’etichetta VJ ed è possibile trovarle andando su Contabilità ‣ Rendicontazione ‣ Resoconti di revisione: Resoconto fiscale.

## Fatturazione elettronica¶

L”SdI è il sistema di [fatturazione elettronica](../accounting/customer_invoices/electronic_invoicing.html) utilizzato in Italia che consente di inviare e ricevere fatture elettroniche. I documenti devono avere il formato :abbr:`EDI (Electronic Data Interchange) XML chiamato **FatturaPA** e devono essere convalidati formalmente dal sistema prima di essere consegnati.

Per essere in grado di ricevere fatture e notifiche, è necessario informare l”SdI circa l’invio e l’elaborazione dei file dell’utente da parte di Odoo. Per farlo, bisogna configurare il Codice Destinatario Odoo dal portale dell”AdE.

  1. Accedi al [portale delle autorità italiane](https://ivaservizi.agenziaentrate.gov.it/portale) ed effettua l’autenticazione.

  2. Vai alla sezione Fatture e Corrispettivi;

  3. Imposta l’utente come entità legale per il numero di partita IVA di cui vuoi configurare l’indirizzo elettroncio;

  4. Inserisci il Codice Destinatario `K95IV18` di Odoo nella sezione Servizi Disponibili ‣ Fatturazione Elettronica ‣ Registrazione dell’indirizzo telematico dove ricevere tutte le fatture elettroniche e conferma.




### Modalità EDI e autorizzazione¶

Dato che i file vengono trasmessi attraverso il server di Odoo, prima di essere inviati all” SdI o ricevuti dal tuo database, è necessario autorizzare Odoo a elaborare i file del database stesso. Per farlo, vai su Contabilità ‣ Configurazione ‣ Impostazioni ‣ Fatturazione elettronica documenti.

Tre sono le modalità disponibili:

  * Demo

Questa modalità simula un ambiente nel quale le fatture vengono inviate al governo. Le fatture devono essere scaricate _manualmente_ come file XML e caricate sul sito web dell”AdE.

  * Test (sperimentale)

In questa modalità le fatture vengono inviate ad un servizio non di produzione (test) messo a disposizione dall”AdE. Salvando le impostazioni, tutte le aziende presenti nel database vengono invitate ad utilizzare questa configurazione.

  * Ufficiale

Si tratta di una modalità di produzione che invia le tue fatture direttamente all”AdE.




Una volta selezionata una delle modalità, è necessario accettare i **termini e condizioni** spuntando la voce `Consenti a Odoo di elaborare le fatture` per poi fare clic su Salva. Ora puoi registrare tutte le operazioni nell’app Contabilità.

Avvertimento

La scelta della modalità Test (sperimentale) o Ufficiale è **irrevocabile**. Ad esempio, se selezioni la modalità Ufficiale, non sarà possibile selezionare le modalità Test (sperimentale) o Demo. Consigliamo di creare un **database dedicato** esclusivamente ai test.

Nota

In modalità Test (sperimentale), tutte le fatture inviate _devono_ avere un partner che utilizza uno dei seguenti Codice Destinatario fittizi forniti dall” AdE: `0803HR0` \- `N8MIMM9` \- `X9XX79Z`. Qualsiasi Codice Destinario vero di produzione, appartenente ai clienti, non verrà considerato valido dal servizio di test.

### Elabora¶

L’invio di fatture all”SdI per l’Italia è un processo digitale utilizzato per la trasmissione obbligatoria di documenti fiscali in formato XML tra le aziende e l”AdE per ridurre gli errori e verificare la correttezza delle operazioni.

Nota

È possibile verificare lo stato attuale di una fattura grazie al campo Stato SDI. Il file XML viene allegato alla fattura.

#### Creazione documenti XML¶

Odoo genera i file XML richiesti come allegati alle fatture nel formato `FatturaPA` richiesto dall”AdE. Una volta selezionate le fatture richieste, vai su Azioni e fai clic su Invia e stampa.

Quando si apre la finestra popup, vi sono una serie di azioni che possono essere eseguite. Ad esempio, Genera file XML genera gli allegati.

Il file XML così come il PDF possono essere trovati in allegato alla fattura.

#### Invio all’SDI¶

L’opzione Invia all’agenzia fiscale nella finestra Invia e stampa invia l’allegato al Server proxy che raccoglie tutte le richieste ed in seguito le invia tramite il canale WebServices all”SdI. Quando visualizzi la fattura, puoi controllare lo stato dell’invio grazie al pulsante Verifica invio.

#### Elaborazione da parte dell’SDI¶

L”SdI riceve il documento e verifica la presenza di eventuali errori. In questa fase, la fattura si trova nello stato di Elaborazione SdI, come mostrato sulla fattura. Inoltre, alla fattura viene assegnato un numero di Transazione FatturaPA mostrato nella scheda Fatturazione elettronica. I controlli potrebbero richiedere tempo, da pochi secondi fino ad un giorno, in base al quantitativo di fatture inviate in Italia.

#### Accettazione¶

Se il documento è valido, viene registrato e considerato valido fiscalmente dall”AdE che procederà con l’archiviazione nella Conservazione Sostitutiva se esplicitamente richiesto nel portale dell’Agenzia.

Avvertimento

Odoo non dispone dei requisiti per la [Conservazione Sostitutiva](https://www.agid.gov.it/index.php/it/piattaforme/conservazione). Esistono altri fornitori oltre all”AdE che forniscono spazio gratis e certificato per rispettare gli obblighi di legge.

Il Codice destinatario dell”SdI porva a inoltrare la fattura al cliente inviandola all’indirizzo fornito, che si tratti di un indirizzo e-mail `PEC` oppure un Codice destinatario dell”SdI per i canali WebServices dell’ERP. È possibile effettuare un massimo di 6 tentativi ogni 12 ore quindi, anche se non ha successo, il processo potrebbe impiegare fino a tre giorni. Lo stato della fattura diventa Accettata dall’SDI, Invio al partner.

#### Eventuale rifiuto¶

L”SdI potrebbe riscontrare incongruenze nella compilazione, eventualmente anche formali. In questo caso, la fattura assumerà lo stato di Rifiutata SDI. Le osservazioni dell”SdI vengono inserite nella parte alta della scheda della fattura. Per risovlere il problema è sufficiente eliminare gli allegati della fattura, modificare lo stato della fattura in Bozza e correggere gli errori. Una volta che la fattura è pronta può essere inviata di nuovo.

Nota

Per rigenerare l’XML, è necessario eliminare sia l’allegato in XML che il rendiconto PDF in modo che vengano rigenerati insieme. La procedura assicura che entrambi contengano gli stessi dati.

#### Invio completato¶

La fattura è stata consegnata al cliente. Tuttavia, puoi ancora inviare una copia in PDF al cliente, via e-mail o tramite posta. Il suo stato diventerà Accettata SDI, Consegnata al partner.

Se l”SdI non può contattare il tuo cliente significa che potrebbe non essere registrato sul portale dell”AdE. In questo caso, assicurati di inviare la fattura in PDF via e-mail o tramite posta. In seguito, la fattura si troverà nello stato di Accettata SDI, Consegna partner fallita.

### Integrazione imposte¶

Al momento della ricezione di una fattura fornitore, dall”SdI, da carta o da un file XML importato, l’agenzia fiscale potrebbe richiedere l’invio di alcune informazioni integrative relative alle imposte all”SdI. Questo succede quando una transazione con esenzione fiscale diventa tassabile per qualsiasi motivo.

Example

Di seguito una lista non esaustiva:

  * Italia/Inversione contabile

In quanto acquirente, devi pagare le imposte su ciò che compri e integrare le informazioni. Imposte Inversione contabile.

  * Italia/Pagamento frazionato

In quanto acquirente d’azienda PA, devi pagare le imposte e integrarne le informazioni. Assicurati di sostituire l”Imposta di vendita 0% sulla fattura fornitore ricevuta con le imposte corrette relative al Pagamento frazionato.

  * Uso personale

In qualità di imprenditore, se utilizzi per motivi personali un bene acquistato per l’azienda è necessario pagare le imposte originariamente detratte come costo aziendale.




Odoo potrebbe rilevare che la fattura fornitore può essere interpretata come un documento che richiede l’integrazione fiscale, come specificato nella sezione Italia/Tipi di documento.

Importante

Assicurati di sostituire l”Imposta di vendita 0% sulla fattura fornitore ricevuta con quelle che devi pagare all”AdE. In seguito, apparirà un pulsante nella parte alta del singolo modulo della fattura fornitore per inviarle.

Quando fai clic sul pulsante Invia integrazione tasse verrà generato un file XML del Tipo di documento appropriato, allegato alla fattura fornitore e inviato come per le fatture.

### Tipi di documento¶

L”SdI necessita che le aziende inviino le fatture dei clienti e altri documenti attraverso l”EDI.

I seguenti codici relativi ai Tipi di documento identificano tutti vari casi d’uso aziendali.

#### TD01 - Fatture¶

Il codice rappresenta lo scenario **nazionale** per tutte le fatture scambiate attraverso l”SdI. Ogni fattura che non corrisponde ad uno dei casi specifici viene categorizzata come fattura regolare, identificata dal Tipo di documento `TD01`.

#### TD02 - Acconto/Anticipo su fattura¶

Le fatture di **acconto** vengono importate/esportate con un codice diverso rispetto alle fatture regolari: `TDO2`. Al momento dell’importazione di una fattura, viene creata una fattura fornitore regolare.

Odoo esporta le transazioni come `TD02` se vengono rispettate le seguenti condizioni:

  1. è una fattura;

  2. tutte le righe della fattura sono legate alle righe di un ordine di vendita per l’acconto.




#### TD04 - Note di credito¶

It is the standard scenario for all **credit notes** issued to **domestic** clients, when we need to formally acknowledge that the seller is reducing or cancelling a previously issued invoice, for example, in case of overbilling, incorrect items, or overpayment. Just like invoices, they must be sent to the SdI, their Document Type `TD04`

#### TD07, TD08, TD09 - Fatturazione semplificata¶

Le fatture semplificate (`TD07`), le note di credito (`TD08`) e di debito (`TD09`) possono essere utilizzate per certificare le operazioni nazionali al di sotto di 400 EURO (IVA inclusa). Lo stato è lo stesso di una fattura regolare ma con meno requisiti relativi alle informazioni.

Per creare una fattura semplificata è necessario includere:

  1. Customer Invoice reference: **unique** numbering sequence with **no gaps** ;

  2. Data fattura: **data** di emissione della fattura;

  3. Informazioni dell’azienda: informazioni complete del **venditore** (numero di partita IVA/TIN, nome, indirizzo completo) in Impostazioni generali ‣ Aziende (sezione);

  4. IVA: il numero di partita IVA/TIN dell”**acquirente** ” (nel modulo corrispondente);

  5. Totale: l” **importo** totale (IVA inclusa) della fattura.




Nell’ambito dell” EDI, Odoo esporta le fatture semplificate se:

  1. Si tratta di un’operazione nazionale (ad es. il partner è italiano);

  2. vengono forniti i **campi richiesti** della tua azienda (Numero IVA o Codice Fiscale, Regime fiscale e l”**indirizzo** per intero);

  3. l’indirizzo del partner non è stato specificato completamente (ad es., non è presente la città o il codice postale);

  4. l’importo totale dell’IVA inclusa è **inferiore** a **400 EURO**.




Nota

La soglia di 400 EURO è stata definita dal [decreto del 10 maggio 2019 pubblicato nella Gazzetta Ufficiale](https://www.gazzettaufficiale.it/eli/id/2019/05/24/19A03271/sg). Ti consigliamo di verificare il valore ufficiale attuale.

#### TD16 - Inversione contabile interna¶

Le operazioni relative all’inversione contabile interna (vedi Italia/Esenzione fiscale e Italia/Inversione contabile) sono esportate come `TD16` se vengono rispettate le seguenti condizioni:

  * si tratta di una fattura fornitore;

  * presenta almeno **un’imposta** sulle righe della fattura che si riferiscono ad una di queste griglie: `VJ6`, `VJ7`, `VJ8`, `VJ12`, `VJ13`, `VJ14`, `VJ15`, `VJ16`, `VJ17`.




#### TD17 - Comprare servizi dall’estero¶

Quando vengono acquistati **servizi** da Paesi **UE** e **non-UE** , il _venditore_ straniero fattura un servizio con un prezzo **IVA esclusa** , in quanto non è tassabile in Italia. L’IVA viene pagata dall” _acquirente_ in Italia.

  * All’interno dell’UE: l” _acquirente_ integra la fattura ricevuta con le **informazioni sull’IVA** da dichiarare in Italia (ad es. **integrazione imposte fattura fornitore**);

  * Non-UE: l” _acquirente_ invia autonomamente la fattura (ad es. **autofatturazione**).




Odoo esporta un’operazione come `TD17` se vengono rispettate le seguenti condizioni:

  * si tratta di una fattura fornitore;

  * Almeno **una** delle imposte presenti nelle righe della fattura deve corrispondere alla griglia delle imposte VJ3;

  * Tutte le righe della fattura hanno Servizi come **prodotti** oppure un’imposta con i Servizi come **ambito impositivo**.




#### TD18 - Acquistare beni dall’UE¶

Le fatture emesse all’interno dell’UE segue un **formato standard** pertanto è richiesta solo l’integrazione delle fatture esistenti.

Odoo esporta un’operazione come `TD18` se vengono rispettate le seguenti condizioni:

  * si tratta di una fattura fornitore;

  * il **partner** viene da un Paese **UE** ;

  * almeno una delle imposte presenti nelle righe della fattura deve corrispondere alla griglia delle imposte VJ9;

  * tutte le righe della fattura presentano la voce Di consumo per i **prodotti** oppure un’imposta con i Beni come **ambito impositivo**.




#### TD19 - Acquistare beni dal deposito IVA¶

Comprare **beni** da un fornitore **straniero** ma i **beni** sono già in **Italia** in un **deposito IVA**.

  * Dall’UE: l” **acquirente** integra la fattura ricevuta con le **informazioni sull’IVA** da dichiarare in Italia (ad es. **integrazione imposte fattura fornitore**);

  * Non-UE: l” _acquirente_ invia una fattura a _se stesso_ (ad es., **autofatturazione**).




Odoo esporta un’operazione come `TD19` se vengono rispettate le seguenti condizioni:

  * si tratta di una fattura fornitore;

  * almeno una delle imposte presenti nelle righe della fattura deve corrispondere alla griglia delle imposte VJ3;

  * tutte le righe della fattura presentano la voce Di consumo per i **prodotti** oppure un’imposta con i Beni come **ambito impositivo**.




#### TD24 - Fatture differite¶

La **fattura differita** è una fattura **emessa in ritardo** rispetto alla vendita dei beni o all’erogazione dei servizi. Una **fattura differita** deve essere emessa al massimo il **15 giorno** del mese successivo alla consegna oggetto del documento.

Di solito, si tratta di una **fattura periodica** che contiene l’elenco delle vendite di beni o servizi effettuate durante il mese. L’azienda può **raggruppare** le vendite in un”**unica fattura** solitamente emessa alla **fine del mese** per ragioni contabili. Le fatture differite sono predefinite per i **commercianti all’ingrosso** che hanno clienti ricorrenti.

Se i beni sono trasportati da un _+corriere*_ , ogni consegna presenta un **Documento di Transporto (DDT)** associato. La fattura differita **deve** indicare i dettagli delle informazioni di tutti i **DDT** per una migliore tracciabilità.

Nota

La fatturazione elettronica di fatture differite richiede il `l10n_it_stock_ddt` modulo <italy/modules>. In questo caso, nella fattura elettronica viene utilizzato un :guilabel:`Tipo Documento `TD24` specifico.

Odoo esporta le transazioni come `TD24` se vengono rispettate le seguenti condizioni:

  1. è una fattura;

  2. è associata a consegne i cui **DDT** hanno una data **diversa** rispetto a quella di emissione della fattura.




#### TD28 - San Marino¶

##### Fatture¶

La Repubblica di San Marino e l’Italia hanno accordi speciali per quanto riguarda le operazioni legate alla fatturazione elettronica. Le **fatture** seguono le regole comuni per l” **inversione contabile**. È possibile utilizzare il Tipo documento appropriato in base al tipo di fattura: `TD01`, `TD04`, `TD05`, `TD24`, `TD25`. Odoo non supporta ulteriori requisiti aggiuntivi ma lo **Stato** chiede comunque all’utente di:

  * selezionare un’imposta con Tipo di esenzione fiscale impostato su `N3.3`;

  * Use the generic SdI Destination Code `2R4GTO8`.




In seguito, la fattura viene inviata da un ufficio specifico di San Marino all’azienda corretta.

##### Fatture fornitore¶

Quando si riceve una **fattura cartacea** da San Marino, qualsiasi azienda italiana **deve** inviare la fattura all” AdE compilando il campo Tipo Documento della fattura elettronica con il valore speciale `TD28`.

Odoo esporta un’operazione come `TD28` se vengono rispettate le seguenti condizioni:

  1. si tratta di una fattura fornitore;

  2. almeno una delle imposte presenti nelle righe della fattura deve corrispondere alla griglia delle imposte VJ;

  3. Il **Paese** del partner è **San Marino**.




## Aziende pubblica amministrazione (B2G)¶

Le aziende della PA sono soggette a maggiori controlli rispetto alle aziende private in quanto gestiscono il denaro pubblico proveniente dai contribuenti. Il procedimento EDI aggiunge alcune fasi al procedimento regolare, in quanto le aziende della PA possono **accettare** o **rifiutare** le fatture.

Nota

Le aziende della PA hanno un Codice destinatario a 6 cifre chiamato anche CUU **obbligatorio** , in questo caso non è possibile utilizzare indirizzi **PEC**.

Vedi anche

[Elenco completo di aziende appartenenti alla Pubblica Amministrazione con rispettivi Codici destinatario](https://www.agenziaentrate.gov.it/portale/web/guest/aree-tematiche/fatturazione-elettronica)

### CIG, CUP, dati ordine d’acquisto¶

Per garantire la tracciabilità dei pagamenti da parte delle amministrazioni pubbliche, le fatture elettroniche emesse devono contenere:

  * Il CIG, tranne nei casi d’esclusione dalla tracciabilità previsti dalla legge n. 136 del 13 agosto 2010;

  * Il CUP, in caso di fatture relative a lavori pubblici.




Se il file XML lo richiede, l”AdE può _solo_ elaborare i pagamenti di fatture elettroniche quando il file XML contiene un CIG e un CUP.

Nota

Il CUP e il CIG devono inclusi in una delle seguenti etichette XML: `DatiOrdineAcquisto`, `DatiContratto`, `DatiConvenzione`, `DateRicezione`, or `DatiFattureCollegate`.

Questi corrispondono agli elementi chiamati CodiceCUP e CodiceCIG del file XML relativo alla fattura elettronica la cui tabella può essere consultata sul sito del governo <http://www.fatturapa.gov.it/>.

### Pagamento frazionato¶

Il meccanismo del Pagamento frazionato è molto simile all”italy/Inversione contabile.

Example

Quando un’azienda italiana fattura un’azienda della PA \- ad esempio, servizi di pulizia per un edificio pubblico - l’azienda PA autodenuncia l’IVA all’Agenzia delle Entrate e il fornitore deve solo selezionare l’imposta appropriata con l”Esenzione fiscale giusta per le righe della fattura.

La posizione fiscale relativa alla Scissione dei Pagamenti è disponibile per trattare con i partner appartenenti alla PA.

### Elabora¶

#### Firma elettronica qualificata¶

Per le fatture destinate alla PA, è richiesta una **Firma elettronica qualificata** per tutti i file inviati tramite l” SdI. Il file **XML** deve essere certificato attraverso:

  * una **smart card** ;

  * un **token USB** ;

  * un HSM.




Avvertimento

Odoo **non può** firmare elettronicamente i documenti per te. Quando viene individuato un Codice Destinatario a 6 cifre, il procedimento EDI si interrompe e la fattura assume lo stato di Richiede firma utente. È possibile scaricare il documento in XML, firmarlo attraverso qualsiasi programma esterno per la Firma digitale qualificata e inviarlo attraverso il portale dell”AdE.

#### Accettazione o rifiuto¶

Avvertimento

Dato che Odoo non gestisce l’invio di fatture firmate alle aziende della PA, questi stati non possono essere attivati direttamente da Odoo. Quando si carica la fattura sul portale AdE, Odoo riceve le notifiche in merito, inserendo lo Stato SDI corretto nella fattura.

Dopo aver ricevuto la fattura attraverso l”SdI, l’azienda della PA ha 15 giorni per accettare la fattura. In caso di esito positivo, il processo termina qui. Se l’azienda della PA rifiuta la fattura, viene ancora considerata valida una volta accetta dall”SdI. In seguito, è necessario emettere una nota di credito per compensare e inviarla all”SdI.

#### Termini di scadenza¶

Se l’azienda della PA non risponde entro 15 giorni, è necessario contattare l’azienda interessata inviando loro sia la fattura che la notifica con la data limite di pagamento ricevuta tramite e-mail. È possibile accordarsi con loro e impostare manualmente lo Stato SDI corretto sulla fattura.

## Stampanti fiscali per il Punto vendita¶

Le disposizioni fiscali impongono l’utilizzo di dispositivi RT certificati, come stampanti o server, per garantire la conformità degli scontrini e comunicazioni sicure con l’autorità fiscale. I dispositivi trasmettono automaticamente i dati fiscali, su base giornaliera. Le stampanti RT, progettate per terminali POS individuali, gestiscono transazioni, stampano scontrini e comunicano con le autorità così da garantire l’integrità e la conformità dei dati.

### Modalità di simulazione¶

Avvertimento

La modalità di simulazione deve essere attività all’inizio del processo di configurazione della stampante perché comporta l’invio di dati alle autorità. Una volta effettuato il passaggio alla modalità di produzione, non sarà più possibile tornare alla modalità di simulazione.

Per testare la configurazione della stampante fiscale con Odoo, attiva la modalità di simulazione e segui le istruzioni qui elencate:

  1. assicurati che la stampante fiscale sia nello stato predefinito: stampante accesa, ciclo di avviamento completato e nessuna transazione in corso

  2. digita `3333`

  3. Press Chiave. The screen displays Scelta Funzione.

  4. scrivi `14`. Sullo schermo apparirà Apprendimento

  5. scrivi `62`. Sullo schermo apparirà Simulazione

  6. per passare da no a sì, premi su X

  7. Per confermare, premi su Contante

  8. premi su Chiave.




Per configurare la stampante per la produzione, ripeti gli step descritti in alto.

Nota

Per testare la configurazione della stampante, il dispositivo fisico deve essere ottenuto e registrato presso le autorità competenti.

### Configurazione della stampante per l’utilizzo con Odoo¶

Le stampanti fiscali sono progettate per lavorare solo su reti locali. Ciò significa che la stampante e il dispositivo che utilizzano [Odoo Punto vendita](../../sales/point_of_sale.html) devono essere collegati alla stessa rete.

In genere, le stampanti fiscali sono configurate per utilizzare il protocollo HTTP in maniera predefinita. Per garantire la compatibilità con Odoo, le impostazioni devono essere aggiornate per abilitare il supporto del protocollo HTTPS sulla stampante. È possibile farlo utilizzando il software di configurazione EpsonFPWizard oppure la tastiera collegata alla stampante.

Segui gli step descritti di seguito per configurare la stampante fiscale utilizzando la tastiera:

  1. assicurati che la stampante fiscale sia nello stato predefinito: stampante accesa, ciclo di avviamento completato e nessuna transazione in corso

  2. digita `3333`

  3. premi Chiave. Sullo schermo apparirà Scelta Funzione

  4. digita `34`. Sullo schermo apparirà Web Server

  5. Premi Contante per 3 volte fino a quando sullo schermo apparirà Web Server: SSL

  6. per passare da `0` a `1`, premi X

  7. per confermare, premi Contante 3 volte

  8. premi su Chiave.




In seguito, accedi alla stampante dal dispositivo su cui è installata l’applicazione [Odoo Punto vendita](../../sales/point_of_sale.html) in modo che possa riconoscere il certificato della stampante.

Per approvare e installare il certificato della stampante, segui gli step descritti:

  1. accedi alla stampante aprendo un browser web e inserendo `https://<ip-of-your-printer>` nella barra degli indirizzi. Apparirà un messaggio relativo alla sicurezza: Attenzione: potenziale rischio per la sicurezza.

  2. fai clic su Avanzato per visualizzare le opzioni di approvazione del certificato

  3. fai clic su Procedi per convalidare il certificato.




In seguito, per assicurarti che [Odoo Punto vendita](../../sales/point_of_sale.html) sia configurato con la stampante fiscale, vai su Punto vendita ‣ Configurazione‣ Impostazioni. Nella sezione Dispositivi connessi, aggiungi l’indirizzo IP nel campo Indirizzo IP stampante fiscale italiana e attiva l’opzione Usa HTTPS.

## Ri.Ba. (Ricevuta Bancaria)¶

Ri.Ba. is a payment method widely used in Italy where vendors request payments through their bank, which forwards the request to the customer’s own bank and takes responsibility for the collection. This enables payment automation and reduces risks for the vendor.

The vendor generally uploads a fixed-format text file with the list of payments to the bank’s web portal.

Nota

  * Ri.Ba. are exclusively for **domestic payments** in Italy. For recurring international payments, please use [SEPA Direct Debt (SDD)](../accounting/payments/batch_sdd-2.html)




### Configurazione¶

  1. Check that the `l10n_it_riba` module is [installed](../../general/apps_modules.html#general-install).

  2. Go to Settings ‣ Users & Companies ‣ Companies and select the company that will use Ri.Ba.

  3. Fill out the required SIA Code.

Nota

The SIA Code identifies businesses within the Italian banking network and is used to receive money through specific payment methods. It consists of one letter and four digits (e.g., T1234) and can usually be found on the bank’s portal or obtained by contacting the bank.

  4. Ensure the Company’s bank account has an Italian IBAN.

Vedi anche

How to configure [Bank Accounts](../accounting/bank.html)




### Accept Ri.Ba. for your invoices¶

Payments of type Ri.Ba. can be registered from the Invoices (Accounting ‣ Customers ‣ Invoices).

Importante

Make sure that your invoice involves a Partner that has a bank account with an Italian IBAN.

Then, all Payments must be grouped in a **Batch Payment**.

Vedi anche

  * [Batch Payments](../accounting/payments.html)

  * [Create a Batch Payment](../accounting/payments/batch.html)




Once you press the Validate button for the Batch Payment, the Ri.Ba. file is generated and attached to the Batch Payment, so you can download it and upload it through your bank’s web portal.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/applications/finance/fiscal_localizations/italy.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](jordan.html "Giordania") |
  * [precedente](indonesia.html "Indonesia") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Documentazione utente](../../../applications.html) »
  * [Finanza](../../finance.html) »
  * [Fiscal localizations](../fiscal_localizations.html) »
  * Italia


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: in-app purchases
  *[RTL]: right-to-left
  *[RST]: reStructuredText
  *[GUI]: graphical user interface
  *[TOC]: Table Of Contents
  *[SEO]: Search Engine Optimization
  *[EDI]: Electronic Data Interchange
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
  *[API]: application programming interface
  *[IVA]: imposta sul valore aggiunto
  *[MRR]: Monthly Recurring Revenue
  *[ARR]: Annual Recurring Revenue
  *[USB]: Universal Serial Bus
  *[IoT]: Internet of Things
  *[OS]: Operating System
  *[SO]: Sales Order
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
  *[LIFO]: Last-In, First-Out
  *[SAQ]: Self-Assessment Questionnaire
  *[VAT]: Value Added Tax
  *[SMP]: Service Metadata Publisher
  *[AVCO]: Average Cost Valuation
  *[OdA]: Ordine di acquisto
  *[sportello unico OSS]: One-Stop Shop
  *[IAPs]: in-app purchases
  *[SOs]: Sales Order
  *[SRI]: servicio de rentas internas
  *[ATS]: Anexo Transaccional Simplificado
  *[FPS]: Service Public Federal Finances
  *[ADW]: Average Daily Wage
  *[SII]: Servicio de Impuestos Internos
  *[CAFs]: Folio Authorization Code
  *[DTE]: Documentos Tributarios Electrónicos
  *[RUT]: Rol Único Tributario
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
  *[OTP]: one-time password
  *[GAAP]: Generally Acceptable Accounting Practices
  *[AR]: Accounts Receivable
  *[AP]: Accounts Payable
  *[CoA]: Chart of Accounts
  *[SEC]: Securities and Exchange Commission
  *[CFS]: Cash Flow Statement
  *[ACH]: Automated Clearing House
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
  *[PAC]: fornitori autorizzati
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
  *[NSSL]: Non-Shopee Supported Logistics
  *[MID]: Merchant ID
  *[TID]: Terminal ID
  *[ISBN]: International Standard Book Number
  *[IP]: intellectual property
  *[SSC]: Jordanian Social Security Corporation
  *[UAE]: United Arab Emirates
  *[GCC]: Gulf Cooperation Council
  *[DEWS]: Daman Investments End of Service Programme
  *[WPS]: Wages Protection System
  *[EOS]: End Of Service
  *[EDR]: Employee Detail Record
  *[SCR]: Salary Control Record
  *[B2G]: business-to-government
  *[UBL]: Universal Business Language
  *[ZRE]: Zentraler Rechnungseingang
  *[OZG-RE]: Onlinezugangsgesetz-Rechnungseingang
  *[IGV]: Impuesto General a las Ventas) e di altre imposte applicabili, garantendo accuratezza e conformità con gli standard di rendicontazione fiscale del :abbr:`SUNAT (Superintendencia Nacional de Aduanas y de Administración Tributaria
  *[CUFE]: Código Único de Factura Electrónica
  *[CIUS-PT]: Customizable Invoice User Specification for Portugal
  *[USP]: Unternehmensserviceportal
  *[CIS]: Central Invoice System
  *[CAE]: Código de Autorización Electrónico
  *[FE]: Factura Electrónica
  *[CFE]: Comprobante Fiscal Electrónico
  *[ANAF]: Agenzia nazionale rumena per l'amministrazione fiscale
  *[Sdi]: Sistema di Interscambio
  *[NF-e]: Nota Fiscal Eletrônica
  *[NFS-e]: Nota Fiscal de Serviços Eletrônica
  *[NFC-e]: Nota Fiscal de Consumidor Eletrônica
  *[SEFAZ]: Secretaria da Fazenda
  *[SIREN]: Système d'identification du répertoire des entreprises, Business Directory Identification System
  *[MICR]: Magnetic Ink Character Recognition
  *[NIT]: El Número de Identificación Tributaria
  *[SLSP]: Summary List of Sales and Purchases
  *[QAP]: Quarterly Alphalist of Payees
  *[SAWT]: Summary Alphalist of Withholding Tax
  *[PCHC]: Philippine Clearing House Corporation