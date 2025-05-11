# Vendite — Odoo 17.0 documentazione

### Navigazione

  * [indice](../genindex.html "Indice generale")
  * [moduli](../py-modindex.html "Indice del modulo Python") |
  * [successivo](sales/crm.html "CRM") |
  * [precedente](finance/fiscal_localizations/uruguay.html "Uruguay") |
  * [Odoo 17.0 documentazione](../index-2.html) »
  * [Documentazione Utente](../applications.html) »
  * Vendite



# Vendite¶

  * [CRM](sales/crm.html)
    * Organizzare il flusso
      * Gestire le opportunità perse
        * [Contrassegnare un’opportunità come persa](sales/crm/pipeline/lost_opportunities.html#mark-an-opportunity-as-lost)
        * [Creare/modificare motivi perdita](sales/crm/pipeline/lost_opportunities.html#create-edit-lost-reasons)
        * Visualizzare opportunità perse
          * [Organizzare le opportunità per motivo perdita](sales/crm/pipeline/lost_opportunities.html#sort-opportunities-by-lost-reason)
        * Ripristinare le opportunità perse
          * [Ripristinare più opportunità perse in una volta](sales/crm/pipeline/lost_opportunities.html#restore-multiple-opportunities-at-once)
        * Gestire lead persi
          * [Segnare un contatto come perso](sales/crm/pipeline/lost_opportunities.html#mark-a-lead-as-lost)
          * [Ripristinare lead persi](sales/crm/pipeline/lost_opportunities.html#restore-lost-leads)
          * [Ripristinare più lead alla volta](sales/crm/pipeline/lost_opportunities.html#restore-multiple-leads-at-once)
      * Unire lead e opportunità simili
        * Individuare lead e opportunità simili
          * [Confrontare lead e opportunità simili](sales/crm/pipeline/merge_similar.html#comparing-similar-leads-and-opportunities)
        * [Unire lead e opportunità simili](sales/crm/pipeline/merge_similar.html#merging-similar-leads-and-opportunities)
        * Casi in cui non bisogna unire lead/opportunità
          * [Lead persi](sales/crm/pipeline/merge_similar.html#lost-leads)
          * [Contatto diverso nell’organizzazione](sales/crm/pipeline/merge_similar.html#different-contact-within-an-organization)
          * [Duplicati esistenti con più di un addetto vendite](sales/crm/pipeline/merge_similar.html#existing-duplicates-with-more-than-one-salesperson)
          * [Le informazioni di contatto sono simili ma non uguali](sales/crm/pipeline/merge_similar.html#contact-information-is-similar-but-not-exact)
      * Gestire i team vendite
        * Creare un team di vendita
          * [Aggiungere membri al team di vendita](sales/crm/pipeline/manage_sales_teams.html#add-sales-team-members)
        * [Attivare più team](sales/crm/pipeline/manage_sales_teams.html#enable-multi-teams)
        * [Dashboard team vendite](sales/crm/pipeline/manage_sales_teams.html#sales-team-dashboard)
    * Acquisire nuovi contatti
      * Convertire i Lead in opportunità
        * [Configurazione](sales/crm/acquire_leads/convert.html#configuration)
        * [Convertire un Contatto in Opportunità](sales/crm/acquire_leads/convert.html#convert-a-lead-into-an-opportunity)
      * Creare opportunità dai moduli di contatto online
        * Personalizzare i moduli di contatto
          * [Personalizzare i campi del modulo contatto](sales/crm/acquire_leads/opportunities_form.html#customize-contact-form-fields)
        * [Visualizzare opportunità](sales/crm/acquire_leads/opportunities_form.html#view-opportunities)
      * Creare lead (da e-mail o manualmente)
        * Configurare alias delle email
          * [Lead creati da e-mail](sales/crm/acquire_leads/email_manual.html#leads-created-from-email)
        * Creare lead manualmente
          * [Creare opportunità manualmente](sales/crm/acquire_leads/email_manual.html#manually-create-opportunities)
      * Creare e inviare preventivi
        * Creare un nuovo preventivo
          * Righe ordine
            * [Catalogo prodotti](sales/crm/acquire_leads/send_quotes.html#product-catalog)
        * [Visualizzare l’anteprima e inviare un preventivo](sales/crm/acquire_leads/send_quotes.html#preview-and-send-quotation)
        * [Contrassegnare un’opportunità come vinta o persa](sales/crm/acquire_leads/send_quotes.html#mark-an-opportunity-won-or-lost)
      * Estrarre lead
        * [Configurazione](sales/crm/acquire_leads/lead_mining.html#configuration)
        * Generare lead
          * [Visualizzare lead](sales/crm/acquire_leads/lead_mining.html#view-leads)
        * [Tariffazione](sales/crm/acquire_leads/lead_mining.html#pricing)
    * Assegnare e tracciare i contatti
      * Assegnare lead con calcolo previsionale
        * Calcolo previsionale dei lead
          * [Configurazione](sales/crm/track_leads/lead_scoring.html#configuration)
          * [Modificare la probabilità manualmente](sales/crm/track_leads/lead_scoring.html#change-the-probability-manually)
        * Assegnare lead in base alla probabilità
          * [Configurare assegnazioni basate su regole](sales/crm/track_leads/lead_scoring.html#configure-rule-based-assignment)
          * [Configurare regole di assegnazione](sales/crm/track_leads/lead_scoring.html#configure-assignment-rules)
      * Resoconto lead non seguiti
        * Creare un resoconto sui lead non seguiti
          * Aggiungere filtri personalizzati
            * [Aggiungere un filtro per attività scadute](sales/crm/track_leads/unattended_leads_report.html#add-filter-for-past-due-activities)
            * [Escludere lead non assegnati](sales/crm/track_leads/unattended_leads_report.html#exclude-unassigned-leads)
            * [Aggiungere un team di vendita](sales/crm/track_leads/unattended_leads_report.html#add-a-sales-team)
        * [Visualizzare i risultati](sales/crm/track_leads/unattended_leads_report.html#view-results)
      * Resoconto lead di qualità
        * Creare un resoconto sui lead di qualità
          * Aggiungere filtri personalizzati
            * [Aggiungere il filtro data di inizio](sales/crm/track_leads/quality_leads_report.html#add-a-starting-date-filter)
            * [Aggiungere il filtro team vendite](sales/crm/track_leads/quality_leads_report.html#add-a-sales-team-filter)
            * [Escludere lead non assegnati](sales/crm/track_leads/quality_leads_report.html#exclude-unassigned-leads)
            * [Includere lead archiviati](sales/crm/track_leads/quality_leads_report.html#include-archived-leads)
            * Aggiungere regole per lead di qualità
              * [Definire un lead di qualità](sales/crm/track_leads/quality_leads_report.html#define-a-quality-lead)
        * [Visualizzare il resoconto](sales/crm/track_leads/quality_leads_report.html#view-the-report)
      * Partner
        * [Configurazione](sales/crm/track_leads/resellers.html#configuration)
        * [Livelli partner](sales/crm/track_leads/resellers.html#partner-levels)
        * [Attivazioni partner](sales/crm/track_leads/resellers.html#partner-activations)
        * [Assegnazioni partner](sales/crm/track_leads/resellers.html#partner-assignments)
        * [Pubblicare i partner](sales/crm/track_leads/resellers.html#publish-partners)
      * Resoconti attribuzione attività marketing
        * [Dashboard analisi lead](sales/crm/track_leads/marketing_attribution.html#leads-analysis-dashboard)
        * Aggiungere parametri UTM
          * [Creare UTM](sales/crm/track_leads/marketing_attribution.html#create-utms)
        * [Creare resoconti](sales/crm/track_leads/marketing_attribution.html#create-reports)
        * [Esportare resoconti](sales/crm/track_leads/marketing_attribution.html#export-reports)
      * Resoconto distribuzione lead
        * Creare resoconti di distribuzione dei lead
          * Filtri essenziali
            * [Data di creazione del lead](sales/crm/track_leads/lead_distribution_report.html#lead-creation-date)
            * [Team di vendita](sales/crm/track_leads/lead_distribution_report.html#sales-team)
            * [Metodo di contatto](sales/crm/track_leads/lead_distribution_report.html#contact-method)
            * [Stato attivo](sales/crm/track_leads/lead_distribution_report.html#active-status)
            * [Raggruppa per](sales/crm/track_leads/lead_distribution_report.html#group-by)
          * [Filtro per lead di qualità](sales/crm/track_leads/lead_distribution_report.html#filter-for-quality-leads)
    * Analizzare le performance
      * Analisi del flusso
        * Esplorare la pagina di analisi della pipeline
          * Opzioni di ricerca
            * [Aggiungere filtri e gruppi personalizzati](sales/crm/performance/win_loss.html#add-custom-filters-and-groups)
          * [Opzioni misure](sales/crm/performance/win_loss.html#measurement-options)
          * [Opzioni di visualizzazione](sales/crm/performance/win_loss.html#view-options)
        * Creare resoconti
          * Resoconti vincite/perdite
            * [Personalizzare resoconti vincite/perdite](sales/crm/performance/win_loss.html#customize-win-loss-reports)
        * [Salvare e condividere resoconti](sales/crm/performance/win_loss.html#save-and-share-reports)
      * Resoconto ricavi previsti
        * Creare un resoconto ricavi previsti
          * Aggiungere filtri personalizzati
            * [Aggiungere il filtro data chiusura prevista](sales/crm/performance/expected_revenue_report.html#add-filter-for-expected-closing-date)
            * [Escludere lead non assegnati](sales/crm/performance/expected_revenue_report.html#exclude-unassigned-leads)
            * [Aggiungere un filtro per i team di vendita](sales/crm/performance/expected_revenue_report.html#add-a-filter-for-sales-teams)
        * Visualizzare i risultati
          * [Opzioni di visualizzazione](sales/crm/performance/expected_revenue_report.html#view-options)
      * Resoconto previsionale
        * Esplorare il resoconto previsionale
          * [Data di chiusura prevista](sales/crm/performance/forecast_report.html#expected-closing-date)
          * [Ricavi ripartiti in proporzione](sales/crm/performance/forecast_report.html#prorated-revenue)
        * [Visualizzare i risultati](sales/crm/performance/forecast_report.html#view-results)
    * Ottimizzare il lavoro quotidiano
      * Arricchire i contatti con l’autocompletamento del partner
        * [Configurazione](sales/crm/optimize/partner_autocomplete.html#configuration)
        * [Arricchire contatti con dati aziendali](sales/crm/optimize/partner_autocomplete.html#enrich-contacts-with-corporate-data)
        * [Tariffazione](sales/crm/optimize/partner_autocomplete.html#pricing)
      * Gamification CRM
        * [Configurazione](sales/crm/optimize/gamification.html#configuration)
        * [Creare badge](sales/crm/optimize/gamification.html#create-badges)
        * Creare una sfida
          * [Creare regole di assegnazione](sales/crm/optimize/gamification.html#create-assignment-rules)
          * [Aggiungere obiettivi](sales/crm/optimize/gamification.html#add-goals)
          * [Aggiungere premi](sales/crm/optimize/gamification.html#add-rewards)
      * Utilizzare attività per i team di vendita
        * Tipi di attività
          * Creare un nuovo tipo di attività
            * Impostazioni attività
              * [Azione](sales/crm/optimize/utilize_activities.html#action)
              * [Utente predefinito](sales/crm/optimize/utilize_activities.html#default-user)
              * [Riepilogo predefinito](sales/crm/optimize/utilize_activities.html#default-summary)
            * Attività successiva
              * [Suggerimento attività successiva](sales/crm/optimize/utilize_activities.html#suggest-next-activity)
              * [Avviare attività successiva](sales/crm/optimize/utilize_activities.html#trigger-next-activity)
        * [Monitorare le attività](sales/crm/optimize/utilize_activities.html#activity-tracking)
        * Piani attività
          * [Lanciare un piano attività](sales/crm/optimize/utilize_activities.html#launch-an-activity-plan)
      * Arricchimento lead
        * [Configurare la funzione di lead enrichment](sales/crm/optimize/lead_enrichment.html#lead-enrichment-set-up)
        * Arricchire lead
          * [Arricchire lead automaticamente](sales/crm/optimize/lead_enrichment.html#automatically-enrich-leads)
          * [Arricchire lead manualmente](sales/crm/optimize/lead_enrichment.html#manually-enrich-leads)
        * [Tariffazione](sales/crm/optimize/lead_enrichment.html#pricing)
  * [Vendite](sales/sales.html)
    * Send Quotations
      * Creare preventivi
        * [Impostazioni preventivo](sales/sales/send_quotations/create_quotations.html#quotation-settings)
        * [Dashboard preventivi](sales/sales/send_quotations/create_quotations.html#quotations-dashboard)
        * Creare un preventivo
          * [Scheda righe ordine](sales/sales/send_quotations/create_quotations.html#order-lines-tab)
          * [Scheda prodotti opzionali](sales/sales/send_quotations/create_quotations.html#optional-products-tab)
          * Scheda Altre informazioni
            * [Sezione vendite](sales/sales/send_quotations/create_quotations.html#sales-section)
            * [Sezione Consegna](sales/sales/send_quotations/create_quotations.html#delivery-section)
            * [Sezione Fatturazione](sales/sales/send_quotations/create_quotations.html#invoicing-section)
            * [Sezione Monitoraggio](sales/sales/send_quotations/create_quotations.html#tracking-section)
          * [Scheda Note](sales/sales/send_quotations/create_quotations.html#notes-tab)
        * [Inviare e confermare preventivi](sales/sales/send_quotations/create_quotations.html#sending-and-confirming-quotations)
      * Modelli preventivo
        * [Configurazione](sales/sales/send_quotations/quote_template.html#configuration)
        * Create quotation templates
          * [Lines tab](sales/sales/send_quotations/quote_template.html#lines-tab)
          * [Scheda prodotti opzionali](sales/sales/send_quotations/quote_template.html#optional-products-tab)
          * [Terms & Conditions tab](sales/sales/send_quotations/quote_template.html#terms-conditions-tab)
          * [PDF Quote Builder tab](sales/sales/send_quotations/quote_template.html#pdf-quote-builder-tab)
        * [Use quotation templates](sales/sales/send_quotations/quote_template.html#use-quotation-templates)
        * [Mass cancel quotations/sales orders](sales/sales/send_quotations/quote_template.html#mass-cancel-quotations-sales-orders)
      * Prodotti opzionali
        * [Prodotti opzionali sui preventivi](sales/sales/send_quotations/optional_products.html#optional-products-on-quotations)
        * [Prodotti opzionali su modelli di preventivo](sales/sales/send_quotations/optional_products.html#optional-products-on-quotation-templates)
      * Firme online per confermare gli ordini
        * [Attivare firme online](sales/sales/send_quotations/get_signature_to_validate.html#activate-online-signatures)
        * [Conferme ordini con firme online](sales/sales/send_quotations/get_signature_to_validate.html#order-confirmations-with-online-signatures)
      * Conferma ordine tramite pagamento online
        * [Attivare i pagamenti online](sales/sales/send_quotations/get_paid_to_validate.html#activate-online-payments)
        * [Fornitori di pagamento](sales/sales/send_quotations/get_paid_to_validate.html#payment-providers)
        * [Registra un pagamento](sales/sales/send_quotations/get_paid_to_validate.html#register-a-payment)
      * Date di scadenza per i preventivi
        * [Scadenza del preventivo](sales/sales/send_quotations/deadline.html#quotation-expiration)
        * [Scadenza modello di preventivo](sales/sales/send_quotations/deadline.html#quotation-template-expiration)
      * Consegne e fatture a indirizzi diversi
        * [Impostazioni](sales/sales/send_quotations/different_addresses.html#settings)
        * [Configurazione del modulo di contatto](sales/sales/send_quotations/different_addresses.html#contact-form-configuration)
        * [Indirizzi aggiunti ai preventivi](sales/sales/send_quotations/different_addresses.html#address-added-to-quotations)
      * Varianti prodotto su preventivi e ordini di vendita
        * [Impostazioni](sales/sales/send_quotations/orders_and_variants.html#settings)
        * [Configurazione prodotto](sales/sales/send_quotations/orders_and_variants.html#product-configuration)
        * [Configuratore prodotto](sales/sales/send_quotations/orders_and_variants.html#product-configurator)
        * [Voce griglia ordine](sales/sales/send_quotations/orders_and_variants.html#order-grid-entry)
      * Creazione preventivi in PDF
        * [Configurazione](sales/sales/send_quotations/pdf_quote_builder.html#configuration)
        * Testo dinamico nei PDF
          * [Valori testo dinamico](sales/sales/send_quotations/pdf_quote_builder.html#dynamic-text-values)
        * [Add PDF to product](sales/sales/send_quotations/pdf_quote_builder.html#add-pdf-to-product)
        * [PDF quote](sales/sales/send_quotations/pdf_quote_builder.html#pdf-quote)
    * Invoicing Method
      * Fatture basate su quantità ordinate o consegnate
        * [Funzionalità politica di fatturazione](sales/sales/invoicing/invoicing_policy.html#invoicing-policy-features)
        * [Politica di fatturazione su modulo prodotto](sales/sales/invoicing/invoicing_policy.html#invoicing-policy-on-product-form)
        * [Impatto sui flussi di vendita](sales/sales/invoicing/invoicing_policy.html#impact-on-sales-flow)
      * Acconti
        * [Crea fatture](sales/sales/invoicing/down_payment.html#create-invoices)
        * [Richiesta acconto iniziale](sales/sales/invoicing/down_payment.html#initial-down-payment-request)
        * [Esempio: richiesta anticipo 50%](sales/sales/invoicing/down_payment.html#example-request-50-down-payment)
        * [Esempio: acconto 100% richiesto](sales/sales/invoicing/down_payment.html#example-request-100-down-payment)
        * [Modifica conto di ricavo per acconti](sales/sales/invoicing/down_payment.html#income-account-modification-on-down-payments)
      * Fatture proforma
        * [Configurazione](sales/sales/invoicing/proforma.html#configuration)
        * [Inviare una fattura proforma](sales/sales/invoicing/proforma.html#send-pro-forma-invoice)
      * Fatture basate su tempo e materiali
        * [Configurazione app e impostazioni](sales/sales/invoicing/time_materials.html#app-and-settings-configuration)
        * [Configurazione prodotto servizio](sales/sales/invoicing/time_materials.html#service-product-configuration)
        * [Aggiungere tempo speso a un ordine di vendita](sales/sales/invoicing/time_materials.html#add-time-spent-to-sales-order)
        * [Fatturare il tempo impiegato](sales/sales/invoicing/time_materials.html#invoice-time-spent)
        * [Configurazione note spese](sales/sales/invoicing/time_materials.html#expenses-configuration)
        * [Aggiungere spese a un ordine di vendita](sales/sales/invoicing/time_materials.html#add-expenses-to-sales-order)
        * [Fatturare le spese](sales/sales/invoicing/time_materials.html#invoice-expenses)
        * [Configurazione di un acquisto](sales/sales/invoicing/time_materials.html#purchase-configuration)
        * [Aggiungere acquisti a un ordine di vendita](sales/sales/invoicing/time_materials.html#add-purchase-to-sales-order)
        * [Fatturare acquisti](sales/sales/invoicing/time_materials.html#invoice-purchase)
      * Fatturare milestone di progetto
        * [Creare prodotti milestone](sales/sales/invoicing/milestone.html#create-milestone-products)
        * [Invoice milestones](sales/sales/invoicing/milestone.html#invoice-milestones)
      * Reinvoice expenses to customers
        * [Expenses application](sales/sales/invoicing/expense.html#expenses-application)
        * [Add expenses to sales orders](sales/sales/invoicing/expense.html#add-expenses-to-sales-orders)
        * [Reinvoice expense](sales/sales/invoicing/expense.html#reinvoice-expense)
    * Products & Prices
      * Manage your products
        * Import products
          * [Import template](sales/sales/products_prices/products/import.html#import-template)
          * [Customize product import template](sales/sales/products_prices/products/import.html#customize-product-import-template)
          * [Import product template spreadsheet](sales/sales/products_prices/products/import.html#import-product-template-spreadsheet)
          * Importare campi di relazione, attributi e varianti
            * [Relation fields](sales/sales/products_prices/products/import.html#relation-fields)
            * [Attributes and values](sales/sales/products_prices/products/import.html#attributes-and-values)
            * [Varianti prodotto](sales/sales/products_prices/products/import.html#product-variants)
        * Varianti prodotto
          * [Configurazione](sales/sales/products_prices/products/variants.html#configuration)
          * Attributi
            * Attribute values
              * [Colori](sales/sales/products_prices/products/variants.html#colors)
          * Varianti prodotto
            * [Configure variants](sales/sales/products_prices/products/variants.html#configure-variants)
            * [Variants smart button](sales/sales/products_prices/products/variants.html#variants-smart-button)
          * [Impact of variants](sales/sales/products_prices/products/variants.html#impact-of-variants)
        * Product images with Google Images
          * Configurazione
            * [Google API dashboard](sales/sales/products_prices/products/product_images.html#google-api-dashboard)
            * [Google Programmable Search dashboard](sales/sales/products_prices/products/product_images.html#google-programmable-search-dashboard)
            * [Odoo](sales/sales/products_prices/products/product_images.html#odoo)
          * [Product images in Odoo with Google Custom Search API](sales/sales/products_prices/products/product_images.html#product-images-in-odoo-with-google-custom-search-api)
      * Manage your pricing
        * Pricelists, discounts, and formulas
          * [Pricing strategy options](sales/sales/products_prices/prices/pricing.html#pricing-strategy-options)
          * Listini prezzi
            * Price Rules tab
              * [Prezzi multipli per prodotto](sales/sales/products_prices/prices/pricing.html#multiple-prices-per-product)
              * [Advanced price rules](sales/sales/products_prices/prices/pricing.html#advanced-price-rules)
            * [Recurring Prices tab](sales/sales/products_prices/prices/pricing.html#recurring-prices-tab)
            * [Rental rules tab](sales/sales/products_prices/prices/pricing.html#rental-rules-tab)
            * Configuration tab
              * [Show discount percentage to customers](sales/sales/products_prices/prices/pricing.html#show-discount-percentage-to-customers)
          * [Customer pricelist application](sales/sales/products_prices/prices/pricing.html#customer-pricelist-application)
          * [Prezzi multipli per prodotto](sales/sales/products_prices/prices/pricing.html#sales-multiple-prices-per-product)
          * Sconti
            * [Discount button](sales/sales/products_prices/prices/pricing.html#discount-button)
          * Advanced price rules
            * [Price computation](sales/sales/products_prices/prices/pricing.html#price-computation)
            * [Condizioni](sales/sales/products_prices/prices/pricing.html#conditions)
        * Foreign currencies
          * [Impostazioni](sales/sales/products_prices/prices/currencies.html#settings)
          * View, edit, and add currencies
            * [Currency detail form](sales/sales/products_prices/prices/currencies.html#currency-detail-form)
            * [Main currency detail form](sales/sales/products_prices/prices/currencies.html#main-currency-detail-form)
          * [Create new currency](sales/sales/products_prices/prices/currencies.html#create-new-currency)
          * [Currency-specific pricelists](sales/sales/products_prices/prices/currencies.html#currency-specific-pricelists)
          * [Auto-conversion from public price](sales/sales/products_prices/prices/currencies.html#auto-conversion-from-public-price)
          * [Set product prices](sales/sales/products_prices/prices/currencies.html#set-product-prices)
      * Returns and refunds
        * [Before invoicing](sales/sales/products_prices/returns.html#before-invoicing)
        * [After invoicing](sales/sales/products_prices/returns.html#after-invoicing)
      * Use eWallets and gift cards
        * [Portafoglio elettronico](sales/sales/products_prices/ewallets_giftcards.html#ewallets)
        * [Gift cards](sales/sales/products_prices/ewallets_giftcards.html#gift-cards)
      * Discount and loyalty programs
        * [Configure the settings](sales/sales/products_prices/loyalty_discount.html#configure-the-settings)
        * Configure discount and loyalty programs
          * [Program types](sales/sales/products_prices/loyalty_discount.html#program-types)
          * [Regole condizionali](sales/sales/products_prices/loyalty_discount.html#conditional-rules)
          * [Premi](sales/sales/products_prices/loyalty_discount.html#rewards)
    * Integrazione con Amazon
      * Amazon Connector features
        * [Supported features](sales/sales/amazon_connector/features.html#supported-features)
        * [Supported marketplaces](sales/sales/amazon_connector/features.html#supported-marketplaces)
      * Amazon Connector configuration
        * [Connect Amazon Seller account to Odoo](sales/sales/amazon_connector/setup.html#connect-amazon-seller-account-to-odoo)
        * [Amazon orders in Odoo](sales/sales/amazon_connector/setup.html#amazon-orders-in-odoo)
        * [Product tax configuration](sales/sales/amazon_connector/setup.html#product-tax-configuration)
        * [Add a new marketplace](sales/sales/amazon_connector/setup.html#add-a-new-marketplace)
      * Amazon order management
        * [Order synchronization](sales/sales/amazon_connector/manage.html#order-synchronization)
        * [Force synchronization](sales/sales/amazon_connector/manage.html#force-synchronization)
        * Manage deliveries in FBM
          * [Manage errors when synchronizing deliveries](sales/sales/amazon_connector/manage.html#manage-errors-when-synchronizing-deliveries)
        * [Follow deliveries in FBA](sales/sales/amazon_connector/manage.html#follow-deliveries-in-fba)
        * Invoice and register payments
          * [Emetti fatture](sales/sales/amazon_connector/manage.html#issue-invoices)
          * [Register payments](sales/sales/amazon_connector/manage.html#register-payments)
        * [Follow Amazon sales in sales reporting](sales/sales/amazon_connector/manage.html#follow-amazon-sales-in-sales-reporting)
    * Integrazione con eBay
      * eBay connector setup
        * Panoramica
          * [eBay - Odoo linked fields](sales/sales/ebay_connector/setup.html#ebay-odoo-linked-fields)
          * [eBay terms](sales/sales/ebay_connector/setup.html#ebay-terms)
          * [eBay actions available on Odoo](sales/sales/ebay_connector/setup.html#ebay-actions-available-on-odoo)
        * [Setup required on Odoo prior to eBay setup](sales/sales/ebay_connector/setup.html#setup-required-on-odoo-prior-to-ebay-setup)
        * Set up on eBay
          * [Set up eBay developer account](sales/sales/ebay_connector/setup.html#set-up-ebay-developer-account)
          * Set up eBay keyset
            * [Configure account deletion / notification settings (Production)](sales/sales/ebay_connector/setup.html#configure-account-deletion-notification-settings-production)
            * [Creating the keyset](sales/sales/ebay_connector/setup.html#creating-the-keyset)
          * [Create eBay user token](sales/sales/ebay_connector/setup.html#create-ebay-user-token)
          * [Grant application access](sales/sales/ebay_connector/setup.html#grant-application-access)
          * [API explorer](sales/sales/ebay_connector/setup.html#api-explorer)
        * [Entering credentials into Odoo](sales/sales/ebay_connector/setup.html#entering-credentials-into-odoo)
      * How to list a product?
        * [Listing without variation](sales/sales/ebay_connector/manage.html#listing-without-variation)
        * [Listing with variations](sales/sales/ebay_connector/manage.html#listing-with-variations)
        * Product identifiers
          * [EAN and UPC identifiers](sales/sales/ebay_connector/manage.html#ean-and-upc-identifiers)
          * [Listing with item specifics](sales/sales/ebay_connector/manage.html#listing-with-item-specifics)
        * Process invoices and payments
          * [Posting payment](sales/sales/ebay_connector/manage.html#posting-payment)
          * [Reconciling payments](sales/sales/ebay_connector/manage.html#reconciling-payments)
      * Troubleshooting eBay connector
        * Accept account deletion notifications
          * Verify the installation of Odoo is up to date
            * [Update Odoo to the latest release](sales/sales/ebay_connector/troubleshooting.html#update-odoo-to-the-latest-release)
            * [Update the list of available modules](sales/sales/ebay_connector/troubleshooting.html#update-the-list-of-available-modules)
            * [Install the eBay Connector - Account Deletion update](sales/sales/ebay_connector/troubleshooting.html#install-the-ebay-connector-account-deletion-update)
          * [Retrieve endpoint details from Odoo](sales/sales/ebay_connector/troubleshooting.html#retrieve-endpoint-details-from-odoo)
          * [Subscribe to account deletion notifications](sales/sales/ebay_connector/troubleshooting.html#subscribe-to-account-deletion-notifications)
          * [Verify the connectivity with the endpoint](sales/sales/ebay_connector/troubleshooting.html#verify-the-connectivity-with-the-endpoint)
      * Linking existing listings
        * Turn off eBay scheduled actions
          * [Sync eBay categories](sales/sales/ebay_connector/linking_listings.html#sync-ebay-categories)
        * Link eBay listings
          * [Manual listing link](sales/sales/ebay_connector/linking_listings.html#manual-listing-link)
        * [Turn on eBay scheduled Actions](sales/sales/ebay_connector/linking_listings.html#turn-on-ebay-scheduled-actions)
  * [Punto vendita](sales/point_of_sale.html)
    * [Start a session](sales/point_of_sale.html#start-a-session)
    * [Sell products](sales/point_of_sale.html#sell-products)
    * [Set customers](sales/point_of_sale.html#set-customers)
    * [Customer notes](sales/point_of_sale.html#customer-notes)
    * [Return and refund products](sales/point_of_sale.html#return-and-refund-products)
    * [Manage the cash register](sales/point_of_sale.html#manage-the-cash-register)
    * [Close the POS session](sales/point_of_sale.html#close-the-pos-session)
    * Analitiche
      * [Configurazione](sales/point_of_sale/configuration.html)
        * [Access the POS settings](sales/point_of_sale/configuration.html#access-the-pos-settings)
        * [Make products available](sales/point_of_sale/configuration.html#make-products-available)
        * PoS product categories
          * [Configurazione](sales/point_of_sale/configuration.html#id1)
          * [Assign PoS product categories](sales/point_of_sale/configuration.html#assign-pos-product-categories)
          * Adapt the POS interface
            * [Start category](sales/point_of_sale/configuration.html#start-category)
            * Restrict categories
              * IoT system connection
                * [Setup example](sales/point_of_sale/configuration/pos_iot.html#setup-example)
              * ePOS printers
                * [Configurazione](sales/point_of_sale/configuration/epos_printers.html#configuration)
                * [Directly supported ePOS printers](sales/point_of_sale/configuration/epos_printers.html#directly-supported-epos-printers)
                * [ePOS printers with IoT system integration](sales/point_of_sale/configuration/epos_printers.html#epos-printers-with-iot-system-integration)
              * Secure connection (HTTPS)
                * [Force your Point of Sale to use a secure connection (HTTPS)](sales/point_of_sale/configuration/https.html#force-your-point-of-sale-to-use-a-secure-connection-https)
              * Self-signed certificate for ePOS printers
                * [Generate, export, and import self-signed certificates](sales/point_of_sale/configuration/epos_ssc.html#generate-export-and-import-self-signed-certificates)
                * [Check if the certificate was imported correctly](sales/point_of_sale/configuration/epos_ssc.html#check-if-the-certificate-was-imported-correctly)
      * Multi-employee management
        * [Configurazione](sales/point_of_sale/employee_login.html#configuration)
        * Usage guidelines
          * [Accedere](sales/point_of_sale/employee_login.html#logging-in)
          * [Logging in with badges](sales/point_of_sale/employee_login.html#logging-in-with-badges)
          * [Adding a PIN Code](sales/point_of_sale/employee_login.html#adding-a-pin-code)
      * Receipts and invoices
        * Ricezioni
          * [Reprint a receipt](sales/point_of_sale/receipts_invoices.html#reprint-a-receipt)
        * Fatture
          * [Configurazione](sales/point_of_sale/receipts_invoices.html#configuration)
          * [Invoice a customer](sales/point_of_sale/receipts_invoices.html#invoice-a-customer)
          * [Retrieve invoices](sales/point_of_sale/receipts_invoices.html#retrieve-invoices)
          * [QR codes to generate invoices](sales/point_of_sale/receipts_invoices.html#qr-codes-to-generate-invoices)
      * Schermo di preparazione
        * [Configurazione](sales/point_of_sale/preparation.html#configuration)
        * Practical application
          * [Using the preparation display](sales/point_of_sale/preparation.html#using-the-preparation-display)
          * [Schermo cliente](sales/point_of_sale/preparation.html#customer-display)
      * Self-ordering
        * Configurazione
          * [Feature activation](sales/point_of_sale/self_order.html#feature-activation)
          * [Additional settings](sales/point_of_sale/self_order.html#additional-settings)
          * [Anteprima](sales/point_of_sale/self_order.html#preview)
        * [Usage guidelines](sales/point_of_sale/self_order.html#usage-guidelines)
      * Product combos
        * [Configurazione](sales/point_of_sale/combos.html#configuration)
        * [Practical application](sales/point_of_sale/combos.html#practical-application)
      * Shop features
        * Sales orders
          * [Select a sales order](sales/point_of_sale/shop/sales_order.html#select-a-sales-order)
          * [Apply a down payment or settle the order](sales/point_of_sale/shop/sales_order.html#apply-a-down-payment-or-settle-the-order)
        * Codici a barre
          * [Configurazione](sales/point_of_sale/shop/barcode.html#configuration)
          * Assign barcodes
            * [To your products](sales/point_of_sale/shop/barcode.html#to-your-products)
            * [To your employees](sales/point_of_sale/shop/barcode.html#to-your-employees)
          * Use barcodes
            * [Scansiona prodotti](sales/point_of_sale/shop/barcode.html#scan-products)
            * [Log employees](sales/point_of_sale/shop/barcode.html#log-employees)
        * Serial numbers and lots
          * [Serial numbers and lots importation](sales/point_of_sale/shop/serial_numbers.html#serial-numbers-and-lots-importation)
          * [Serial numbers and lots creation](sales/point_of_sale/shop/serial_numbers.html#serial-numbers-and-lots-creation)
        * Ship later
          * [Configurazione](sales/point_of_sale/shop/ship_later.html#configuration)
          * [Practical application](sales/point_of_sale/shop/ship_later.html#practical-application)
        * Schermo cliente
          * Configurazione
            * [Local](sales/point_of_sale/shop/customer_display.html#local)
            * [IoT system](sales/point_of_sale/shop/customer_display.html#iot-system)
      * [Restaurant features](sales/point_of_sale/restaurant.html)
        * [Configurazione](sales/point_of_sale/restaurant.html#configuration)
        * Take orders
          * Floors and tables
            * Configurazione
              * [From the POS backend](sales/point_of_sale/restaurant/floors_tables.html#from-the-pos-backend)
              * [From the POS frontend](sales/point_of_sale/restaurant/floors_tables.html#from-the-pos-frontend)
            * [Table transfer](sales/point_of_sale/restaurant/floors_tables.html#table-transfer)
          * Orders printing
            * Configurazione
              * [Enable and create printers](sales/point_of_sale/restaurant/kitchen_printing.html#enable-and-create-printers)
              * [Setup form](sales/point_of_sale/restaurant/kitchen_printing.html#setup-form)
            * [Print orders](sales/point_of_sale/restaurant/kitchen_printing.html#print-orders)
          * Fatture
            * [Configurazione](sales/point_of_sale/restaurant/bill_printing.html#configuration)
            * [Bill printing](sales/point_of_sale/restaurant/bill_printing.html#bill-printing)
            * [Bill splitting](sales/point_of_sale/restaurant/bill_printing.html#bill-splitting)
          * Mance
            * Configurazione
              * [Tip products](sales/point_of_sale/restaurant/tips.html#tip-products)
              * [Tip using an Adyen terminal](sales/point_of_sale/restaurant/tips.html#tip-using-an-adyen-terminal)
              * [Tip after payment](sales/point_of_sale/restaurant/tips.html#tip-after-payment)
            * Add tips
              * [Tip using an Adyen terminal](sales/point_of_sale/restaurant/tips.html#id2)
              * [Tip after payment](sales/point_of_sale/restaurant/tips.html#id3)
      * Pricing features
        * Sconti
          * Apply manual discounts
            * [Apply a discount on a product](sales/point_of_sale/pricing/discounts.html#apply-a-discount-on-a-product)
            * [Apply a global discount](sales/point_of_sale/pricing/discounts.html#apply-a-global-discount)
          * Apply time-limited discounts
            * [Create a pricelist](sales/point_of_sale/pricing/discounts.html#create-a-pricelist)
            * [Using a pricelist with the PoS interface](sales/point_of_sale/pricing/discounts.html#using-a-pricelist-with-the-pos-interface)
        * Discount tags (barcode scanner)
          * [Nomenclatura codice a barre](sales/point_of_sale/pricing/discount_tags.html#barcode-nomenclature)
          * [Scan the products & tags](sales/point_of_sale/pricing/discount_tags.html#scan-the-products-tags)
        * Loyalty programs
          * [Configurazione](sales/point_of_sale/pricing/loyalty.html#configuration)
          * [Use the loyalty program in your PoS interface](sales/point_of_sale/pricing/loyalty.html#use-the-loyalty-program-in-your-pos-interface)
        * Listini prezzi
          * Configurazione
            * Create pricelists
              * [Prezzi multipli per prodotto](sales/point_of_sale/pricing/pricelists.html#multiple-prices-per-product)
              * [Advanced price rules](sales/point_of_sale/pricing/pricelists.html#advanced-price-rules)
            * [Select pricelists](sales/point_of_sale/pricing/pricelists.html#select-pricelists)
        * Flexible taxes (fiscal positions)
          * [Configurazione](sales/point_of_sale/pricing/fiscal_position.html#configuration)
          * [Use fiscal positions](sales/point_of_sale/pricing/fiscal_position.html#use-fiscal-positions)
        * Arrotondamento di cassa
          * [Configurazione](sales/point_of_sale/pricing/cash_rounding.html#configuration)
        * Electronic shelf labels
          * Configurazione
            * [Pricer setup](sales/point_of_sale/pricing/electronic_labels.html#pricer-setup)
            * Configurare Odoo
              * [Pricer stores](sales/point_of_sale/pricing/electronic_labels.html#pricer-stores)
              * [Etichette Pricer](sales/point_of_sale/pricing/electronic_labels.html#pricer-tags)
            * [Practical application](sales/point_of_sale/pricing/electronic_labels.html#practical-application)
      * [Metodo di pagamento](sales/point_of_sale/payment_methods.html)
        * [Payment terminals](sales/point_of_sale/payment_methods/terminals.html)
          * [Configurazione](sales/point_of_sale/payment_methods/terminals.html#configuration)
          * Pay with a payment terminal
            * Adyen
              * Configurazione
                * [Generate an Adyen API key](sales/point_of_sale/payment_methods/terminals/adyen.html#generate-an-adyen-api-key)
                * [Locate the Adyen terminal identifier](sales/point_of_sale/payment_methods/terminals/adyen.html#locate-the-adyen-terminal-identifier)
                * [Set the Event URLs](sales/point_of_sale/payment_methods/terminals/adyen.html#set-the-event-urls)
                * [Configure the payment method](sales/point_of_sale/payment_methods/terminals/adyen.html#configure-the-payment-method)
            * Ingenico
              * Configurazione
                * [Connect an IoT system](sales/point_of_sale/payment_methods/terminals/ingenico.html#connect-an-iot-system)
                * [Configure the Lane/Desk/Move 5000 terminals for Ingenico BENELUX](sales/point_of_sale/payment_methods/terminals/ingenico.html#configure-the-lane-desk-move-5000-terminals-for-ingenico-benelux)
                * [Configure the payment method](sales/point_of_sale/payment_methods/terminals/ingenico.html#configure-the-payment-method)
            * Mercado Pago
              * Configurazione
                * [Point Smart application](sales/point_of_sale/payment_methods/terminals/mercado_pago.html#point-smart-application)
                * [Credenziali](sales/point_of_sale/payment_methods/terminals/mercado_pago.html#credentials)
                * [Metodo di pagamento](sales/point_of_sale/payment_methods/terminals/mercado_pago.html#payment-method)
            * Razorpay
              * Configurazione
                * [Locate your Razorpay credentials](sales/point_of_sale/payment_methods/terminals/razorpay.html#locate-your-razorpay-credentials)
                * [Configure the payment method](sales/point_of_sale/payment_methods/terminals/razorpay.html#configure-the-payment-method)
            * SIX
              * Configurazione
                * [Install the POS IoT Six module](sales/point_of_sale/payment_methods/terminals/six.html#install-the-pos-iot-six-module)
                * [Connect an IoT system](sales/point_of_sale/payment_methods/terminals/six.html#connect-an-iot-system)
                * [Configure the terminal ID](sales/point_of_sale/payment_methods/terminals/six.html#configure-the-terminal-id)
                * [Configure the payment method](sales/point_of_sale/payment_methods/terminals/six.html#configure-the-payment-method)
            * Stripe
              * Configurazione
                * [Configure the payment method](sales/point_of_sale/payment_methods/terminals/stripe.html#configure-the-payment-method)
                * [Connect Stripe to Odoo](sales/point_of_sale/payment_methods/terminals/stripe.html#connect-stripe-to-odoo)
                * [Configure the payment terminal](sales/point_of_sale/payment_methods/terminals/stripe.html#configure-the-payment-terminal)
                * [Link the payment method to a POS](sales/point_of_sale/payment_methods/terminals/stripe.html#link-the-payment-method-to-a-pos)
              * Risoluzione problemi
                * [Payment terminal unavailable in your Stripe account](sales/point_of_sale/payment_methods/terminals/stripe.html#payment-terminal-unavailable-in-your-stripe-account)
            * Vantiv
              * Configurazione
                * [Configure the payment method](sales/point_of_sale/payment_methods/terminals/vantiv.html#configure-the-payment-method)
            * Viva Wallet
              * Configurazione
                * Locate your Viva Wallet credentials
                  * [Merchant ID and API key](sales/point_of_sale/payment_methods/terminals/viva_wallet.html#merchant-id-and-api-key)
                  * [POS API credentials](sales/point_of_sale/payment_methods/terminals/viva_wallet.html#pos-api-credentials)
                  * [ID terminale](sales/point_of_sale/payment_methods/terminals/viva_wallet.html#terminal-id)
                * [Configure the payment method](sales/point_of_sale/payment_methods/terminals/viva_wallet.html#configure-the-payment-method)
                * [Configure the webhook](sales/point_of_sale/payment_methods/terminals/viva_wallet.html#configure-the-webhook)
                * [Link the payment method to a POS](sales/point_of_sale/payment_methods/terminals/viva_wallet.html#link-the-payment-method-to-a-pos)
            * Worldline
              * Configurazione
                * [Connect an IoT system](sales/point_of_sale/payment_methods/terminals/worldline.html#connect-an-iot-system)
                * [Configure the protocol](sales/point_of_sale/payment_methods/terminals/worldline.html#configure-the-protocol)
                * Set the IP address
                  * [Hostname](sales/point_of_sale/payment_methods/terminals/worldline.html#hostname)
                  * [Port number](sales/point_of_sale/payment_methods/terminals/worldline.html#port-number)
                * [Configure the payment method](sales/point_of_sale/payment_methods/terminals/worldline.html#configure-the-payment-method)
      * Rendiconto
        * [View statistics](sales/point_of_sale/reporting.html#view-statistics)
  * [Abbonamenti](sales/subscriptions.html)
    * Set up recurring plans
      * [DETAILS section](sales/subscriptions.html#details-section)
      * [SELF-SERVICE section](sales/subscriptions.html#self-service-section)
      * [Pricing tab](sales/subscriptions.html#pricing-tab)
    * [Product form configuration](sales/subscriptions.html#product-form-configuration)
    * [Create a subscriptions quotation](sales/subscriptions.html#create-a-subscriptions-quotation)
    * Conferma
      * Subscriptions in the eCommerce shop
        * [Create recurrence periods as product variants](sales/subscriptions/ecommerce.html#create-recurrence-periods-as-product-variants)
      * Subscription plans
        * [Configure subscription plans](sales/subscriptions/plans.html#configure-subscription-plans)
        * [Use subscription plans on quotations](sales/subscriptions/plans.html#use-subscription-plans-on-quotations)
      * Upsell subscriptions
        * Discount configuration
          * [Upsell subscriptions](sales/subscriptions/upselling.html#id1)
      * Renew subscriptions
        * [Subscription renewals](sales/subscriptions/renewals.html#subscription-renewals)
      * Close subscriptions
        * [Configurazione](sales/subscriptions/closing.html#configuration)
        * Close a subscription
          * [Administrator view](sales/subscriptions/closing.html#administrator-view)
          * [Customer view](sales/subscriptions/closing.html#customer-view)
      * Regole di automazione
        * Crea regole per l’automazione
          * Automation rule form fields
            * [Apply On section](sales/subscriptions/automatic_alerts.html#apply-on-section)
            * Action section
              * [Activity section](sales/subscriptions/automatic_alerts.html#activity-section)
      * Scheduled actions
        * [Access scheduled actions](sales/subscriptions/scheduled_actions.html#access-scheduled-actions)
        * Generate recurring invoices and payments
          * [Crea fattura](sales/subscriptions/scheduled_actions.html#create-invoice)
          * [Closing invoices](sales/subscriptions/scheduled_actions.html#closing-invoices)
        * [Subscriptions expiration](sales/subscriptions/scheduled_actions.html#subscriptions-expiration)
      * Subscription reports
        * Reporting page elements
          * [Filters and Group By](sales/subscriptions/reports.html#filters-and-group-by)
          * Visualizzazioni
            * [Vista grafico](sales/subscriptions/reports.html#graph-view)
            * [Vista elenco](sales/subscriptions/reports.html#list-view)
            * [VIsta pivot](sales/subscriptions/reports.html#pivot-view)
          * [Misure](sales/subscriptions/reports.html#measures)
          * [Inserisci nel foglio di calcolo](sales/subscriptions/reports.html#insert-in-spreadsheet)
        * Reporting pages
          * [Subscriptions analysis](sales/subscriptions/reports.html#subscriptions-analysis)
          * [Retention analysis](sales/subscriptions/reports.html#retention-analysis)
          * [MRR breakdown](sales/subscriptions/reports.html#mrr-breakdown)
          * [MRR analysis](sales/subscriptions/reports.html#mrr-analysis)
  * Noleggio
    * [Bacheca](sales/rental.html#dashboard)
    * [Impostazioni](sales/rental.html#settings)
    * [Rental products](sales/rental.html#rental-products)
    * Rental pricing
      * [Tariffazione](sales/rental.html#pricing)
      * [Prenotazioni](sales/rental.html#reservations)
      * [Price computing](sales/rental.html#price-computing)
    * [Rental orders](sales/rental.html#rental-orders)
    * [Customer signature](sales/rental.html#customer-signature)
    * [Pickup products](sales/rental.html#pickup-products)
    * [Return products](sales/rental.html#return-products)
    * [Print pickup and return receipts](sales/rental.html#print-pickup-and-return-receipts)
  * [Iscritti](sales/members.html)
    * [Prodotti iscrizione](sales/members.html#membership-products)
    * [Attivare un’iscrizione](sales/members.html#activate-a-membership)
    * [Stato iscrizione](sales/members.html#membership-status)
    * Pubblicare l’elenco degli iscritti
      * Pubblicare singoli membri
        * Analisi iscritti
          * [Esplorare il resoconto](sales/members/members_analysis.html#navigate-the-report)
          * [Visualizzare i risultati](sales/members/members_analysis.html#view-results)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/sales.rst)

### Navigazione

  * [indice](../genindex.html "Indice generale")
  * [moduli](../py-modindex.html "Indice del modulo Python") |
  * [successivo](sales/crm.html "CRM") |
  * [precedente](finance/fiscal_localizations/uruguay.html "Uruguay") |
  * [Odoo 17.0 documentazione](../index-2.html) »
  * [Documentazione Utente](../applications.html) »
  * Vendite


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