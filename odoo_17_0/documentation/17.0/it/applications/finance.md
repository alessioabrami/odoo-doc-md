# Finanza — Odoo 17.0 documentazione

### Navigazione

  * [indice](../genindex.html "Indice generale")
  * [moduli](../py-modindex.html "Indice del modulo Python") |
  * [successivo](finance/accounting.html "Contabilità e fatturazione") |
  * [precedente](essentials/keyboard_shortcuts.html "Scelte rapide da tastiera") |
  * [Odoo 17.0 documentazione](../index-2.html) »
  * [Documentazione Utente](../applications.html) »
  * Finanza



# Finanza¶

  * [Contabilità e fatturazione](finance/accounting.html)
    * [Contabilità a partita doppia](finance/accounting.html#double-entry-bookkeeping)
    * [Base di competenza e base di cassa](finance/accounting.html#accrual-and-cash-basis)
    * [Multi-azienda](finance/accounting.html#multi-company)
    * [Ambiente multi-valuta](finance/accounting.html#multi-currency-environment)
    * [Gestione delle filiali](finance/accounting.html#branch-management)
    * [Standard internazionali](finance/accounting.html#international-standards)
    * [Conti attivi e passivi](finance/accounting.html#accounts-receivable-and-payable)
    * Rendiconto
      * [Resoconto FISCALE](finance/accounting.html#tax-report)
    * [Sincronizzazione bancaria](finance/accounting.html#bank-synchronization)
    * [Valutazione dell’inventario](finance/accounting.html#inventory-valuation)
    * [Utili a nuovo](finance/accounting.html#retained-earnings)
    * Fiduciari
      * [Esordiente](finance/accounting/get_started.html)
        * Banner onboarding Contabilità
          * [Periodi contabili](finance/accounting/get_started.html#accounting-periods)
          * [Conto bancario](finance/accounting/get_started.html#bank-account)
          * [Imposte](finance/accounting/get_started.html#taxes)
          * [Piano dei conti](finance/accounting/get_started.html#chart-of-accounts)
        * Banner onboarding Fatturazione
          * [Dati azienda](finance/accounting/get_started.html#company-data)
          * [Struttura documenti](finance/accounting/get_started.html#documents-layout)
          * [Crea fattura](finance/accounting/get_started.html#create-invoice)
          * Pagamenti online
            * Promemoria contabile
              * Piano dei conti
                * [Esempio](finance/accounting/get_started/cheat_sheet.html#example)
              * [Registrazioni contabili](finance/accounting/get_started/cheat_sheet.html#journal-entries)
              * [Riconciliazione](finance/accounting/get_started/cheat_sheet.html#reconciliation)
              * [Riconciliazione bancaria](finance/accounting/get_started/cheat_sheet.html#bank-reconciliation)
              * [Gestione degli assegni](finance/accounting/get_started/cheat_sheet.html#checks-handling)
            * Piano dei conti
              * Configurare un conto
                * [Codice e nome](finance/accounting/get_started/chart_of_accounts.html#code-and-name)
                * Tipo
                  * [Cespiti](finance/accounting/get_started/chart_of_accounts.html#assets)
                * [Imposte predefinite](finance/accounting/get_started/chart_of_accounts.html#default-taxes)
                * [Etichette](finance/accounting/get_started/chart_of_accounts.html#tags)
                * Gruppi del conto
                  * [Creare gruppi conto manualmente](finance/accounting/get_started/chart_of_accounts.html#create-account-groups-manually)
                * [Consentire la riconciliazione](finance/accounting/get_started/chart_of_accounts.html#allow-reconciliation)
                * [Non attivo](finance/accounting/get_started/chart_of_accounts.html#deprecated)
            * Sistema multi valuta
              * Configurazione
                * [Valuta principale](finance/accounting/get_started/multi_currency.html#main-currency)
                * [Abilita le valute straniere».](finance/accounting/get_started/multi_currency.html#enable-foreign-currencies)
                * Tassi di cambio
                  * [Aggiornamento manuale](finance/accounting/get_started/multi_currency.html#manual-update)
                  * [Aggiornamento automatico](finance/accounting/get_started/multi_currency.html#automatic-update)
                * [Voci di differenza di cambio](finance/accounting/get_started/multi_currency.html#exchange-difference-entries)
                * [Piano dei conti](finance/accounting/get_started/multi_currency.html#chart-of-accounts)
                * [Registri](finance/accounting/get_started/multi_currency.html#journals)
              * Contabilità multi valuta
                * [Fatture cliente, fornitore e altri documenti](finance/accounting/get_started/multi_currency.html#invoices-bills-and-other-documents)
                * [Registrare un pagamento](finance/accounting/get_started/multi_currency.html#payment-registration)
                * [Operazioni bancarie](finance/accounting/get_started/multi_currency.html#bank-transactions)
                * [Tasso di cambio registrazioni contabili](finance/accounting/get_started/multi_currency.html#exchange-rate-journal-entries)
            * Prezzo medio sulla merce resa
              * [Configurazione](finance/accounting/get_started/avg_price_valuation.html#configuration)
              * Utilizzare la valutazione del costo medio
                * [Formula](finance/accounting/get_started/avg_price_valuation.html#formula)
                * Calcolare il costo medio
                  * [Consegna prodotto (caso d’uso)](finance/accounting/get_started/avg_price_valuation.html#product-delivery-use-case)
              * Restituire prodotti al fornitore (caso d’uso)
                * [Eliminare errori di valutazione del magazzino nei prodotti in uscita](finance/accounting/get_started/avg_price_valuation.html#eliminate-stock-valuation-errors-in-outgoing-products)
              * Contabilità anglosassone
                * Ricezione prodotto
                  * [Riepilogo](finance/accounting/get_started/avg_price_valuation.html#summary)
                  * Conti bilanciati con prodotti ricevuti
                    * [In Odoo](finance/accounting/get_started/avg_price_valuation.html#in-odoo)
                  * Conti bilanciati una volta ricevuta la fattura fornitore
                    * [In Odoo](finance/accounting/get_started/avg_price_valuation.html#id1)
                * [Alla consegna dei prodotti](finance/accounting/get_started/avg_price_valuation.html#on-product-delivery)
                * [Alla restituzione dei prodotti](finance/accounting/get_started/avg_price_valuation.html#on-product-return)
            * Unità fiscali
              * Configurazione
                * [Posizione di bilancio](finance/accounting/get_started/tax_units.html#fiscal-position)
              * [Resoconto FISCALE](finance/accounting/get_started/tax_units.html#tax-report)
      * [Imposte](finance/accounting/taxes.html)
        * [Imposte predefinite](finance/accounting/taxes.html#default-taxes)
        * [Attivare imposte di vendita dalla vista elenco](finance/accounting/taxes.html#activate-sales-taxes-from-the-list-view)
        * Configurazione
          * Opzioni di base
            * [Nome imposta](finance/accounting/taxes.html#tax-name)
            * [Calcolare le imposte](finance/accounting/taxes.html#tax-computation)
            * [Attivo](finance/accounting/taxes.html#active)
            * [Tipo di imposta](finance/accounting/taxes.html#tax-type)
            * [Ambito imposte](finance/accounting/taxes.html#tax-scope)
          * [Scheda Definizione](finance/accounting/taxes.html#definition-tab)
          * Scheda Opzioni avanzate
            * [Etichetta su fatture](finance/accounting/taxes.html#label-on-invoices)
            * [Gruppo imposte](finance/accounting/taxes.html#tax-group)
            * [Includere nel costo analitico](finance/accounting/taxes.html#include-in-analytic-cost)
            * [Includere nel prezzo](finance/accounting/taxes.html#included-in-price)
            * [Determinare imponibile imposte successive](finance/accounting/taxes.html#affect-base-of-subsequent-taxes)
        * Imposte aggiuntive
          * Imposte per cassa
            * [Configurazione](finance/accounting/taxes/cash_basis.html#configuration)
            * [Impatto delle imposte con criterio di cassa sulla contabilità](finance/accounting/taxes/cash_basis.html#impact-of-cash-basis-taxes-on-accounting)
          * Imposte alla fonte
            * [Configurazione](finance/accounting/taxes/retention.html#configuration)
            * [Ritenute d’acconto sulle fatture](finance/accounting/taxes/retention.html#retention-taxes-on-invoices)
          * Verifica numero partita IVA (VIES)
            * [Verifica numero partita IVA VIES](finance/accounting/taxes/vat_verification.html#vies-vat-number-verification)
          * Posizioni di bilancio (mappatura fiscale e contabile)
            * Configurazione
              * [Mappatura fiscale e contabile](finance/accounting/taxes/fiscal_positions.html#tax-and-account-mapping)
            * Proposta
              * [Applicazione automatica](finance/accounting/taxes/fiscal_positions.html#automatic-application)
              * [Applicazione manuale](finance/accounting/taxes/fiscal_positions.html#manual-application)
              * [Assegnare a un partner](finance/accounting/taxes/fiscal_positions.html#assign-to-a-partner)
          * [Integrazione AvaTax](finance/accounting/taxes/avatax.html)
            * Eseguire la configurazione su AvaTax
              * [Creare un profilo aziendale di base](finance/accounting/taxes/avatax.html#create-basic-company-profile)
              * [Collegarsi ad AvaTax](finance/accounting/taxes/avatax.html#connect-to-avatax)
            * Configurazione Odoo
              * [Paese fiscale](finance/accounting/taxes/avatax.html#fiscal-country)
              * [Impostazioni azienda](finance/accounting/taxes/avatax.html#company-settings)
              * [Installazione del modulo](finance/accounting/taxes/avatax.html#module-installation)
              * Impostazioni AvaTax Odoo
                * [Prerequisiti](finance/accounting/taxes/avatax.html#prerequisites)
                * [Credenziali](finance/accounting/taxes/avatax.html#credentials)
                * [Opzioni transazioni](finance/accounting/taxes/avatax.html#transaction-options)
                * [Convalida indirizzo](finance/accounting/taxes/avatax.html#address-validation)
                * [Testare la connessione](finance/accounting/taxes/avatax.html#test-connection)
                * [Parametri di sincronizzazione](finance/accounting/taxes/avatax.html#sync-parameters)
              * Posizione di bilancio
                * [Conti AvaTax](finance/accounting/taxes/avatax.html#avatax-accounts)
              * Mappatura imposte
                * [Mappatura categorie prodotto](finance/accounting/taxes/avatax.html#product-category-mapping)
                * Mappatura dei prodotti
                  * Utilizzare AvaTax
                    * Calcolare le imposte
                      * [Trigger automatici](finance/accounting/taxes/avatax/avatax_use.html#automatic-triggers)
                      * [Trigger manuali](finance/accounting/taxes/avatax/avatax_use.html#manual-triggers)
                    * [Sincronizzazione AvaTax](finance/accounting/taxes/avatax/avatax_use.html#avatax-synchronization)
                    * [Sconti prezzo fisso](finance/accounting/taxes/avatax/avatax_use.html#fixed-price-discounts)
                    * [Registrazione](finance/accounting/taxes/avatax/avatax_use.html#logging)
                  * Portale Avalara (Avatax)
                    * Transazioni
                      * [Modificare le transazioni](finance/accounting/taxes/avatax/avalara_portal.html#edit-transaction)
                      * [Filtro](finance/accounting/taxes/avatax/avalara_portal.html#filter)
                      * Ordina per
                        * [Personalizzare le colonne](finance/accounting/taxes/avatax/avalara_portal.html#customize-columns)
                      * [Importazione ed esportazione](finance/accounting/taxes/avatax/avalara_portal.html#import-export)
                      * [Report](finance/accounting/taxes/avatax/avalara_portal.html#reports)
                    * [Aggiungere più giurisdizioni](finance/accounting/taxes/avatax/avalara_portal.html#add-more-jurisdictions)
                    * [Certificato esenzione da imposta](finance/accounting/taxes/avatax/avalara_portal.html#tax-exemption-certificate)
                    * [Operazioni di fine anno](finance/accounting/taxes/avatax/avalara_portal.html#end-of-year-operations)
          * [TaxCloud integration](finance/accounting/taxes/taxcloud.html)
          * Vendite a distanza intracomunitarie nell’UE
            * [Configurazione](finance/accounting/taxes/eu_distance_selling.html#configuration)
            * One-Stop Shop (OSS)
              * [Report](finance/accounting/taxes/eu_distance_selling.html#reports)
          * Tariffe B2B (imposte escluse) e B2C (imposte incluse)
            * Configurazione
              * [Introduzione](finance/accounting/taxes/B2B_B2C.html#introduction)
              * [E-commerce](finance/accounting/taxes/B2B_B2C.html#ecommerce)
              * [Configurare i prodotti](finance/accounting/taxes/B2B_B2C.html#setting-your-products)
              * [Configurare una posizione di bilancio B2C](finance/accounting/taxes/B2B_B2C.html#setting-the-b2c-fiscal-position)
            * [Fare un test creando un preventivo](finance/accounting/taxes/B2B_B2C.html#test-by-creating-a-quotation)
            * [Evitare di modificare ogni singolo ordine di vendita](finance/accounting/taxes/B2B_B2C.html#avoid-changing-every-sale-order)
      * [Fatture cliente](finance/accounting/customer_invoices.html)
        * [Creazione fattura](finance/accounting/customer_invoices.html#invoice-creation)
        * [Conferma fattura](finance/accounting/customer_invoices.html#invoice-confirmation)
        * [Invio fattura](finance/accounting/customer_invoices.html#invoice-sending)
        * [Pagamento e riconciliazione](finance/accounting/customer_invoices.html#payment-and-reconciliation)
        * [Controllo pagamenti](finance/accounting/customer_invoices.html#payment-follow-up)
        * Rendiconto
          * Rendiconti partner
            * [Partitario clienti/fornitori](finance/accounting/customer_invoices.html#partner-ledger)
            * [Crediti esigibili](finance/accounting/customer_invoices.html#aged-receivable)
            * [Debiti scaduti](finance/accounting/customer_invoices.html#aged-payable)
          * [Conto economico](finance/accounting/customer_invoices.html#profit-and-loss)
          * Stato patrimoniale
            * Processi di fatturazione
              * Vendite
                * [Ordine di vendita ‣ Fattura](finance/accounting/customer_invoices/overview.html#sales-order-invoice)
                * [Ordine di vendita ‣ Ordine di consegna ‣ Fattura](finance/accounting/customer_invoices/overview.html#sales-order-delivery-order-invoice)
                * [Ordine e-commerce ‣ Fattura](finance/accounting/customer_invoices/overview.html#ecommerce-order-invoice)
              * Contratti
                * [Contratti regolari ‣ Fatture](finance/accounting/customer_invoices/overview.html#regular-contracts-invoices)
                * [Contratti ricorrenti ‣ Fatture](finance/accounting/customer_invoices/overview.html#recurring-contracts-invoices)
              * Altri
                * [Creare una fattura manualmente](finance/accounting/customer_invoices/overview.html#creating-an-invoice-manually)
                * [Moduli specifici](finance/accounting/customer_invoices/overview.html#specific-modules)
                * [Risequenziare le fatture](finance/accounting/customer_invoices/overview.html#resequencing-of-the-invoices)
                * [Digitalizzare le fatture con il riconoscimento ottico dei caratteri (OCR)](finance/accounting/customer_invoices/overview.html#invoice-digitization-with-optical-character-recognition-ocr)
            * Indirizzi di consegna e di fatturazione
              * [Configurazione](finance/accounting/customer_invoices/customer_addresses.html#configuration)
              * [Fatturare e spedire a indirizzi diversi](finance/accounting/customer_invoices/customer_addresses.html#invoice-and-deliver-to-different-addresses)
            * Termini di pagamento e piani di rateizzazione
              * [Configurazione](finance/accounting/customer_invoices/payment_terms.html#configuration)
              * [Utilizzare i termini di pagamento](finance/accounting/customer_invoices/payment_terms.html#using-payment-terms)
              * [Registrazioni contabili](finance/accounting/customer_invoices/payment_terms.html#journal-entries)
            * Termini e condizioni predefiniti
              * [Configurazione](finance/accounting/customer_invoices/terms_conditions.html#configuration)
            * Sconti di cassa e riduzioni fiscali
              * Configurazione
                * [Sconto di cassa conti utili e perdite](finance/accounting/customer_invoices/cash_discounts.html#cash-discount-gain-loss-accounts)
                * [Termini di pagamento](finance/accounting/customer_invoices/cash_discounts.html#payment-terms)
                * [Riduzioni fiscali](finance/accounting/customer_invoices/cash_discounts.html#tax-reductions)
              * Applicare uno sconto di cassa alla fattura di un cliente
                * [Riconciliazione pagamenti](finance/accounting/customer_invoices/cash_discounts.html#payment-reconciliation)
            * Note di credito e rimborsi
              * [Creare una nota di credito cliente](finance/accounting/customer_invoices/credit_notes.html#issue-a-customer-credit-note)
              * [Creare una nota di debito cliente](finance/accounting/customer_invoices/credit_notes.html#issue-a-customer-debit-note)
              * [Registrare un rimborso fornitore](finance/accounting/customer_invoices/credit_notes.html#record-a-vendor-refund)
              * [Registrare una nota di debito fornitore](finance/accounting/customer_invoices/credit_notes.html#record-a-vendor-debit-note)
              * [Registrazioni contabili](finance/accounting/customer_invoices/credit_notes.html#journal-entries)
            * Arrotondamento di cassa
              * [Configurazione](finance/accounting/customer_invoices/cash_rounding.html#configuration)
              * [Applicare gli arrotondamenti](finance/accounting/customer_invoices/cash_rounding.html#apply-roundings)
            * Risconti passivi
              * [Configurazione](finance/accounting/customer_invoices/deferred_revenues.html#configuration)
              * [Generare registrazioni differite al momento della convalida](finance/accounting/customer_invoices/deferred_revenues.html#generate-deferral-entries-on-validation)
              * [Rendiconto](finance/accounting/customer_invoices/deferred_revenues.html#reporting)
              * [Generare registrazioni differite raggruppate manualmente](finance/accounting/customer_invoices/deferred_revenues.html#generate-grouped-deferral-entries-manually)
            * Fatturazione elettronica (EDI)
              * Configurazione
                * [Fatturazione elettronica nazionale](finance/accounting/customer_invoices/electronic_invoicing.html#national-electronic-invoicing)
              * [Generazione di fatture elettroniche](finance/accounting/customer_invoices/electronic_invoicing.html#e-invoices-generation)
              * Peppol
                * [Registrazione](finance/accounting/customer_invoices/electronic_invoicing.html#registration)
                * [Verificare un contatto](finance/accounting/customer_invoices/electronic_invoicing.html#contact-verification)
                * [Inviare fatture](finance/accounting/customer_invoices/electronic_invoicing.html#send-invoices)
                * [Ricevere fatture fornitore](finance/accounting/customer_invoices/electronic_invoicing.html#receive-vendor-bills)
            * Sequenza fattura
              * [Modificare la sequenza predefinita](finance/accounting/customer_invoices/sequence.html#changing-the-default-sequence)
              * [Risequenziare le fatture in massa](finance/accounting/customer_invoices/sequence.html#mass-resequencing-invoices)
            * Posta ordinaria
              * [Configurazione](finance/accounting/customer_invoices/snailmail.html#configuration)
              * [Inviare fatture tramite posta](finance/accounting/customer_invoices/snailmail.html#send-invoices-by-post)
              * [Tariffazione](finance/accounting/customer_invoices/snailmail.html#pricing)
            * Codici QR EPC
              * Configurazione
                * [Configurare il registro del tuo conto bancario](finance/accounting/customer_invoices/epc_qr_code.html#configure-your-bank-account-s-journal)
              * [Emettere fatture con codici QR EPC](finance/accounting/customer_invoices/epc_qr_code.html#issue-invoices-with-epc-qr-codes)
            * Termini di resa
              * Stabilire un termine di resa
                * [Posizione termine di resa](finance/accounting/customer_invoices/incoterms.html#incoterm-location)
              * [Configurazione termini di resa predefinita](finance/accounting/customer_invoices/incoterms.html#default-incoterm-configuration)
      * [Fatture fornitore](finance/accounting/vendor_bills.html)
        * Bill creation
          * [Manuale](finance/accounting/vendor_bills.html#manually)
          * [Automaticamente](finance/accounting/vendor_bills.html#automatically)
        * [Bill completion](finance/accounting/vendor_bills.html#bill-completion)
        * [Bill confirmation](finance/accounting/vendor_bills.html#bill-confirmation)
        * [Pagamento e riconciliazione](finance/accounting/vendor_bills.html#payment-and-reconciliation)
        * Aged payable report
          * AI-powered document digitization
            * [Configurazione](finance/accounting/vendor_bills/invoice_digitization.html#configuration)
            * Invoice upload
              * [Upload invoices manually](finance/accounting/vendor_bills/invoice_digitization.html#upload-invoices-manually)
              * [Upload invoices using an email alias](finance/accounting/vendor_bills/invoice_digitization.html#upload-invoices-using-an-email-alias)
            * [Invoice digitization](finance/accounting/vendor_bills/invoice_digitization.html#invoice-digitization)
            * [Data recognition with AI](finance/accounting/vendor_bills/invoice_digitization.html#data-recognition-with-ai)
            * [Tariffazione](finance/accounting/vendor_bills/invoice_digitization.html#pricing)
          * Non-current assets and fixed assets
            * Prerequisiti
              * [Configure an Assets Account](finance/accounting/vendor_bills/assets.html#configure-an-assets-account)
              * Post an expense to the right account
                * [Select the account on a draft bill](finance/accounting/vendor_bills/assets.html#select-the-account-on-a-draft-bill)
                * [Choose a different Expense Account for specific products](finance/accounting/vendor_bills/assets.html#choose-a-different-expense-account-for-specific-products)
                * [Change the account of a posted journal item](finance/accounting/vendor_bills/assets.html#change-the-account-of-a-posted-journal-item)
            * Assets entries
              * Crea nuova voce
                * [What does «Prorata Temporis» mean?](finance/accounting/vendor_bills/assets.html#what-does-prorata-temporis-mean)
                * [What are the different Depreciation Methods](finance/accounting/vendor_bills/assets.html#what-are-the-different-depreciation-methods)
              * [Assets from the Purchases Journal](finance/accounting/vendor_bills/assets.html#assets-from-the-purchases-journal)
            * [Modification of an Asset](finance/accounting/vendor_bills/assets.html#modification-of-an-asset)
            * [Disposal of Fixed Assets](finance/accounting/vendor_bills/assets.html#disposal-of-fixed-assets)
            * Assets Models
              * [Apply an Asset Model to a new entry](finance/accounting/vendor_bills/assets.html#apply-an-asset-model-to-a-new-entry)
            * [Automate the Assets](finance/accounting/vendor_bills/assets.html#automate-the-assets)
          * Deferred expenses
            * [Configurazione](finance/accounting/vendor_bills/deferred_expenses.html#configuration)
            * [Generare registrazioni differite al momento della convalida](finance/accounting/vendor_bills/deferred_expenses.html#generate-deferral-entries-on-validation)
            * [Rendiconto](finance/accounting/vendor_bills/deferred_expenses.html#reporting)
            * [Generare registrazioni differite raggruppate manualmente](finance/accounting/vendor_bills/deferred_expenses.html#generate-grouped-deferral-entries-manually)
          * Vendor bill sequence
            * [Modificare la sequenza predefinita](finance/accounting/vendor_bills/sequence.html#changing-the-default-sequence)
            * [Mass-resequencing vendor bills](finance/accounting/vendor_bills/sequence.html#mass-resequencing-vendor-bills)
      * [Pagamenti](finance/accounting/payments.html)
        * [Registrazione di un pagamento da una fattura o da un conto](finance/accounting/payments.html#registering-payment-from-an-invoice-or-bill)
        * Registering payments not tied to an invoice or bill
          * Payments matching
            * [For a single invoice or bill](finance/accounting/payments.html#for-a-single-invoice-or-bill)
            * Matching payments
              * [Auto-Reconcile Feature](finance/accounting/payments.html#auto-reconcile-feature)
        * [Registering payments on multiple invoices or bills (group payments)](finance/accounting/payments.html#registering-payments-on-multiple-invoices-or-bills-group-payments)
        * [Registering a single payment for multiple customers or vendors (batch payments)](finance/accounting/payments.html#registering-a-single-payment-for-multiple-customers-or-vendors-batch-payments)
        * [Registering a partial payment](finance/accounting/payments.html#registering-a-partial-payment)
        * Reconciling payments with bank transactions
          * [Online payments](finance/accounting/payments/online.html)
            * Install the patch to disable online invoice payment
              * [Update Odoo to the latest release](finance/accounting/payments/online/install_portal_patch.html#update-odoo-to-the-latest-release)
              * [Update the list of available modules](finance/accounting/payments/online/install_portal_patch.html#update-the-list-of-available-modules)
              * [Install the module Invoice Online Payment Patch](finance/accounting/payments/online/install_portal_patch.html#install-the-module-invoice-online-payment-patch)
            * [Configurazione](finance/accounting/payments/online.html#configuration)
            * [Portale clienti](finance/accounting/payments/online.html#customer-portal)
          * Controlli
            * [Method 1: Outstanding account](finance/accounting/payments/checks.html#method-1-outstanding-account)
            * [Method 2: Reconciliation bypass](finance/accounting/payments/checks.html#method-2-reconciliation-bypass)
            * [Registrare un pagamento](finance/accounting/payments/checks.html#payment-registration)
            * Registrazioni contabili
              * [Outstanding account](finance/accounting/payments/checks.html#outstanding-account)
              * [Reconciliation bypass](finance/accounting/payments/checks.html#reconciliation-bypass)
          * Pagamenti raggruppati
            * [Configurazione](finance/accounting/payments/batch.html#configuration)
            * Batch creation
              * [Riconciliazione bancaria](finance/accounting/payments/batch.html#bank-reconciliation)
          * SEPA Direct Debit (SDD) customer payments
            * Configurazione
              * [Creditor identifier](finance/accounting/payments/batch_sdd.html#creditor-identifier)
              * [PAIN file version](finance/accounting/payments/batch_sdd.html#pain-file-version)
            * SEPA Direct Debit Mandates
              * [Creating mandates](finance/accounting/payments/batch_sdd.html#creating-mandates)
              * [Closing or revoking a mandate](finance/accounting/payments/batch_sdd.html#closing-or-revoking-a-mandate)
            * [Processing SDD payments](finance/accounting/payments/batch_sdd.html#processing-sdd-payments)
            * [SDD rejections](finance/accounting/payments/batch_sdd.html#sdd-rejections)
          * Follow-up on invoices
            * [Configurazione](finance/accounting/payments/follow_up.html#configuration)
            * Report promemoria di pagamento
              * [Debtor’s trust level](finance/accounting/payments/follow_up.html#debtor-s-trust-level)
              * [Send reminders in batches](finance/accounting/payments/follow_up.html#send-reminders-in-batches)
          * Trasferimenti interni
            * [Configurazione](finance/accounting/payments/internal_transfers.html#configuration)
            * [Registrare un trasferimento interno da una banca all’altra](finance/accounting/payments/internal_transfers.html#register-an-internal-transfer-from-one-bank-to-another)
          * Pay with SEPA
            * Configurazione
              * [Activate SEPA Credit Transfer (SCT)](finance/accounting/payments/pay_sepa.html#activate-sepa-credit-transfer-sct)
              * [Activate SEPA payment methods on banks](finance/accounting/payments/pay_sepa.html#activate-sepa-payment-methods-on-banks)
              * [Registering payments](finance/accounting/payments/pay_sepa.html#registering-payments)
          * Pay by checks
            * Configurazione
              * [Activate checks payment methods](finance/accounting/payments/pay_checks.html#activate-checks-payment-methods)
            * Compatible check stationery for printing checks
              * [Stati Uniti](finance/accounting/payments/pay_checks.html#united-states)
            * Pay a supplier bill with a check
              * [Register a payment by check](finance/accounting/payments/pay_checks.html#register-a-payment-by-check)
              * [Print checks](finance/accounting/payments/pay_checks.html#print-checks)
          * Forecast future bills to pay
            * [Configuration: payment terms](finance/accounting/payments/forecast.html#configuration-payment-terms)
            * [Forecast bills to pay with the aged payable report](finance/accounting/payments/forecast.html#forecast-bills-to-pay-with-the-aged-payable-report)
            * [Select bills to pay](finance/accounting/payments/forecast.html#select-bills-to-pay)
          * Trusted accounts (send money)
            * Phishing attacks
              * [Elements to check](finance/accounting/payments/trusted_accounts.html#elements-to-check)
      * [Conti bancari e di cassa](finance/accounting/bank.html)
        * Gestire i conti bancari e di cassa
          * [Collegate la vostra banca per la sincronizzazione automatica](finance/accounting/bank.html#connect-your-bank-for-automatic-synchronization)
          * [Crea un conto bancario](finance/accounting/bank.html#create-a-bank-account)
          * [Crea un giornale di cassa](finance/accounting/bank.html#create-a-cash-journal)
          * [Modificare un giornale bancario o di cassa esistente](finance/accounting/bank.html#edit-an-existing-bank-or-cash-journal)
        * Configurazione
          * [Conto di sospensione](finance/accounting/bank.html#suspense-account)
          * [Conto economico](finance/accounting/bank.html#profit-and-loss-accounts)
          * [Valuta](finance/accounting/bank.html#currency)
          * [Numero di conto](finance/accounting/bank.html#account-number)
          * [Alimentazioni bancarie](finance/accounting/bank.html#bank-feeds)
        * Conti in sospeso
          * [Configurazione predefinita degli account](finance/accounting/bank.html#default-accounts-configuration)
          * Configurazione dei giornali di banca e cassa
            * [Sincronizzazione bancaria](finance/accounting/bank/bank_synchronization.html)
              * Configurazione
                * [Utenti On-Premise](finance/accounting/bank/bank_synchronization.html#on-premise-users)
                * [Prima sincronizzazione](finance/accounting/bank/bank_synchronization.html#first-synchronization)
                * [Sincronizzare manualmente](finance/accounting/bank/bank_synchronization.html#synchronize-manually)
              * Problemi
                * [Sincronizzazione errata](finance/accounting/bank/bank_synchronization.html#synchronization-in-error)
                * [Sincronizzazione disconnessa](finance/accounting/bank/bank_synchronization.html#synchronization-disconnected)
              * [Processo di migrazione per gli utenti che hanno installato Odoo prima di dicembre 2020](finance/accounting/bank/bank_synchronization.html#migration-process-for-users-having-installed-odoo-before-december-2020)
              * FAQ
                * [La sincronizzazione non funziona in tempo reale. È normale?](finance/accounting/bank/bank_synchronization.html#the-synchronization-is-not-working-in-real-time-is-that-normal)
                * [La funzione di sincronizzazione bancaria online è inclusa nel mio contratto?](finance/accounting/bank/bank_synchronization.html#is-the-online-bank-synchronization-feature-included-in-my-contract)
                * [Alcune banche hanno uno status “Beta”. Che cosa significa?](finance/accounting/bank/bank_synchronization.html#some-banks-have-a-status-beta-what-does-this-mean)
                * [Perché le mie transazioni si sincronizzano solo quando le aggiorno manualmente?](finance/accounting/bank/bank_synchronization.html#why-do-my-transactions-only-synchronize-when-i-refresh-manually)
                * [Non tutte le mie transazioni passate sono presenti in Odoo, perché?](finance/accounting/bank/bank_synchronization.html#not-all-of-my-past-transactions-are-in-odoo-why)
                * [Perché non vedo alcuna transazione?](finance/accounting/bank/bank_synchronization.html#why-don-t-i-see-any-transactions)
                * Come posso aggiornare le mie credenziali bancarie?
                  * Salt Edge
                    * Configurazione
                      * [Collegamento dei conti bancari con Odoo](finance/accounting/bank/bank_synchronization/saltedge.html#link-your-bank-accounts-with-odoo)
                      * [Aggiornare le credenziali](finance/accounting/bank/bank_synchronization/saltedge.html#update-your-credentials)
                      * [Recupera nuovi account](finance/accounting/bank/bank_synchronization/saltedge.html#fetch-new-accounts)
                    * FAQ
                      * [Errore durante l’eliminazione della sincronizzazione con Odoo](finance/accounting/bank/bank_synchronization/saltedge.html#i-have-an-error-when-i-try-to-delete-my-synchronization-within-odoo)
                      * [Errore conto già sincronizzato](finance/accounting/bank/bank_synchronization/saltedge.html#i-have-an-error-saying-that-i-have-already-synchronized-this-account)
                  * Ponto
                    * Configurazione
                      * [Collega i tuoi conti bancari con Ponto](finance/accounting/bank/bank_synchronization/ponto.html#link-your-bank-accounts-with-ponto)
                      * [Collega il tuo account Ponto con il tuo database Odoo](finance/accounting/bank/bank_synchronization/ponto.html#link-your-ponto-account-with-your-odoo-database)
                      * [Aggiorna le tue credenziali di sincronizzazione](finance/accounting/bank/bank_synchronization/ponto.html#update-your-synchronization-credentials)
                      * [Recupera nuovi account](finance/accounting/bank/bank_synchronization/ponto.html#fetch-new-accounts)
                    * FAQ
                      * [Dopo la mia sincronizzazione, non appare alcun account](finance/accounting/bank/bank_synchronization/ponto.html#after-my-synchronization-no-account-appears)
                      * [Ho un errore che indica che la mia autorizzazione è scaduta.](finance/accounting/bank/bank_synchronization/ponto.html#i-have-an-error-about-that-my-authorization-has-expired)
                      * [Ho alcuni errori con la mia istituzione beta](finance/accounting/bank/bank_synchronization/ponto.html#i-have-some-errors-with-my-beta-institution)
                  * Abilitare la Banca
                    * Configurazione
                      * [Collegare i conti bancari con Odoo](finance/accounting/bank/bank_synchronization/enablebanking.html#link-bank-accounts-with-odoo)
            * Transazioni
              * [Importare transazioni](finance/accounting/bank/transactions.html#import-transactions)
              * [Registrare transazioni bancarie manualmente](finance/accounting/bank/transactions.html#register-bank-transactions-manually)
              * Estratti conto
                * [Creare estratti conto dalla vista kanban](finance/accounting/bank/transactions.html#statement-creation-from-the-kanban-view)
                * [Creare estratti conto dalla vista elenco](finance/accounting/bank/transactions.html#statement-creation-from-the-list-view)
                * [Visualizzare, modificare e stampare gli estratti conto](finance/accounting/bank/transactions.html#statement-viewing-editing-and-printing)
            * Riconciliazione bancaria
              * [Visualizzazione riconciliazione bancaria](finance/accounting/bank/reconciliation.html#bank-reconciliation-view)
              * Riconciliare le transazioni
                * [Abbinare registrazioni esistenti](finance/accounting/bank/reconciliation.html#match-existing-entries)
                * [Pagamenti raggruppati](finance/accounting/bank/reconciliation.html#batch-payments)
                * [Operazioni manuali](finance/accounting/bank/reconciliation.html#manual-operations)
                * [Pulsanti modelli di riconciliazione](finance/accounting/bank/reconciliation.html#reconciliation-model-buttons)
            * Modelli di riconciliazione
              * [Tipi di modelli di riconciliazione](finance/accounting/bank/reconciliation_models.html#reconciliation-model-types)
              * Modelli di riconciliazione predefiniti
                * [Corrispondenza perfetta fatture clienti/fornitori](finance/accounting/bank/reconciliation_models.html#invoices-bills-perfect-match)
                * [Corrispondenza parziale fatture clienti/fornitori se sottopagate](finance/accounting/bank/reconciliation_models.html#invoices-bills-partial-match-if-underpaid)
                * [Riga commissioni bancarie](finance/accounting/bank/reconciliation_models.html#line-with-bank-fees)
              * [Mappatura partner](finance/accounting/bank/reconciliation_models.html#partner-mapping)
            * Gestire un conto bancario in una valuta straniera
              * Configurazione
                * [Attivare più valute](finance/accounting/bank/foreign_currency.html#activate-multi-currencies)
                * [Configurare valute](finance/accounting/bank/foreign_currency.html#configure-currencies)
                * [Crea un nuovo conto bancario](finance/accounting/bank/foreign_currency.html#create-a-new-bank-account)
              * [Fatture fornitore in valuta estera](finance/accounting/bank/foreign_currency.html#vendor-bill-in-a-foreign-currency)
              * [Resoconto utili/perdite sui cambi non realizzati](finance/accounting/bank/foreign_currency.html#unrealized-currency-gains-losses-report)
      * [Rendiconto](finance/accounting/reporting.html)
        * [Stato patrimoniale](finance/accounting/reporting.html#balance-sheet)
        * [Conto economico](finance/accounting/reporting.html#profit-and-loss)
        * [Sintesi esecutiva](finance/accounting/reporting.html#executive-summary)
        * [Libro mastro](finance/accounting/reporting.html#general-ledger)
        * [Crediti esigibili](finance/accounting/reporting.html#aged-receivable)
        * [Debiti scaduti](finance/accounting/reporting.html#aged-payable)
        * [Rendiconto finanziario](finance/accounting/reporting.html#cash-flow-statement)
        * Resoconto fiscale
          * Tax return (VAT declaration)
            * Prerequisiti
              * [Periodicità dichiarazione fiscale](finance/accounting/reporting/tax_returns.html#tax-return-periodicity)
              * [Griglie imposta](finance/accounting/reporting/tax_returns.html#tax-grids)
            * Close a tax period
              * [Data chiusura fiscale](finance/accounting/reporting/tax_returns.html#tax-lock-date)
              * [Resoconto fiscale](finance/accounting/reporting/tax_returns.html#tax-report)
          * [Tax carryover](finance/accounting/reporting/tax_carryover.html)
          * Contabilità analitica
            * [Configurazione](finance/accounting/reporting/analytic_accounting.html#configuration)
            * [Analytic accounts](finance/accounting/reporting/analytic_accounting.html#analytic-accounts)
            * [Analytic plans](finance/accounting/reporting/analytic_accounting.html#analytic-plans)
            * Analytic distribution
              * [Analytic distribution models](finance/accounting/reporting/analytic_accounting.html#analytic-distribution-models)
          * Analytic budgets
            * Configurazione
              * [Budgetary positions](finance/accounting/reporting/budget.html#budgetary-positions)
            * Caso d’uso
              * [Analytical accounts](finance/accounting/reporting/budget.html#analytical-accounts)
              * [Define the budget](finance/accounting/reporting/budget.html#define-the-budget)
              * [Check your budget](finance/accounting/reporting/budget.html#check-your-budget)
          * Intrastat
            * General configuration
              * [Default transaction codes: invoice and refund](finance/accounting/reporting/intrastat.html#default-transaction-codes-invoice-and-refund)
              * [Region code](finance/accounting/reporting/intrastat.html#region-code)
            * Configurazione prodotto
              * [Codice merce](finance/accounting/reporting/intrastat.html#commodity-code)
              * [Quantity: weight and supplementary unit](finance/accounting/reporting/intrastat.html#quantity-weight-and-supplementary-unit)
              * [Country of origin](finance/accounting/reporting/intrastat.html#country-of-origin)
            * Invoices and bills configuration
              * [Transaction code](finance/accounting/reporting/intrastat.html#transaction-code)
              * [Partner country](finance/accounting/reporting/intrastat.html#partner-country)
              * [Transport code](finance/accounting/reporting/intrastat.html#transport-code)
              * [Value of the goods](finance/accounting/reporting/intrastat.html#value-of-the-goods)
            * [Partner configuration](finance/accounting/reporting/intrastat.html#partner-configuration)
            * [Generate the Intrastat report](finance/accounting/reporting/intrastat.html#generate-the-intrastat-report)
          * Data inalterability check report
            * [Lock posted entries with hash](finance/accounting/reporting/data_inalterability.html#lock-posted-entries-with-hash)
            * [Report download](finance/accounting/reporting/data_inalterability.html#report-download)
          * Silverfin integration
            * Configurazione
              * Odoo API key
                * [Per database](finance/accounting/reporting/silverfin.html#per-database)
                * [For all databases (fiduciaries)](finance/accounting/reporting/silverfin.html#for-all-databases-fiduciaries)
          * Custom reports
            * [Root reports](finance/accounting/reporting/customize.html#root-reports)
            * [Varianti](finance/accounting/reporting/customize.html#variants)
            * [Righe](finance/accounting/reporting/customize.html#lines)
            * Espressioni
              * [“Odoo Domain” engine](finance/accounting/reporting/customize.html#odoo-domain-engine)
              * [“Tax Tags” engine](finance/accounting/reporting/customize.html#tax-tags-engine)
              * [“Aggregate Other Formulas” engine](finance/accounting/reporting/customize.html#aggregate-other-formulas-engine)
              * [“Prefix of Account Codes” engine](finance/accounting/reporting/customize.html#prefix-of-account-codes-engine)
              * [“External Value” engine](finance/accounting/reporting/customize.html#external-value-engine)
              * [“Custom Python Function” engine](finance/accounting/reporting/customize.html#custom-python-function-engine)
            * [Colonne](finance/accounting/reporting/customize.html#columns)
          * Year-end closing
            * [Anni fiscali](finance/accounting/reporting/year_end.html#fiscal-years)
            * Year-end checklist
              * [Before closure](finance/accounting/reporting/year_end.html#before-closure)
              * Closing a fiscal year
                * [Current year’s earnings](finance/accounting/reporting/year_end.html#current-year-s-earnings)
  * [Costi](finance/expenses.html)
    * Set expense categories
      * Approve expenses
        * [View expense reports](finance/expenses/approve_expenses.html#view-expense-reports)
        * Approve expense reports
          * [Approve individual reports](finance/expenses/approve_expenses.html#approve-individual-reports)
          * [Approve multiple reports](finance/expenses/approve_expenses.html#approve-multiple-reports)
        * [Refuse expense reports](finance/expenses/approve_expenses.html#refuse-expense-reports)
      * Log expenses
        * Manually enter expenses
          * [Attach receipts](finance/expenses/log_expenses.html#attach-receipts)
        * Upload expenses
          * [Digitalization settings](finance/expenses/log_expenses.html#digitalization-settings)
          * [Upload receipts](finance/expenses/log_expenses.html#upload-receipts)
        * [Email expenses](finance/expenses/log_expenses.html#email-expenses)
      * Expense reports
        * [Create expense reports](finance/expenses/expense_reports.html#create-expense-reports)
        * [Submit expense reports](finance/expenses/expense_reports.html#submit-expense-reports)
      * Registra spese
        * [Post individual reports](finance/expenses/post_expenses.html#post-individual-reports)
        * [Post multiple reports](finance/expenses/post_expenses.html#post-multiple-reports)
      * Reimburse employees
        * [Impostazioni](finance/expenses/reimburse.html#settings)
        * [Reimburse individually](finance/expenses/reimburse.html#reimburse-individually)
        * [Reimburse in bulk](finance/expenses/reimburse.html#reimburse-in-bulk)
        * [Report in next payslip](finance/expenses/reimburse.html#report-in-next-payslip)
      * Re-invoice expenses
        * [Imposta](finance/expenses/reinvoice_expenses.html#setup)
        * [Create an expense](finance/expenses/reinvoice_expenses.html#create-an-expense)
        * [Create an expense report](finance/expenses/reinvoice_expenses.html#create-an-expense-report)
        * [Approve and post expenses](finance/expenses/reinvoice_expenses.html#approve-and-post-expenses)
        * [Fatturare le spese](finance/expenses/reinvoice_expenses.html#invoice-expenses)
  * [Online payments](finance/payment_providers.html)
    * Wire transfers
      * [Configurazione](finance/payment_providers/wire_transfer.html#configuration)
    * Addebito Diretto SEPA
      * [Online payments with SDD](finance/payment_providers/sdd.html#online-payments-with-sdd)
    * Adyen
      * Configurazione
        * Credentials tab
          * [API Key and Client Key](finance/payment_providers/adyen.html#api-key-and-client-key)
          * [HMAC key](finance/payment_providers/adyen.html#hmac-key)
          * [API URLs](finance/payment_providers/adyen.html#api-urls)
        * Conto Adyen
          * [Allow payments from a specific origin](finance/payment_providers/adyen.html#allow-payments-from-a-specific-origin)
        * [Place a hold on a card](finance/payment_providers/adyen.html#place-a-hold-on-a-card)
    * Alipay
      * Configurazione
        * [Credentials tab](finance/payment_providers/alipay.html#credentials-tab)
    * Servizi di pagamento Amazon
      * [Configuration on APS Dashboard](finance/payment_providers/amazon_payment_services.html#configuration-on-aps-dashboard)
      * [Configuration on Odoo](finance/payment_providers/amazon_payment_services.html#configuration-on-odoo)
    * AsiaPay
      * [Configuration on AsiaPay Dashboard](finance/payment_providers/asiapay.html#configuration-on-asiapay-dashboard)
      * [Configuration on Odoo](finance/payment_providers/asiapay.html#configuration-on-odoo)
    * Authorize.Net
      * Configurazione
        * [Credentials tab](finance/payment_providers/authorize.html#credentials-tab)
        * Configuration tab
          * [Place a hold on a card](finance/payment_providers/authorize.html#place-a-hold-on-a-card)
      * ACH payments (USA only)
        * [Configurazione](finance/payment_providers/authorize.html#id2)
      * Import an Authorize.Net statement
        * [Export from Authorize.Net](finance/payment_providers/authorize.html#export-from-authorize-net)
        * [Import into Odoo](finance/payment_providers/authorize.html#import-into-odoo)
    * Buckaroo
      * [Configuration on Buckaroo Plaza](finance/payment_providers/buckaroo.html#configuration-on-buckaroo-plaza)
      * [Configuration on Odoo](finance/payment_providers/buckaroo.html#configuration-on-odoo)
    * Demo
      * [Configurazione](finance/payment_providers/demo.html#configuration)
      * [Payment outcome](finance/payment_providers/demo.html#payment-outcome)
      * [Transaction state](finance/payment_providers/demo.html#transaction-state)
    * Flutterwave
      * [Configuration on Flutterwave Dashboard](finance/payment_providers/flutterwave.html#configuration-on-flutterwave-dashboard)
      * [Configuration on Odoo](finance/payment_providers/flutterwave.html#configuration-on-odoo)
    * Mercado Pago
      * [Configuration on Mercado Pago Dashboard](finance/payment_providers/mercado_pago.html#configuration-on-mercado-pago-dashboard)
      * [Configuration on Odoo](finance/payment_providers/mercado_pago.html#configuration-on-odoo)
    * Mollie
      * Configurazione
        * [Credentials tab](finance/payment_providers/mollie.html#credentials-tab)
    * Ogone
      * Settings in Ogone
        * [Create an API user](finance/payment_providers/ogone.html#create-an-api-user)
        * [Set up Ogone for Odoo](finance/payment_providers/ogone.html#set-up-ogone-for-odoo)
      * [Settings in Odoo](finance/payment_providers/ogone.html#settings-in-odoo)
    * PayPal
      * Settings in PayPal
        * [Auto Return](finance/payment_providers/paypal.html#auto-return)
        * [Payment Data Transfer (PDT)](finance/payment_providers/paypal.html#payment-data-transfer-pdt)
        * [PayPal Account Optional](finance/payment_providers/paypal.html#paypal-account-optional)
        * [Payment Messages Format](finance/payment_providers/paypal.html#payment-messages-format)
      * [Settings in Odoo](finance/payment_providers/paypal.html#settings-in-odoo)
      * Test environment
        * [Configurazione](finance/payment_providers/paypal.html#configuration)
    * Razorpay
      * [Configuration on Razorpay Dashboard](finance/payment_providers/razorpay.html#configuration-on-razorpay-dashboard)
      * [Configuration on Odoo](finance/payment_providers/razorpay.html#configuration-on-odoo)
    * SIPS
      * Configurazione
        * [Credentials tab](finance/payment_providers/sips.html#credentials-tab)
    * Stripe
      * Create your Stripe account with Odoo
        * [Fill in your credentials](finance/payment_providers/stripe.html#fill-in-your-credentials)
        * [Generate a webhook](finance/payment_providers/stripe.html#generate-a-webhook)
      * [Abilita Apple Pay](finance/payment_providers/stripe.html#enable-apple-pay)
    * Xendit
      * [Configuration on the Xendit Dashboard](finance/payment_providers/xendit.html#configuration-on-the-xendit-dashboard)
      * [Configuration on Odoo](finance/payment_providers/xendit.html#configuration-on-odoo)
    * Supported payment providers
      * [Online payment providers](finance/payment_providers.html#online-payment-providers)
      * [Bank payments](finance/payment_providers.html#bank-payments)
    * Enabling a payment provider
      * [Modalità di prova](finance/payment_providers.html#test-mode)
    * Metodo di pagamento
      * [Icons and brands](finance/payment_providers.html#icons-and-brands)
      * [Configurazione avanzata](finance/payment_providers.html#advanced-configuration)
    * [Tokenizzazione](finance/payment_providers.html#tokenization)
    * [Manual capture](finance/payment_providers.html#manual-capture)
    * [Rimborsi](finance/payment_providers.html#refunds)
    * [Express checkout](finance/payment_providers.html#express-checkout)
    * Disponibilità
      * [Currencies and countries](finance/payment_providers.html#currencies-and-countries)
      * [Maximum amount](finance/payment_providers.html#maximum-amount)
    * Payment journal
      * [Accounting perspective](finance/payment_providers.html#accounting-perspective)
  * [Fiscal localizations](finance/fiscal_localizations.html)
    * Fiscal localization packages
      * [Configurazione](finance/fiscal_localizations.html#configuration)
      * [Usa](finance/fiscal_localizations.html#use)
    * List of supported countries
      * Argentina
        * [Webinars](finance/fiscal_localizations/argentina.html#webinars)
        * Configurazione
          * [Modules installation](finance/fiscal_localizations/argentina.html#modules-installation)
          * [Configure your company](finance/fiscal_localizations/argentina.html#configure-your-company)
          * [Piano dei conti](finance/fiscal_localizations/argentina.html#chart-of-account)
          * Configure master data
            * Electronic Invoice Credentials
              * [Ambiente](finance/fiscal_localizations/argentina.html#environment)
              * [AFIP certificates](finance/fiscal_localizations/argentina.html#afip-certificates)
            * Partner
              * [Identification type and VAT](finance/fiscal_localizations/argentina.html#identification-type-and-vat)
              * [AFIP responsibility type](finance/fiscal_localizations/argentina.html#afip-responsibility-type)
            * Imposte
              * [Taxes types](finance/fiscal_localizations/argentina.html#taxes-types)
              * [Special taxes](finance/fiscal_localizations/argentina.html#special-taxes)
            * Document types
              * [Lettere](finance/fiscal_localizations/argentina.html#letters)
              * [Use on invoices](finance/fiscal_localizations/argentina.html#use-on-invoices)
          * Registri
            * AFIP information (also known as AFIP Point of Sale)
              * [Web services](finance/fiscal_localizations/argentina.html#web-services)
            * [Sequenze](finance/fiscal_localizations/argentina.html#sequences)
        * Usage and testing
          * Fattura
            * [Document type assignation](finance/fiscal_localizations/argentina.html#document-type-assignation)
            * [Electronic invoice elements](finance/fiscal_localizations/argentina.html#electronic-invoice-elements)
            * [Invoice taxes](finance/fiscal_localizations/argentina.html#invoice-taxes)
            * Special use cases
              * [Invoices for services](finance/fiscal_localizations/argentina.html#invoices-for-services)
              * [Exportation invoices](finance/fiscal_localizations/argentina.html#exportation-invoices)
              * [Fiscal bond](finance/fiscal_localizations/argentina.html#fiscal-bond)
              * [Electronic credit invoice MiPyme (FCE)](finance/fiscal_localizations/argentina.html#electronic-credit-invoice-mipyme-fce)
            * [Invoice printed report](finance/fiscal_localizations/argentina.html#invoice-printed-report)
            * [Troubleshooting and auditing](finance/fiscal_localizations/argentina.html#troubleshooting-and-auditing)
          * Fatture fornitore
            * Validate vendor bill number in AFIP
              * [Validate vendor bills in Odoo](finance/fiscal_localizations/argentina.html#validate-vendor-bills-in-odoo)
            * Special use cases
              * [Untaxed concepts](finance/fiscal_localizations/argentina.html#untaxed-concepts)
              * [Perception taxes](finance/fiscal_localizations/argentina.html#perception-taxes)
          * Check management
            * Own checks
              * [Management of own checks](finance/fiscal_localizations/argentina.html#management-of-own-checks)
              * [Cancel an own check](finance/fiscal_localizations/argentina.html#cancel-an-own-check)
            * Third party checks
              * [New third party checks](finance/fiscal_localizations/argentina.html#new-third-party-checks)
              * [Existing third party checks](finance/fiscal_localizations/argentina.html#existing-third-party-checks)
          * Ecommerce electronic invoicing
            * Configurazione
              * [Client account registration](finance/fiscal_localizations/argentina.html#client-account-registration)
              * [Automatic invoice](finance/fiscal_localizations/argentina.html#automatic-invoice)
              * [Prodotti](finance/fiscal_localizations/argentina.html#products)
            * [Invoicing flow for eCommerce](finance/fiscal_localizations/argentina.html#invoicing-flow-for-ecommerce)
          * Liquidity product direct sales
            * Configurazione
              * [Purchase journal](finance/fiscal_localizations/argentina.html#purchase-journal)
              * [Sales journal](finance/fiscal_localizations/argentina.html#sales-journal)
            * [Invoicing flow](finance/fiscal_localizations/argentina.html#invoicing-flow)
        * Report
          * [VAT summary](finance/fiscal_localizations/argentina.html#vat-summary)
          * [IIBB - Sales by jurisdiction](finance/fiscal_localizations/argentina.html#iibb-sales-by-jurisdiction)
          * [IIBB - Purchases by jurisdiction](finance/fiscal_localizations/argentina.html#iibb-purchases-by-jurisdiction)
      * Australia
        * [Configurazione](finance/fiscal_localizations/australia.html#configuration)
        * [Piano dei conti](finance/fiscal_localizations/australia.html#chart-of-accounts)
        * Taxes and GST
          * [Mappatura imposta](finance/fiscal_localizations/australia.html#tax-mapping)
        * BAS report
          * [Chiusura del report BAS](finance/fiscal_localizations/australia.html#closing-the-bas-report)
        * Rapporto TPAR
          * [Configurazione](finance/fiscal_localizations/australia.html#id1)
        * [Customer statements](finance/fiscal_localizations/australia.html#customer-statements)
        * [Remittance advice](finance/fiscal_localizations/australia.html#remittance-advice)
        * [E-Invoicing via Peppol](finance/fiscal_localizations/australia.html#e-invoicing-via-peppol)
        * ABA files for batch payments
          * [Introduzione](finance/fiscal_localizations/australia.html#introduction)
          * Configurazione
            * [Impostazioni](finance/fiscal_localizations/australia.html#settings)
            * [Bank journal](finance/fiscal_localizations/australia.html#bank-journal)
            * [Partners’ bank accounts](finance/fiscal_localizations/australia.html#partners-bank-accounts)
          * [Generate an ABA file](finance/fiscal_localizations/australia.html#generate-an-aba-file)
        * [Buy Now, Pay Later solutions](finance/fiscal_localizations/australia.html#buy-now-pay-later-solutions)
        * [POS terminals for Australia](finance/fiscal_localizations/australia.html#pos-terminals-for-australia)
        * Libro paga
          * [Create your employees](finance/fiscal_localizations/australia.html#create-your-employees)
          * [Manage Australian contracts](finance/fiscal_localizations/australia.html#manage-australian-contracts)
          * [Assign superannuation accounts](finance/fiscal_localizations/australia.html#assign-superannuation-accounts)
          * Create pay runs with payslips
            * [Create a batch of payslips](finance/fiscal_localizations/australia.html#create-a-batch-of-payslips)
            * [Create an individual payslip](finance/fiscal_localizations/australia.html#create-an-individual-payslip)
            * [Understand payslip features](finance/fiscal_localizations/australia.html#understand-payslip-features)
          * Pay employees
            * One-time payments
              * [Return-to-Work payments](finance/fiscal_localizations/australia.html#return-to-work-payments)
              * [Termination payments](finance/fiscal_localizations/australia.html#termination-payments)
        * Retribuzione australiana con Employment Hero
          * [Configurazione](finance/fiscal_localizations/australia.html#id3)
          * [How does the API work?](finance/fiscal_localizations/australia.html#how-does-the-api-work)
      * Austria
        * [Configurazione](finance/fiscal_localizations/austria.html#configuration)
        * [Rapporti finanziari](finance/fiscal_localizations/austria.html#financial-reports)
        * SAF-T (Standard Audit File for Tax)
          * Configurazione
            * Informazioni aziendali
              * [Contact person](finance/fiscal_localizations/austria.html#contact-person)
            * [Customer and supplier information](finance/fiscal_localizations/austria.html#customer-and-supplier-information)
            * [Accounting settings](finance/fiscal_localizations/austria.html#accounting-settings)
            * [Chart of accounts mapping](finance/fiscal_localizations/austria.html#chart-of-accounts-mapping)
          * [Exporting the SAF-T report](finance/fiscal_localizations/austria.html#exporting-the-saf-t-report)
      * Belgio
        * [Configurazione](finance/fiscal_localizations/belgium.html#configuration)
        * [Piano dei conti](finance/fiscal_localizations/belgium.html#chart-of-accounts)
        * Imposte
          * [Non-deductible taxes](finance/fiscal_localizations/belgium.html#non-deductible-taxes)
        * Report
          * Disallowed expenses report
            * [Restaurant expenses](finance/fiscal_localizations/belgium.html#restaurant-expenses)
            * [Car expenses: vehicle split](finance/fiscal_localizations/belgium.html#car-expenses-vehicle-split)
        * Fee form 281.50 and form 325
          * [Fee form 281.50](finance/fiscal_localizations/belgium.html#fee-form-281-50)
          * [Form 325](finance/fiscal_localizations/belgium.html#form-325)
        * CODA and SODA statements
          * [CODA](finance/fiscal_localizations/belgium.html#coda)
          * [SODA](finance/fiscal_localizations/belgium.html#soda)
          * CodaBox
            * Configurazione
              * [Configure the Connection](finance/fiscal_localizations/belgium.html#configure-the-connection)
              * [Configure the journals](finance/fiscal_localizations/belgium.html#configure-the-journals)
            * [Sincronizzazione](finance/fiscal_localizations/belgium.html#synchronization)
            * [Potenziali problemi](finance/fiscal_localizations/belgium.html#potential-issues)
        * [Fatturazione elettronica](finance/fiscal_localizations/belgium.html#electronic-invoicing)
        * [Cash discount](finance/fiscal_localizations/belgium.html#cash-discount)
        * Fiscal certification: POS restaurant
          * [Certified POS system](finance/fiscal_localizations/belgium.html#certified-pos-system)
          * Fiscal Data Module (FDM)
            * Configurazione
              * [Black box module](finance/fiscal_localizations/belgium.html#black-box-module)
              * [Box IoT](finance/fiscal_localizations/belgium.html#iot-box)
          * [VAT signing card](finance/fiscal_localizations/belgium.html#vat-signing-card)
      * Brasile
        * [Introduzione](finance/fiscal_localizations/brazil.html#introduction)
        * Configurazione
          * [Modules installation](finance/fiscal_localizations/brazil.html#modules-installation)
          * [Configure your company](finance/fiscal_localizations/brazil.html#configure-your-company)
          * Configure AvaTax integration
            * [Credential configuration](finance/fiscal_localizations/brazil.html#credential-configuration)
            * [A1 certificate upload](finance/fiscal_localizations/brazil.html#a1-certificate-upload)
          * Configure master data
            * [Piano dei conti](finance/fiscal_localizations/brazil.html#chart-of-accounts)
            * [Registri](finance/fiscal_localizations/brazil.html#journals)
            * [Imposte](finance/fiscal_localizations/brazil.html#taxes)
            * Prodotti
              * [E-Invoice for goods (NF-e)](finance/fiscal_localizations/brazil.html#e-invoice-for-goods-nf-e)
              * [E-Invoice for services (NFS-e)](finance/fiscal_localizations/brazil.html#e-invoice-for-services-nfs-e)
            * [Contatti](finance/fiscal_localizations/brazil.html#contacts)
            * [Fiscal positions](finance/fiscal_localizations/brazil.html#fiscal-positions)
        * Workflow
          * Calcolare le imposte
            * [Tax calculations on quotations and sales orders](finance/fiscal_localizations/brazil.html#tax-calculations-on-quotations-and-sales-orders)
            * [Tax calculations on invoices](finance/fiscal_localizations/brazil.html#tax-calculations-on-invoices)
          * Electronic documents
            * [Fatture cliente](finance/fiscal_localizations/brazil.html#customer-invoices)
            * [Credit notes](finance/fiscal_localizations/brazil.html#credit-notes)
            * [Note di debito](finance/fiscal_localizations/brazil.html#debit-notes)
            * Invoice cancellation
              * [E-invoices for goods (NF-e)](finance/fiscal_localizations/brazil.html#e-invoices-for-goods-nf-e)
              * [E-invoices for services (NFS-e)](finance/fiscal_localizations/brazil.html#e-invoices-for-services-nfs-e)
            * [Correction letter](finance/fiscal_localizations/brazil.html#correction-letter)
            * [Invalidate invoice number range](finance/fiscal_localizations/brazil.html#invalidate-invoice-number-range)
          * [Fatture fornitore](finance/fiscal_localizations/brazil.html#vendor-bills)
      * Canada
        * Configurazione
          * [Modules installation](finance/fiscal_localizations/canada.html#modules-installation)
        * [Piano dei conti](finance/fiscal_localizations/canada.html#chart-of-accounts)
        * [Fiscal positions](finance/fiscal_localizations/canada.html#fiscal-positions)
        * Imposte
          * [AvaTax](finance/fiscal_localizations/canada.html#avatax)
        * [Report](finance/fiscal_localizations/canada.html#reports)
        * [Cash discount](finance/fiscal_localizations/canada.html#cash-discount)
        * [Writing checks](finance/fiscal_localizations/canada.html#writing-checks)
        * [Receive pre-authorized debits](finance/fiscal_localizations/canada.html#receive-pre-authorized-debits)
      * Cile
        * [Moduli](finance/fiscal_localizations/chile.html#modules)
        * [Informazioni aziendali](finance/fiscal_localizations/chile.html#company-information)
        * Accounting settings
          * [Fiscal information](finance/fiscal_localizations/chile.html#fiscal-information)
          * [Electronic invoice data](finance/fiscal_localizations/chile.html#electronic-invoice-data)
        * DTE incoming email server
          * [Certificato](finance/fiscal_localizations/chile.html#certificate)
        * [Multicurrency](finance/fiscal_localizations/chile.html#multicurrency)
        * [Partner information](finance/fiscal_localizations/chile.html#partner-information)
        * Document types
          * [Use on invoices](finance/fiscal_localizations/chile.html#use-on-invoices)
        * Registri
          * [Create a sales journal](finance/fiscal_localizations/chile.html#create-a-sales-journal)
        * CAF
          * [Upload CAF files](finance/fiscal_localizations/chile.html#upload-caf-files)
        * [Piano dei conti](finance/fiscal_localizations/chile.html#chart-of-accounts)
        * [Imposte](finance/fiscal_localizations/chile.html#taxes)
        * Usage and testing
          * [Electronic invoice workflow](finance/fiscal_localizations/chile.html#electronic-invoice-workflow)
          * Customer invoice emission
            * [Validation and DTE status](finance/fiscal_localizations/chile.html#validation-and-dte-status)
            * [Crossed references](finance/fiscal_localizations/chile.html#crossed-references)
            * [Invoice PDF report](finance/fiscal_localizations/chile.html#invoice-pdf-report)
            * [Commercial validation](finance/fiscal_localizations/chile.html#commercial-validation)
            * [Processed for claimed invoices](finance/fiscal_localizations/chile.html#processed-for-claimed-invoices)
            * [Common errors](finance/fiscal_localizations/chile.html#common-errors)
          * Credit notes
            * Casi d’uso
              * [Cancel referenced document](finance/fiscal_localizations/chile.html#cancel-referenced-document)
              * [Correct referenced document](finance/fiscal_localizations/chile.html#correct-referenced-document)
              * [Corrects referenced document amount](finance/fiscal_localizations/chile.html#corrects-referenced-document-amount)
          * Debit notes
            * Casi d’uso
              * [Add debt on invoices](finance/fiscal_localizations/chile.html#add-debt-on-invoices)
              * [Cancel credit notes](finance/fiscal_localizations/chile.html#cancel-credit-notes)
          * Fatture fornitore
            * [Reception](finance/fiscal_localizations/chile.html#reception)
            * [Acceptation](finance/fiscal_localizations/chile.html#acceptation)
            * [Richiedi](finance/fiscal_localizations/chile.html#claim)
          * Electronic purchase invoice
            * [Configurazione](finance/fiscal_localizations/chile.html#configuration)
            * [Generate an electronic purchase invoice](finance/fiscal_localizations/chile.html#generate-an-electronic-purchase-invoice)
          * Delivery guide
            * [Delivery guide from a sales process](finance/fiscal_localizations/chile.html#delivery-guide-from-a-sales-process)
          * Electronic receipt
            * [Validation and DTE status](finance/fiscal_localizations/chile.html#id2)
          * Electronic export of goods
            * [Contact configurations](finance/fiscal_localizations/chile.html#contact-configurations)
            * [Chilean customs](finance/fiscal_localizations/chile.html#chilean-customs)
            * [PDF report](finance/fiscal_localizations/chile.html#pdf-report)
          * eCommerce electronic invoicing
            * [Invoicing flows](finance/fiscal_localizations/chile.html#invoicing-flows)
          * Point of Sale electronic invoicing
            * Invoicing flows
              * [Electronic receipts: anonymous end user](finance/fiscal_localizations/chile.html#electronic-receipts-anonymous-end-user)
              * [Electronic receipts: specific customer](finance/fiscal_localizations/chile.html#electronic-receipts-specific-customer)
              * [Electronic invoices](finance/fiscal_localizations/chile.html#electronic-invoices)
              * [Resi](finance/fiscal_localizations/chile.html#returns)
        * Rapporti finanziari
          * [Balance tributario de 8 columnas](finance/fiscal_localizations/chile.html#balance-tributario-de-8-columnas)
          * [Propuesta F29](finance/fiscal_localizations/chile.html#propuesta-f29)
      * Colombia
        * Configurazione
          * [Modules installation](finance/fiscal_localizations/colombia.html#modules-installation)
          * [Company configuration](finance/fiscal_localizations/colombia.html#company-configuration)
          * [Carjaval credentials configuration](finance/fiscal_localizations/colombia.html#carjaval-credentials-configuration)
          * [Report data configuration](finance/fiscal_localizations/colombia.html#report-data-configuration)
          * Master data configuration
            * Partner
              * [Identification information](finance/fiscal_localizations/colombia.html#identification-information)
              * [Fiscal information](finance/fiscal_localizations/colombia.html#fiscal-information)
            * [Prodotti](finance/fiscal_localizations/colombia.html#products)
            * [Imposte](finance/fiscal_localizations/colombia.html#taxes)
            * Sales journals
              * [Sequenza fattura](finance/fiscal_localizations/colombia.html#invoice-sequence)
              * [Purchase journals](finance/fiscal_localizations/colombia.html#purchase-journals)
              * [Piano dei conti](finance/fiscal_localizations/colombia.html#chart-of-accounts)
        * Main workflows
          * Electronic invoices
            * [Creazione fattura](finance/fiscal_localizations/colombia.html#invoice-creation)
            * [Invoice validation](finance/fiscal_localizations/colombia.html#invoice-validation)
            * [Reception of legal XML and PDF](finance/fiscal_localizations/colombia.html#reception-of-legal-xml-and-pdf)
          * [Credit notes](finance/fiscal_localizations/colombia.html#credit-notes)
          * [Debit notes](finance/fiscal_localizations/colombia.html#debit-notes)
          * [Support document for vendor bills](finance/fiscal_localizations/colombia.html#support-document-for-vendor-bills)
          * [Common errors](finance/fiscal_localizations/colombia.html#common-errors)
        * Rapporti finanziari
          * [Certificado de Retención en ICA](finance/fiscal_localizations/colombia.html#certificado-de-retencion-en-ica)
          * [Certificado de Retención en IVA](finance/fiscal_localizations/colombia.html#certificado-de-retencion-en-iva)
          * [Certificado de Retención en la Fuente](finance/fiscal_localizations/colombia.html#certificado-de-retencion-en-la-fuente)
      * Danimarca
        * Compliance with Danish bookkeeping requirements: data retention and integrity
          * [Key requirements of the Danish Bookkeeping Act](finance/fiscal_localizations/denmark.html#key-requirements-of-the-danish-bookkeeping-act)
          * [Odoo compliance measures](finance/fiscal_localizations/denmark.html#odoo-compliance-measures)
          * [Immutable transaction records](finance/fiscal_localizations/denmark.html#immutable-transaction-records)
          * [Secure document storage](finance/fiscal_localizations/denmark.html#secure-document-storage)
          * [Continuous data availability](finance/fiscal_localizations/denmark.html#continuous-data-availability)
          * [Automated data export and secure storage](finance/fiscal_localizations/denmark.html#automated-data-export-and-secure-storage)
          * [Data lifecycle management](finance/fiscal_localizations/denmark.html#data-lifecycle-management)
          * [Decryption](finance/fiscal_localizations/denmark.html#decryption)
      * Ecuador
        * Introduzione
          * [Glossary](finance/fiscal_localizations/ecuador.html#glossary)
        * Configurazione
          * [Modules installation](finance/fiscal_localizations/ecuador.html#modules-installation)
          * [Configure your company](finance/fiscal_localizations/ecuador.html#configure-your-company)
          * [Electronic documents](finance/fiscal_localizations/ecuador.html#electronic-documents)
          * [VAT withholding](finance/fiscal_localizations/ecuador.html#vat-withholding)
          * [Printer points](finance/fiscal_localizations/ecuador.html#printer-points)
          * [Withholding](finance/fiscal_localizations/ecuador.html#withholding)
          * [Purchase Liquidations](finance/fiscal_localizations/ecuador.html#purchase-liquidations)
          * Configure master data
            * [Piano dei conti](finance/fiscal_localizations/ecuador.html#chart-of-accounts)
            * [Prodotti](finance/fiscal_localizations/ecuador.html#products)
            * [Contatti](finance/fiscal_localizations/ecuador.html#contacts)
            * [Review your taxes](finance/fiscal_localizations/ecuador.html#review-your-taxes)
            * [Review your Document Types](finance/fiscal_localizations/ecuador.html#review-your-document-types)
        * Workflow
          * Sales documents
            * [Fatture cliente](finance/fiscal_localizations/ecuador.html#customer-invoices)
            * [Customer credit note](finance/fiscal_localizations/ecuador.html#customer-credit-note)
            * [Customer debit note](finance/fiscal_localizations/ecuador.html#customer-debit-note)
            * [Customer withholding](finance/fiscal_localizations/ecuador.html#customer-withholding)
          * Purchase Documents
            * [Fattura fornitore](finance/fiscal_localizations/ecuador.html#vendor-bill)
            * [Purchase liquidation](finance/fiscal_localizations/ecuador.html#purchase-liquidation)
            * [Purchase withholding](finance/fiscal_localizations/ecuador.html#purchase-withholding)
          * E-commerce
            * Configurazione
              * [Sito web](finance/fiscal_localizations/ecuador.html#website)
              * Fornitori di pagamento
                * [Metodo di pagamento](finance/fiscal_localizations/ecuador.html#payment-methods)
            * eCommerce workflow
              * [Identification type and number](finance/fiscal_localizations/ecuador.html#identification-type-and-number)
          * Point of Sale electronic invoicing
            * [Payment method configuration](finance/fiscal_localizations/ecuador.html#payment-method-configuration)
            * Invoicing flows
              * [Identification type and number](finance/fiscal_localizations/ecuador.html#id2)
              * [Electronic invoice: anonymous end consumer](finance/fiscal_localizations/ecuador.html#electronic-invoice-anonymous-end-consumer)
              * [Electronic invoice: specific customer](finance/fiscal_localizations/ecuador.html#electronic-invoice-specific-customer)
        * Rapporti finanziari
          * [Report 103](finance/fiscal_localizations/ecuador.html#report-103)
          * [Report 104](finance/fiscal_localizations/ecuador.html#report-104)
          * ATS report
            * Configurazione
              * [Fatture fornitore](finance/fiscal_localizations/ecuador.html#vendor-bills)
              * [Credit and debit notes](finance/fiscal_localizations/ecuador.html#credit-and-debit-notes)
            * [XML generation](finance/fiscal_localizations/ecuador.html#xml-generation)
      * Egitto
        * [Installazione](finance/fiscal_localizations/egypt.html#installation)
        * Egyptian e-invoicing
          * [Register Odoo on your ETA portal](finance/fiscal_localizations/egypt.html#register-odoo-on-your-eta-portal)
          * Configuration on Odoo
            * [ETA codes](finance/fiscal_localizations/egypt.html#eta-codes)
            * [Filiali](finance/fiscal_localizations/egypt.html#branches)
            * [Clienti](finance/fiscal_localizations/egypt.html#customers)
            * [Prodotti](finance/fiscal_localizations/egypt.html#products)
          * USB authentication
            * [Install Odoo as a local proxy on your computer](finance/fiscal_localizations/egypt.html#install-odoo-as-a-local-proxy-on-your-computer)
            * [Configure the USB key](finance/fiscal_localizations/egypt.html#configure-the-usb-key)
      * Francia
        * [Moduli](finance/fiscal_localizations/france.html#modules)
        * Localization overview
          * [Rendiconto](finance/fiscal_localizations/france.html#reporting)
        * Contabilità
          * E-Invoicing
            * Configurazione
              * [Clienti](finance/fiscal_localizations/france.html#customers)
            * [Sending invoices to Chorus Pro](finance/fiscal_localizations/france.html#sending-invoices-to-chorus-pro)
          * FEC - Fichier des Écritures Comptables
            * Improtazione FEC
              * [Formati file](finance/fiscal_localizations/france.html#file-formats)
              * [Fields description and use](finance/fiscal_localizations/france.html#fields-description-and-use)
              * Implementation details
                * [Conti](finance/fiscal_localizations/france.html#accounts)
                * [Code matching](finance/fiscal_localizations/france.html#code-matching)
                * [Reconcilable flag](finance/fiscal_localizations/france.html#reconcilable-flag)
                * [Account type and templates matching](finance/fiscal_localizations/france.html#account-type-and-templates-matching)
                * [Registri](finance/fiscal_localizations/france.html#journals)
                * [Journal type determination](finance/fiscal_localizations/france.html#journal-type-determination)
                * [Contatti](finance/fiscal_localizations/france.html#contacts)
                * [Movimenti](finance/fiscal_localizations/france.html#moves)
                * [Rounding issues](finance/fiscal_localizations/france.html#rounding-issues)
                * [Missing move name](finance/fiscal_localizations/france.html#missing-move-name)
                * [Contact information](finance/fiscal_localizations/france.html#contact-information)
            * [FEC Export](finance/fiscal_localizations/france.html#fec-export)
        * Point of sale
          * VAT anti-fraud certification
            * [Odoo certification](finance/fiscal_localizations/france.html#odoo-certification)
            * Anti-fraud features
              * [Inalterability](finance/fiscal_localizations/france.html#inalterability)
              * [Sicurezza](finance/fiscal_localizations/france.html#security)
              * [Stoccaggio](finance/fiscal_localizations/france.html#storage)
            * [Responsabilità](finance/fiscal_localizations/france.html#responsibilities)
      * Germania
        * [Piano dei conti tedesco](finance/fiscal_localizations/germany.html#german-chart-of-accounts)
        * [German Accounting Reports](finance/fiscal_localizations/germany.html#german-accounting-reports)
        * [Export from Odoo to Datev](finance/fiscal_localizations/germany.html#export-from-odoo-to-datev)
        * Point of Sale in Germany: Technical Security System
          * Configurazione
            * [Modules installation](finance/fiscal_localizations/germany.html#modules-installation)
            * [Register your company at the financial authority](finance/fiscal_localizations/germany.html#register-your-company-at-the-financial-authority)
            * [Create and link a Technical Security System to your PoS](finance/fiscal_localizations/germany.html#create-and-link-a-technical-security-system-to-your-pos)
          * [DSFinV-K](finance/fiscal_localizations/germany.html#dsfinv-k)
        * German Tax Accounting Standards: Odoo’s guide to GoBD Compliance
          * [What do you need to know about GoBD when relying on accounting software?](finance/fiscal_localizations/germany.html#what-do-you-need-to-know-about-gobd-when-relying-on-accounting-software)
          * [What about data security?](finance/fiscal_localizations/germany.html#what-about-data-security)
          * [Responsibility of the software editor](finance/fiscal_localizations/germany.html#responsibility-of-the-software-editor)
          * [How can Odoo help you achieve Compliance?](finance/fiscal_localizations/germany.html#how-can-odoo-help-you-achieve-compliance)
          * [Do you need a GoBD-Export?](finance/fiscal_localizations/germany.html#do-you-need-a-gobd-export)
          * [What is the role and meaning of the compliance certification?](finance/fiscal_localizations/germany.html#what-is-the-role-and-meaning-of-the-compliance-certification)
          * [What happens if you are not compliant?](finance/fiscal_localizations/germany.html#what-happens-if-you-are-not-compliant)
      * Hong Kong
        * [Configurazione](finance/fiscal_localizations/hong_kong.html#configuration)
        * FPS QR codes on invoices
          * [Activate QR codes](finance/fiscal_localizations/hong_kong.html#activate-qr-codes)
          * [FPS bank account configuration](finance/fiscal_localizations/hong_kong.html#fps-bank-account-configuration)
          * [Bank journal configuration](finance/fiscal_localizations/hong_kong.html#bank-journal-configuration)
          * [Issue invoices with FPS QR codes](finance/fiscal_localizations/hong_kong.html#issue-invoices-with-fps-qr-codes)
        * Libro paga
          * [Create employees](finance/fiscal_localizations/hong_kong.html#create-employees)
          * [Manage contracts](finance/fiscal_localizations/hong_kong.html#manage-contracts)
          * Genera buste paga
            * [Batch payslips](finance/fiscal_localizations/hong_kong.html#batch-payslips)
            * [Individual payslips](finance/fiscal_localizations/hong_kong.html#individual-payslips)
          * [Pay employees](finance/fiscal_localizations/hong_kong.html#pay-employees)
          * [Attendances and hourly wage](finance/fiscal_localizations/hong_kong.html#attendances-and-hourly-wage)
          * [Time Off with Payroll](finance/fiscal_localizations/hong_kong.html#time-off-with-payroll)
          * [Understanding 713 Ordinance](finance/fiscal_localizations/hong_kong.html#understanding-713-ordinance)
          * Generate reports
            * [IRD report](finance/fiscal_localizations/hong_kong.html#ird-report)
            * [Manulife MPF sheet](finance/fiscal_localizations/hong_kong.html#manulife-mpf-sheet)
            * [HSBC autopay report](finance/fiscal_localizations/hong_kong.html#hsbc-autopay-report)
      * India
        * [Installazione](finance/fiscal_localizations/india.html#installation)
        * e-Invoice system
          * Imposta
            * [NIC e-Invoice registration](finance/fiscal_localizations/india.html#nic-e-invoice-registration)
            * Configuration in Odoo
              * [Registri](finance/fiscal_localizations/india.html#journals)
          * Flusso di lavoro
            * [Invoice validation](finance/fiscal_localizations/india.html#invoice-validation)
            * [Invoice PDF report](finance/fiscal_localizations/india.html#invoice-pdf-report)
            * [e-Invoice cancellation](finance/fiscal_localizations/india.html#e-invoice-cancellation)
            * [GST e-Invoice verification](finance/fiscal_localizations/india.html#gst-e-invoice-verification)
        * E-Way bill
          * Imposta
            * [API registration on NIC E-Way bill](finance/fiscal_localizations/india.html#api-registration-on-nic-e-way-bill)
            * [Configuration in Odoo](finance/fiscal_localizations/india.html#india-e-waybill-configuration)
          * Flusso di lavoro
            * [Send an E-Way bill](finance/fiscal_localizations/india.html#send-an-e-way-bill)
            * [Invoice validation](finance/fiscal_localizations/india.html#india-invoice-validation-e-way)
            * [Invoice PDF report](finance/fiscal_localizations/india.html#id6)
            * [E-Way bill cancellation](finance/fiscal_localizations/india.html#e-way-bill-cancellation)
          * [E-waybill creation from receipts and delivery orders](finance/fiscal_localizations/india.html#e-waybill-creation-from-receipts-and-delivery-orders)
        * Indian GST Return filing
          * [Enable API access](finance/fiscal_localizations/india.html#enable-api-access)
          * [Indian GST Service In Odoo](finance/fiscal_localizations/india.html#indian-gst-service-in-odoo)
          * File-in GST Return
            * [Send GSTR-1](finance/fiscal_localizations/india.html#send-gstr-1)
            * [Receive GSTR-2B](finance/fiscal_localizations/india.html#receive-gstr-2b)
            * [GSTR-3 report](finance/fiscal_localizations/india.html#gstr-3-report)
        * Tax reports
          * [GSTR-1 report](finance/fiscal_localizations/india.html#gstr-1-report)
          * [GSTR-3 report](finance/fiscal_localizations/india.html#india-gstr-3-report)
      * Indonesia
        * E-Faktur Module
          * [NPWP/NIK settings](finance/fiscal_localizations/indonesia.html#npwp-nik-settings)
          * Utilizzo
            * [Generate Tax Invoice Serial Number](finance/fiscal_localizations/indonesia.html#generate-tax-invoice-serial-number)
            * [Generate e-faktur csv for a single invoice or a batch invoices](finance/fiscal_localizations/indonesia.html#generate-e-faktur-csv-for-a-single-invoice-or-a-batch-invoices)
            * [Kode Transaksi FP (Transaction Code)](finance/fiscal_localizations/indonesia.html#kode-transaksi-fp-transaction-code)
            * [Correct an invoice that has been posted and downloaded: Replace Invoice feature](finance/fiscal_localizations/indonesia.html#correct-an-invoice-that-has-been-posted-and-downloaded-replace-invoice-feature)
            * [Correct an invoice that has been posted but not downloaded yet: Reset e-Faktur](finance/fiscal_localizations/indonesia.html#correct-an-invoice-that-has-been-posted-but-not-downloaded-yet-reset-e-faktur)
      * Italia
        * Configurazione
          * [Informazioni aziendali](finance/fiscal_localizations/italy.html#company-information)
          * Configurazione delle imposte
            * [Esenzione fiscale](finance/fiscal_localizations/italy.html#tax-exemption)
        * Inversione contabile
          * [Fatture](finance/fiscal_localizations/italy.html#invoices)
          * [Fatture fornitore](finance/fiscal_localizations/italy.html#vendor-bills)
          * [Griglie imposte](finance/fiscal_localizations/italy.html#tax-grids)
        * Fatturazione elettronica
          * [Modalità EDI e autorizzazione](finance/fiscal_localizations/italy.html#edi-mode-and-authorization)
          * Elabora
            * [Creazione documenti XML](finance/fiscal_localizations/italy.html#xml-documents-creation)
            * [Invio all’SDI](finance/fiscal_localizations/italy.html#submission-to-sdi)
            * [Elaborazione da parte dell’SDI](finance/fiscal_localizations/italy.html#processing-by-sdi)
            * [Accettazione](finance/fiscal_localizations/italy.html#acceptance)
            * [Eventuale rifiuto](finance/fiscal_localizations/italy.html#possible-rejection)
            * [Invio completato](finance/fiscal_localizations/italy.html#forwarding-completed)
          * [Integrazione imposte](finance/fiscal_localizations/italy.html#tax-integration)
          * Tipi di documento
            * [TD01 - Fatture](finance/fiscal_localizations/italy.html#td01-invoices)
            * [TD02 - Acconto/Anticipo su fattura](finance/fiscal_localizations/italy.html#td02-down-payments)
            * [TD04 - Note di credito](finance/fiscal_localizations/italy.html#td04-credit-notes)
            * [TD07, TD08, TD09 - Fatturazione semplificata](finance/fiscal_localizations/italy.html#td07-td08-td09-simplified-invoicing)
            * [TD16 - Inversione contabile interna](finance/fiscal_localizations/italy.html#td16-internal-reverse-charge)
            * [TD17 - Comprare servizi dall’estero](finance/fiscal_localizations/italy.html#td17-buying-services-from-abroad)
            * [TD18 - Acquistare beni dall’UE](finance/fiscal_localizations/italy.html#td18-buying-goods-from-eu)
            * [TD19 - Acquistare beni dal deposito IVA](finance/fiscal_localizations/italy.html#td19-buying-goods-from-vat-deposit)
            * [TD24 - Fatture differite](finance/fiscal_localizations/italy.html#td24-deferred-invoices)
            * TD28 - San Marino
              * [Fatture](finance/fiscal_localizations/italy.html#id1)
              * [Fatture fornitore](finance/fiscal_localizations/italy.html#id2)
        * Aziende pubblica amministrazione (B2G)
          * [CIG, CUP, Dati ordine d’acquisto](finance/fiscal_localizations/italy.html#cig-cup-datiordineacquisto)
          * [Pagamento frazionato](finance/fiscal_localizations/italy.html#split-payment)
          * Elabora
            * [Firma elettroncia qualificata](finance/fiscal_localizations/italy.html#digital-qualified-signature)
            * [Accettazione o rifiuto](finance/fiscal_localizations/italy.html#acceptance-or-refusal)
            * [Termini di scadenza](finance/fiscal_localizations/italy.html#expired-terms)
        * Ri.Ba. (Ricevuta Bancaria)
          * [Configurazione](finance/fiscal_localizations/italy.html#id4)
          * [Accept Ri.Ba. for your invoices](finance/fiscal_localizations/italy.html#accept-ri-ba-for-your-invoices)
      * Giordania
        * [Moduli](finance/fiscal_localizations/jordan.html#modules)
        * Localization overview
          * [Imposte](finance/fiscal_localizations/jordan.html#taxes)
          * [Tax reporting](finance/fiscal_localizations/jordan.html#tax-reporting)
        * E-invoicing with JoFotara
          * Configurazione
            * [Link Odoo to JoFotara](finance/fiscal_localizations/jordan.html#link-odoo-to-jofotara)
            * [Company and customers](finance/fiscal_localizations/jordan.html#company-and-customers)
          * Sending invoices to JoFotara via Odoo
            * [JoFotara State](finance/fiscal_localizations/jordan.html#jofotara-state)
            * [Validating QR codes (Sanad app)](finance/fiscal_localizations/jordan.html#validating-qr-codes-sanad-app)
            * [Debit and credit notes](finance/fiscal_localizations/jordan.html#debit-and-credit-notes)
            * [Sconti](finance/fiscal_localizations/jordan.html#discounts)
      * Kenya
        * [Configurazione](finance/fiscal_localizations/kenya.html#configuration)
        * eTIMS
          * [OSCU device initialization](finance/fiscal_localizations/kenya.html#oscu-device-initialization)
          * [Registering on eTIMS](finance/fiscal_localizations/kenya.html#registering-on-etims)
          * [eTIMS codes](finance/fiscal_localizations/kenya.html#etims-codes)
          * [UNSPSC codes](finance/fiscal_localizations/kenya.html#unspsc-codes)
          * [Notices](finance/fiscal_localizations/kenya.html#notices)
          * [Multi-azienda](finance/fiscal_localizations/kenya.html#multi-company)
          * [Contact branch ID](finance/fiscal_localizations/kenya.html#contact-branch-id)
          * [KRA sequences](finance/fiscal_localizations/kenya.html#kra-sequences)
        * [Assicurazione](finance/fiscal_localizations/kenya.html#insurance)
        * [Product registration](finance/fiscal_localizations/kenya.html#product-registration)
        * [Stock movements](finance/fiscal_localizations/kenya.html#stock-movements)
        * [Acquisti](finance/fiscal_localizations/kenya.html#purchases)
        * [Fatturazione](finance/fiscal_localizations/kenya.html#invoicing)
        * [Imports](finance/fiscal_localizations/kenya.html#imports)
        * [BOM](finance/fiscal_localizations/kenya.html#bom)
        * [Credit notes](finance/fiscal_localizations/kenya.html#credit-notes)
      * Lussemburgo
        * [Configurazione](finance/fiscal_localizations/luxembourg.html#configuration)
        * [Standard Chart of Accounts - PCN 2020](finance/fiscal_localizations/luxembourg.html#standard-chart-of-accounts-pcn-2020)
        * [eCDF tax return](finance/fiscal_localizations/luxembourg.html#ecdf-tax-return)
        * [Annual tax report](finance/fiscal_localizations/luxembourg.html#annual-tax-report)
        * FAIA (SAF-T)
          * [Export FAIA file](finance/fiscal_localizations/luxembourg.html#export-faia-file)
      * Malesia
        * Configurazione
          * [Modules installation](finance/fiscal_localizations/malaysia.html#modules-installation)
          * [Informazioni aziendali](finance/fiscal_localizations/malaysia.html#company-information)
        * E-invoicing integration with MyInvois
          * Set-up
            * [MyInvois registration](finance/fiscal_localizations/malaysia.html#myinvois-registration)
            * Configuration in Odoo
              * [Fatturazione elettronica](finance/fiscal_localizations/malaysia.html#electronic-invoicing)
              * [Azienda](finance/fiscal_localizations/malaysia.html#company)
              * [Contatti](finance/fiscal_localizations/malaysia.html#contacts)
              * [Prodotti](finance/fiscal_localizations/malaysia.html#products)
          * Flusso di lavoro
            * Send invoices to MyInvois
              * [MyInvois status](finance/fiscal_localizations/malaysia.html#myinvois-status)
            * [Invoice cancellation](finance/fiscal_localizations/malaysia.html#invoice-cancellation)
      * Messico
        * [Webinars](finance/fiscal_localizations/mexico.html#webinars)
        * [Introduzione](finance/fiscal_localizations/mexico.html#introduction)
        * Configurazione
          * [Requisiti](finance/fiscal_localizations/mexico.html#requirements)
          * [Installing modules](finance/fiscal_localizations/mexico.html#installing-modules)
          * [Configure your company](finance/fiscal_localizations/mexico.html#configure-your-company)
          * [Contatti](finance/fiscal_localizations/mexico.html#contacts)
          * Imposte
            * [Factor type](finance/fiscal_localizations/mexico.html#factor-type)
            * [Tax object](finance/fiscal_localizations/mexico.html#tax-object)
            * [Other tax configurations](finance/fiscal_localizations/mexico.html#other-tax-configurations)
          * [Prodotti](finance/fiscal_localizations/mexico.html#products)
          * Fatturazione elettronica
            * [PAC credentials](finance/fiscal_localizations/mexico.html#pac-credentials)
            * [.cer and .key certificates](finance/fiscal_localizations/mexico.html#cer-and-key-certificates)
        * Workflow
          * Fatturazione elettronica
            * [Fatture cliente](finance/fiscal_localizations/mexico.html#customer-invoices)
            * [Credit notes](finance/fiscal_localizations/mexico.html#credit-notes)
            * Payment complements
              * [Payment policy](finance/fiscal_localizations/mexico.html#payment-policy)
              * [Payment flow](finance/fiscal_localizations/mexico.html#payment-flow)
            * Invoice cancellations
              * [Cancellation reason 01 - Invoice issued with errors (with related document)](finance/fiscal_localizations/mexico.html#cancellation-reason-01-invoice-issued-with-errors-with-related-document)
              * [Cancellation reasons 02, 03, and 04](finance/fiscal_localizations/mexico.html#cancellation-reasons-02-03-and-04)
              * [Payment cancellations](finance/fiscal_localizations/mexico.html#payment-cancellations)
            * Invoicing special use cases
              * [CFDI to public](finance/fiscal_localizations/mexico.html#cfdi-to-public)
              * [Multicurrency](finance/fiscal_localizations/mexico.html#multicurrency)
              * [Acconti](finance/fiscal_localizations/mexico.html#down-payments)
          * External trade
            * Configurazione
              * [Contatti](finance/fiscal_localizations/mexico.html#id3)
              * [Prodotti](finance/fiscal_localizations/mexico.html#id4)
            * [Invoicing flow](finance/fiscal_localizations/mexico.html#invoicing-flow)
          * Delivery guide
            * Configurazione
              * [Contacts and vehicles](finance/fiscal_localizations/mexico.html#contacts-and-vehicles)
              * [Prodotti](finance/fiscal_localizations/mexico.html#id6)
            * Sales and inventory flow
              * [Dangerous hazards](finance/fiscal_localizations/mexico.html#dangerous-hazards)
          * Customs numbers
            * [Configurazione](finance/fiscal_localizations/mexico.html#id8)
            * [Purchase and sales flow](finance/fiscal_localizations/mexico.html#purchase-and-sales-flow)
          * Electronic accounting
            * [Piano dei conti](finance/fiscal_localizations/mexico.html#chart-of-accounts)
            * Bilancio di verifica
              * [Month 13 trial balance](finance/fiscal_localizations/mexico.html#month-13-trial-balance)
            * [Contabilità generale](finance/fiscal_localizations/mexico.html#general-ledger)
            * [DIOT report](finance/fiscal_localizations/mexico.html#diot-report)
      * Olanda
        * [XAF Export](finance/fiscal_localizations/netherlands.html#xaf-export)
        * [Dutch Accounting Reports](finance/fiscal_localizations/netherlands.html#dutch-accounting-reports)
      * Romania
        * [Configurazione](finance/fiscal_localizations/romania.html#configuration)
        * D.406 declaration
          * Configurazione
            * [Azienda](finance/fiscal_localizations/romania.html#company)
            * [Piano dei conti](finance/fiscal_localizations/romania.html#chart-of-accounts)
            * [Customer and supplier](finance/fiscal_localizations/romania.html#customer-and-supplier)
            * [Imposta](finance/fiscal_localizations/romania.html#tax)
            * [Prodotto](finance/fiscal_localizations/romania.html#product)
            * [Fattura fornitore](finance/fiscal_localizations/romania.html#vendor-bill)
          * Generating the declaration
            * [Exporting your data](finance/fiscal_localizations/romania.html#exporting-your-data)
            * [Signing the report](finance/fiscal_localizations/romania.html#signing-the-report)
      * Perù
        * [Moduli](finance/fiscal_localizations/peru.html#modules)
        * Configurazione
          * Install the Peruvian localization modules
            * [Configure your company](finance/fiscal_localizations/peru.html#configure-your-company)
            * [Chart of Account](finance/fiscal_localizations/peru.html#chart-of-account)
          * Impostazioni contabili
            * [Basic Concepts](finance/fiscal_localizations/peru.html#basic-concepts)
            * Signature Provider
              * IAP (Odoo In-App Purchase)
                * [What is the IAP?](finance/fiscal_localizations/peru.html#what-is-the-iap)
                * [How does it work?](finance/fiscal_localizations/peru.html#how-does-it-work)
                * [What do you need to do?](finance/fiscal_localizations/peru.html#what-do-you-need-to-do)
              * [Digiflow](finance/fiscal_localizations/peru.html#digiflow)
              * [SUNAT](finance/fiscal_localizations/peru.html#sunat)
            * [Testing environment](finance/fiscal_localizations/peru.html#testing-environment)
            * [Certificato](finance/fiscal_localizations/peru.html#certificate)
            * [Multicurrency](finance/fiscal_localizations/peru.html#multicurrency)
          * Configure Master data
            * Imposte
              * [EDI Configuration](finance/fiscal_localizations/peru.html#edi-configuration)
            * [Posizioni fiscali](finance/fiscal_localizations/peru.html#fiscal-positions)
            * [Tipi di documento](finance/fiscal_localizations/peru.html#document-types)
            * Registri
              * [Usa Documenti](finance/fiscal_localizations/peru.html#use-documents)
              * [Interscambio dati elettronici](finance/fiscal_localizations/peru.html#electronic-data-interchange)
            * Partner
              * [Identification Type and VAT](finance/fiscal_localizations/peru.html#identification-type-and-vat)
            * [Prodotto](finance/fiscal_localizations/peru.html#product)
        * Usage and testing
          * Fattura cliente
            * [EDI Elements](finance/fiscal_localizations/peru.html#edi-elements)
            * Invoice validation
              * [Electronic Invoice Status](finance/fiscal_localizations/peru.html#electronic-invoice-status)
            * [Common Errors](finance/fiscal_localizations/peru.html#common-errors)
            * [Invoice PDF Report](finance/fiscal_localizations/peru.html#invoice-pdf-report)
            * [Crediti acquisti in-app](finance/fiscal_localizations/peru.html#iap-credits)
            * Special Use cases
              * Cancellation process
                * [Electronic Invoice Status](finance/fiscal_localizations/peru.html#id3)
              * [Export invoices](finance/fiscal_localizations/peru.html#export-invoices)
              * [Advance Payments](finance/fiscal_localizations/peru.html#advance-payments)
              * [Detraction Invoices](finance/fiscal_localizations/peru.html#detraction-invoices)
          * [Note di credito](finance/fiscal_localizations/peru.html#credit-notes)
          * [Note di debito](finance/fiscal_localizations/peru.html#debit-notes)
          * Electronic delivery guide 2.0
            * Delivery guide types
              * [Mittente](finance/fiscal_localizations/peru.html#sender)
              * [Corriere](finance/fiscal_localizations/peru.html#carrier)
            * Transportation types
              * [Privato](finance/fiscal_localizations/peru.html#private)
              * [Pubblico](finance/fiscal_localizations/peru.html#public)
            * [Direct submission to SUNAT](finance/fiscal_localizations/peru.html#direct-submission-to-sunat)
            * [Required information](finance/fiscal_localizations/peru.html#required-information)
            * [Cancellations](finance/fiscal_localizations/peru.html#cancellations)
            * [Testing](finance/fiscal_localizations/peru.html#testing)
            * Configurazione
              * [Operatore](finance/fiscal_localizations/peru.html#operator)
              * [Corriere](finance/fiscal_localizations/peru.html#id5)
              * [Veicoli](finance/fiscal_localizations/peru.html#vehicles)
              * [Prodotti](finance/fiscal_localizations/peru.html#products)
            * [Generating a GRE](finance/fiscal_localizations/peru.html#generating-a-gre)
            * [Common errors](finance/fiscal_localizations/peru.html#id6)
          * eCommerce electronic invoicing
            * [Configurazione](finance/fiscal_localizations/peru.html#peru-ecommerce-configuration)
            * [Invoicing flow for eCommerce](finance/fiscal_localizations/peru.html#invoicing-flow-for-ecommerce)
        * Report
          * Permanent inventory reports: PLE 12.1 and PLE 13.1
            * Configurazione
              * [Prodotti](finance/fiscal_localizations/peru.html#peru-reports-ple-products)
              * [Magazzini](finance/fiscal_localizations/peru.html#warehouses)
              * [Inventory transfers](finance/fiscal_localizations/peru.html#inventory-transfers)
            * [Generate a .txt file for permanent inventory Kardex reports](finance/fiscal_localizations/peru.html#generate-a-txt-file-for-permanent-inventory-kardex-reports)
      * Filippine
        * Configurazione
          * [Chart of accounts and taxes](finance/fiscal_localizations/philippines.html#chart-of-accounts-and-taxes)
          * [Contatti](finance/fiscal_localizations/philippines.html#contacts)
        * [BIR 2307 report](finance/fiscal_localizations/philippines.html#bir-2307-report)
        * [SLSP Report](finance/fiscal_localizations/philippines.html#slsp-report)
        * [2550Q Tax report](finance/fiscal_localizations/philippines.html#q-tax-report)
      * Arabia Saudita
        * [Configurazione](finance/fiscal_localizations/saudi_arabia.html#configuration)
        * ZATCA e-invoices
          * [Informazioni aziendali](finance/fiscal_localizations/saudi_arabia.html#company-information)
          * Modalità di simulazione
            * [Fatoora simulation portal](finance/fiscal_localizations/saudi_arabia.html#fatoora-simulation-portal)
            * [ZATCA API integration](finance/fiscal_localizations/saudi_arabia.html#zatca-api-integration)
            * [Sales journals](finance/fiscal_localizations/saudi_arabia.html#sales-journals)
            * [Testing](finance/fiscal_localizations/saudi_arabia.html#testing)
            * [Imposte](finance/fiscal_localizations/saudi_arabia.html#taxes)
          * [Modalità di produzione](finance/fiscal_localizations/saudi_arabia.html#production-mode)
      * Singapore
        * Add PayNow QR codes to invoices
          * [Activate QR codes](finance/fiscal_localizations/singapore.html#activate-qr-codes)
          * [PayNow bank account configuration](finance/fiscal_localizations/singapore.html#paynow-bank-account-configuration)
          * [Bank journal configuration](finance/fiscal_localizations/singapore.html#bank-journal-configuration)
          * [Issue invoices with PayNow QR codes](finance/fiscal_localizations/singapore.html#issue-invoices-with-paynow-qr-codes)
      * Spagna
        * [Configurazione](finance/fiscal_localizations/spain.html#configuration)
        * [Piano dei conti](finance/fiscal_localizations/spain.html#chart-of-accounts)
        * [Imposte](finance/fiscal_localizations/spain.html#taxes)
        * Report
          * Modelo 130
            * [Change the percentage](finance/fiscal_localizations/spain.html#change-the-percentage)
            * [Report agriculture activity](finance/fiscal_localizations/spain.html#report-agriculture-activity)
        * TicketBAI
          * [Caso d’uso](finance/fiscal_localizations/spain.html#use-case)
        * FACe
          * [Caso d’uso](finance/fiscal_localizations/spain.html#id2)
          * [Administrative centers](finance/fiscal_localizations/spain.html#administrative-centers)
      * Svizzera
        * ISR (In-payment Slip with Reference number)
          * [ISR reference on invoices](finance/fiscal_localizations/switzerland.html#isr-reference-on-invoices)
        * [Currency Rate Live Update](finance/fiscal_localizations/switzerland.html#currency-rate-live-update)
        * Updated VAT for January 2018
          * [How to update your taxes in Odoo Enterprise (Odoo Online or On-premise)?](finance/fiscal_localizations/switzerland.html#how-to-update-your-taxes-in-odoo-enterprise-odoo-online-or-on-premise)
      * Thailandia
        * [Configurazione](finance/fiscal_localizations/thailand.html#configuration)
        * [Chart of accounts and taxes](finance/fiscal_localizations/thailand.html#chart-of-accounts-and-taxes)
        * Resoconto FISCALE
          * [Sales and purchase tax report](finance/fiscal_localizations/thailand.html#sales-and-purchase-tax-report)
          * [Withholding PND tax report](finance/fiscal_localizations/thailand.html#withholding-pnd-tax-report)
        * Tax invoice
          * [Headquarter/Branch number settings](finance/fiscal_localizations/thailand.html#headquarter-branch-number-settings)
        * PromptPay QR code on invoices
          * [Activate QR codes](finance/fiscal_localizations/thailand.html#activate-qr-codes)
          * [PromptPay QR bank account configuration](finance/fiscal_localizations/thailand.html#promptpay-qr-bank-account-configuration)
          * [Bank journal configuration](finance/fiscal_localizations/thailand.html#bank-journal-configuration)
          * [Issue invoices with PromptPay QR code](finance/fiscal_localizations/thailand.html#issue-invoices-with-promptpay-qr-code)
      * Vietnam
        * [Moduli](finance/fiscal_localizations/vietnam.html#modules)
        * [Azienda](finance/fiscal_localizations/vietnam.html#company)
        * E-invoicing with SInvoice
          * Configurazione
            * SInvoice platform
              * [SInvoice registration](finance/fiscal_localizations/vietnam.html#sinvoice-registration)
              * [Invoice template creation](finance/fiscal_localizations/vietnam.html#invoice-template-creation)
              * [Invoice symbol creation](finance/fiscal_localizations/vietnam.html#invoice-symbol-creation)
              * [Invoice issuance notice](finance/fiscal_localizations/vietnam.html#invoice-issuance-notice)
            * Odoo database
              * [Link Odoo to SInvoice](finance/fiscal_localizations/vietnam.html#link-odoo-to-sinvoice)
              * [Modello fattura](finance/fiscal_localizations/vietnam.html#invoice-template)
          * Sending invoices to SInvoice
            * [Replacement or adjustment invoices](finance/fiscal_localizations/vietnam.html#replacement-or-adjustment-invoices)
            * [Invoice cancellation](finance/fiscal_localizations/vietnam.html#invoice-cancellation)
        * QR banking codes
          * Configurazione
            * [Conto bancario](finance/fiscal_localizations/vietnam.html#bank-account)
          * [Generating QR codes on invoices](finance/fiscal_localizations/vietnam.html#generating-qr-codes-on-invoices)
      * Emirati Arabi Uniti
        * [Installazione](finance/fiscal_localizations/united_arab_emirates.html#installation)
        * [Piano dei conti](finance/fiscal_localizations/united_arab_emirates.html#chart-of-accounts)
        * [Imposte](finance/fiscal_localizations/united_arab_emirates.html#taxes)
        * [Currency exchange rates](finance/fiscal_localizations/united_arab_emirates.html#currency-exchange-rates)
        * Libro paga
          * [Salary rules](finance/fiscal_localizations/united_arab_emirates.html#salary-rules)
          * [End of service provision](finance/fiscal_localizations/united_arab_emirates.html#end-of-service-provision)
          * [Fatture](finance/fiscal_localizations/united_arab_emirates.html#invoices)
      * Regno Unito
        * [Configurazione](finance/fiscal_localizations/united_kingdom.html#configuration)
        * [Piano dei conti](finance/fiscal_localizations/united_kingdom.html#chart-of-accounts)
        * Imposte
          * Making Tax Digital (MTD)
            * [Register your company to HMRC before the first submission](finance/fiscal_localizations/united_kingdom.html#register-your-company-to-hmrc-before-the-first-submission)
            * [Periodic submission to HMRC](finance/fiscal_localizations/united_kingdom.html#periodic-submission-to-hmrc)
            * [Periodic submission to HMRC for multi-company](finance/fiscal_localizations/united_kingdom.html#periodic-submission-to-hmrc-for-multi-company)
        * Bacs files
          * [Bill payments](finance/fiscal_localizations/united_kingdom.html#bill-payments)
          * [Invoice payments](finance/fiscal_localizations/united_kingdom.html#invoice-payments)
      * Stati Uniti
        * Configurazione
          * [Modules installation](finance/fiscal_localizations/united_states.html#modules-installation)
        * Piano dei conti
          * [View, edit, and sort accounts](finance/fiscal_localizations/united_states.html#view-edit-and-sort-accounts)
        * Imposte
          * [AvaTax](finance/fiscal_localizations/united_states.html#avatax)
        * Report
          * [Rapporto 1099](finance/fiscal_localizations/united_states.html#report)
          * [Rendiconto finanziario](finance/fiscal_localizations/united_states.html#cash-flow-statement)
        * [Cash discount](finance/fiscal_localizations/united_states.html#cash-discount)
        * [Writing checks](finance/fiscal_localizations/united_states.html#writing-checks)
        * Libro paga
          * Required information
            * [Employee records](finance/fiscal_localizations/united_states.html#employee-records)
            * [Employee contracts](finance/fiscal_localizations/united_states.html#employee-contracts)
          * Export work entries to ADP
            * [Requisiti](finance/fiscal_localizations/united_states.html#requirements)
            * [Export data](finance/fiscal_localizations/united_states.html#export-data)
        * ACH - electronic transfers
          * [Receive ACH payments: payment provider integration](finance/fiscal_localizations/united_states.html#receive-ach-payments-payment-provider-integration)
          * Send payments: NACHA files
            * [Configurazione](finance/fiscal_localizations/united_states.html#id1)
            * [Crea pagamento raggruppato](finance/fiscal_localizations/united_states.html#create-batch-payment)
      * Uruguay
        * Introduzione
          * [Glossary](finance/fiscal_localizations/uruguay.html#glossary)
        * Configurazione
          * [Modules installation](finance/fiscal_localizations/uruguay.html#modules-installation)
          * [Azienda](finance/fiscal_localizations/uruguay.html#company)
          * [Set up a Uruware account](finance/fiscal_localizations/uruguay.html#set-up-a-uruware-account)
          * [Electronic invoice data](finance/fiscal_localizations/uruguay.html#electronic-invoice-data)
          * Master data
            * [Piano dei conti](finance/fiscal_localizations/uruguay.html#chart-of-accounts)
            * [Contatti](finance/fiscal_localizations/uruguay.html#contacts)
            * [Imposte](finance/fiscal_localizations/uruguay.html#taxes)
            * [Document types](finance/fiscal_localizations/uruguay.html#document-types)
            * [Sales journals](finance/fiscal_localizations/uruguay.html#sales-journals)
        * Workflow
          * Sales documents
            * [Fatture cliente](finance/fiscal_localizations/uruguay.html#customer-invoices)
            * [Customer credit note](finance/fiscal_localizations/uruguay.html#customer-credit-note)
            * [Customer debit note](finance/fiscal_localizations/uruguay.html#customer-debit-note)
        * Addendas and disclosures
          * [Leyenda and additional information in product](finance/fiscal_localizations/uruguay.html#leyenda-and-additional-information-in-product)
          * [Leyenda and additional information](finance/fiscal_localizations/uruguay.html#leyenda-and-additional-information)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/finance.rst)

### Navigazione

  * [indice](../genindex.html "Indice generale")
  * [moduli](../py-modindex.html "Indice del modulo Python") |
  * [successivo](finance/accounting.html "Contabilità e fatturazione") |
  * [precedente](essentials/keyboard_shortcuts.html "Scelte rapide da tastiera") |
  * [Odoo 17.0 documentazione](../index-2.html) »
  * [Documentazione Utente](../applications.html) »
  * Finanza


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