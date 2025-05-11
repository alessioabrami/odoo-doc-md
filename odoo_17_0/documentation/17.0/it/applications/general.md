# Impostazioni generali — Odoo 17.0 documentazione

### Navigazione

  * [indice](../genindex.html "Indice generale")
  * [moduli](../py-modindex.html "Indice del modulo Python") |
  * [successivo](general/apps_modules.html "App e Moduli") |
  * [precedente](studio/approval_rules.html "Regole di approvazione") |
  * [Odoo 17.0 documentazione](../index-2.html) »
  * [Documentazione Utente](../applications.html) »
  * Impostazioni generali



# Impostazioni generali¶

  * App e Moduli
    * [Installare applicazioni e moduli](general/apps_modules.html#install-apps-and-modules)
    * [Aggiornare applicazioni e moduli](general/apps_modules.html#upgrade-apps-and-modules)
    * [Disinstallare applicazioni e moduli](general/apps_modules.html#uninstall-apps-and-modules)
  * [Utenti](general/users.html)
    * Aggiungere utenti
      * [Tipo di utente](general/users.html#user-type)
    * Disattivare utenti
      * [Errore: troppi utenti](general/users.html#error-too-many-users)
    * Gestione password
      * Reset della password
        * [Abilitare la reimpostazione della password dalla pagina di login](general/users.html#enable-password-reset-from-login-page)
        * [Inviare istruzioni reimpostazione password](general/users.html#send-reset-instructions)
      * [Modificare password utente](general/users.html#change-user-password)
    * Multi azienda
      * Modificare la lingua
        * [Aggiungi lingue](general/users/language.html#add-languages)
        * Modificare la lingua
          * [Modificare la lingua di un altro utente](general/users/language.html#change-another-user-s-language)
      * Autenticazione a due fattori
        * [Requisiti](general/users/2fa.html#requirements)
        * [Configurazione autenticazione a due fattori](general/users/2fa.html#two-factor-authentication-setup)
        * [Accedere](general/users/2fa.html#logging-in)
        * [Applicare l’autenticazione a due fattori](general/users/2fa.html#enforce-two-factor-authentication)
      * Diritti di accesso
        * [Utenti](general/users/access_rights.html#users)
        * [Creare e modificare gruppi](general/users/access_rights.html#create-and-modify-groups)
        * [Modalità superutente](general/users/access_rights.html#superuser-mode)
      * Accedere al portale
        * [Fornire ai clienti l’accesso al portale](general/users/portal.html#provide-portal-access-to-customers)
        * [Modificare il nome utente nel portale](general/users/portal.html#change-portal-username)
        * Modificare il portale clienti
          * [Modificare le informazioni del cliente](general/users/portal.html#change-customer-info)
          * [Modifica password](general/users/portal.html#change-password)
          * [Aggiungere l’autenticazione a due fattori](general/users/portal.html#add-two-factor-authentication)
          * [Modificare le informazioni di pagamento](general/users/portal.html#change-payment-info)
      * Autenticazione accesso Facebook
        * Configurare Meta for Developers
          * [Personalizzare l’app](general/users/facebook.html#customize-app)
          * [Configurare le impostazioni](general/users/facebook.html#configure-settings)
          * [Acquisire ID app](general/users/facebook.html#capture-app-id)
          * [Pubblicata](general/users/facebook.html#publish)
        * [Configurare Odoo](general/users/facebook.html#odoo-setup)
      * Autenticazione accesso Google
        * Configurazione
          * Dashboard Google API
            * [Schermata di consenso OAuth](general/users/google.html#oauth-consent-screen)
            * [Credenziali](general/users/google.html#credentials)
          * Autenticazione Google su Odoo
            * [Recuperare l’ID client](general/users/google.html#retrieve-the-client-id)
            * [Attivazione di Odoo](general/users/google.html#odoo-activation)
        * [Accedere a Odoo tramite Google](general/users/google.html#log-in-to-odoo-with-google)
      * Autenticazione accesso Microsoft Azure
        * Configurazione
          * [Parametri di sistema Odoo](general/users/azure.html#odoo-system-parameter)
          * Dashboard Microsoft Azure
            * [Creare una nuova applicazione](general/users/azure.html#create-a-new-application)
            * [Autenticazione](general/users/azure.html#authentication)
            * [Ottenere le credenziali](general/users/azure.html#gather-credentials)
          * [Configurare Odoo](general/users/azure.html#odoo-setup)
          * [Flussi esperienza utente](general/users/azure.html#user-experience-flows)
      * [Autenticazione LDAP](general/users/ldap.html)
  * [Aziende](general/companies.html)
    * Gestire aziende e record
      * [Passare da un’azienda all’altra](general/companies.html#switch-between-companies)
      * [Condividere record](general/companies.html#share-records)
    * [Filiali](general/companies.html#branches)
    * [Accesso dipendenti](general/companies.html#employee-access)
    * [Formato documenti](general/companies.html#document-format)
    * Transazioni interaziendali
      * E-mail di riepilogo
        * [Personalizzare e-mail di riepilogo predefinite](general/companies/digest_emails.html#customize-default-digest-email)
        * [Disattivare le e-mail di riepilogo](general/companies/digest_emails.html#deactivate-digest-email)
        * [Inviare e-mail di riepilogo manualmente](general/companies/digest_emails.html#manually-send-digest-email)
        * [KPI](general/companies/digest_emails.html#kpis)
        * [Destinatari](general/companies/digest_emails.html#recipients)
        * [Creare e-mail di riepilogo](general/companies/digest_emails.html#create-digest-emails)
        * ICP personalizzati con Odoo Studio
          * [Tabella di riferimento valori calcolati](general/companies/digest_emails.html#computed-values-reference-table)
      * Modelli e-mail
        * Modificare i modelli e-mail
          * [Powerbox](general/companies/email_template.html#powerbox)
          * [Editor di codice XML/HTML](general/companies/email_template.html#xml-html-code-editor)
          * [Segnaposto dinamici](general/companies/email_template.html#dynamic-placeholders)
          * [Editor di testi ricco di funzionalità](general/companies/email_template.html#rich-text-editor)
          * [Ripristinare i modelli e-mail](general/companies/email_template.html#resetting-email-templates)
          * [Risposte predefinite nei modelli e-mail](general/companies/email_template.html#default-reply-on-email-templates)
        * E-mail di transazione e URL corrispondenti
          * [Aggiornare le traduzioni nei modelli e-mail](general/companies/email_template.html#updating-translations-within-email-templates)
  * Multi-azienda
    * Accedere a più aziende
      * [Più aziende attive](general/multi_company.html#multiple-active-companies)
    * Condividere dati
      * [Prodotti](general/multi_company.html#products)
      * [Contatti](general/multi_company.html#contacts)
    * [Transazioni interaziendali](general/multi_company.html#inter-company-transactions)
    * Casi d’uso
      * [Aziende multinazionali](general/multi_company.html#multinational-companies)
      * [Processi separati](general/multi_company.html#separate-processes)
    * Limitazioni
      * [Diritti di accesso](general/multi_company.html#access-rights)
      * [Record condivisi](general/multi_company.html#shared-records)
      * [Reportistica in PDF](general/multi_company.html#pdf-reports)
  * [Internet delle cose (IoT)](general/iot.html)
    * Abbonamento box IoT
      * Box IoT
        * Connessione alla rete
          * [Ethernet](general/iot/iot_box.html#ethernet)
          * [Wi-Fi](general/iot/iot_box.html#wi-fi)
        * [Pagina principale box IoT](general/iot/iot_box.html#iot-box-homepage)
      * Windows virtual IoT
        * [Prerequisiti](general/iot/windows_iot.html#prerequisites)
        * [Installazione](general/iot/windows_iot.html#installation)
        * [Configurazione Firewall Windows](general/iot/windows_iot.html#windows-firewall-configuration)
        * [Pagina principale Windows virtual IoT](general/iot/windows_iot.html#windows-virtual-iot-homepage)
        * [Collegare dispositivi](general/iot/windows_iot.html#device-connection)
        * [Riavviare Windows virtual IoT](general/iot/windows_iot.html#windows-virtual-iot-restart)
        * [Disinstallare Windows virtual IoT](general/iot/windows_iot.html#windows-virtual-iot-uninstall)
      * Conessione sistema IoT a Odoo
        * [Prerequisiti](general/iot/connect.html#prerequisites)
        * Connessione
          * [Connessione con un codice di abbinamento](general/iot/connect.html#connection-using-a-pairing-code)
          * [Connessione con un token](general/iot/connect.html#connection-using-a-connection-token)
        * [Modulo sistema IoT](general/iot/connect.html#iot-system-form)
        * Risoluzione problemi
          * [Il codice di abbinamento non appare o non funziona](general/iot/connect.html#the-pairing-code-does-not-appear-or-does-not-work)
          * [Sistema IoT collegato ma non appare nel database](general/iot/connect.html#the-iot-system-is-connected-but-does-not-appear-in-the-database)
          * [Box IoT collegata al database Odoo ma non raggiungibile](general/iot/connect.html#the-iot-box-is-connected-to-the-odoo-database-but-cannot-be-reached)
          * [Pagina principale Windows virtual IoT non accessibile da un altro dispositivo](general/iot/connect.html#the-windows-virtual-iot-s-homepage-cannot-be-accessed-from-another-device)
          * [Sistema IoT scolelgato dal database dopo l’aggiornamento di Odoo](general/iot/connect.html#the-iot-system-is-disconnected-from-the-database-after-an-odoo-upgrade)
      * Avanzato
        * Certificato HTTPS (IoT)
          * [Creazione certificato HTTPS](general/iot/iot_advanced/https_certificate_iot.html#https-certificate-generation)
          * Errori e problemi legati alla generazione del certificato HTTPS
            * [Certificato HTTPS non generato](general/iot/iot_advanced/https_certificate_iot.html#the-https-certificate-does-not-generate)
            * [Accesso alla pagina principale del sistema IoT tramite indirizzo IP ma non via URL `xxx.odoo-iot.com`](general/iot/iot_advanced/https_certificate_iot.html#the-iot-system-s-homepage-can-be-accessed-using-its-ip-address-but-not-the-xxx-odoo-iot-com-url)
            * Errori
              * [`ERR_IOT_HTTPS_CHECK_NO_SERVER`](general/iot/iot_advanced/https_certificate_iot.html#err-iot-https-check-no-server)
              * [`ERR_IOT_HTTPS_CHECK_CERT_READ_EXCEPTION`](general/iot/iot_advanced/https_certificate_iot.html#err-iot-https-check-cert-read-exception)
              * [`ERR_IOT_HTTPS_LOAD_NO_CREDENTIAL`](general/iot/iot_advanced/https_certificate_iot.html#err-iot-https-load-no-credential)
              * [`ERR_IOT_HTTPS_LOAD_REQUEST_EXCEPTION`](general/iot/iot_advanced/https_certificate_iot.html#err-iot-https-load-request-exception)
              * [`ERR_IOT_HTTPS_LOAD_REQUEST_STATUS`](general/iot/iot_advanced/https_certificate_iot.html#err-iot-https-load-request-status)
              * [`ERR_IOT_HTTPS_LOAD_REQUEST_NO_RESULT`](general/iot/iot_advanced/https_certificate_iot.html#err-iot-https-load-request-no-result)
        * Aggiornamenti sistema IoT
          * [Aggiornamento immagine e codice principale](general/iot/iot_advanced/updating_iot.html#image-and-core-code-update)
          * [Aggiornamento gestore (driver)](general/iot/iot_advanced/updating_iot.html#handler-driver-update)
        * [Connessione SSH box IoT](general/iot/iot_advanced/ssh_connect.html)
      * [Dispositivi](general/iot/devices.html)
        * Collegare uno schermo
          * [Connessione](general/iot/devices/screen.html#connection)
          * Utilizzo
            * [Mostrare gli ordini del Punto vendita ai clienti](general/iot/devices/screen.html#show-point-of-sale-orders-to-customers)
            * [Visualizzare un sito web sullo schermo](general/iot/devices/screen.html#display-a-website-on-the-screen)
        * Collegare uno strumento di misura
          * [Collegamento USB](general/iot/devices/measurement_tool.html#connect-with-universal-serial-bus-usb)
          * [Collegamento via bluetooth](general/iot/devices/measurement_tool.html#connect-with-bluetooth)
          * [Collegare uno strumento di misura a un punto di controllo qualità nel processo di produzione](general/iot/devices/measurement_tool.html#link-a-measurement-tool-to-a-quality-control-point-in-the-manufacturing-process)
          * [Collegare uno strumento di misura a un centro di lavoro nell’app Produzione](general/iot/devices/measurement_tool.html#link-a-measurement-tool-to-a-work-center-in-the-manufacturing-app)
        * Collegare una fotocamenra
          * [Connessione](general/iot/devices/camera.html#connection)
          * [Collegare la fotocamera a un punto di controllo qualità per il processo di produzione](general/iot/devices/camera.html#link-camera-to-quality-control-point-in-manufacturing-process)
          * [Collegare la fotocamera a un centro di lavoro nell’app Produzione](general/iot/devices/camera.html#link-camera-to-a-work-center-in-the-manufacturing-app)
        * Collegare un sensore a pedale
          * [Connessione](general/iot/devices/footswitch.html#connection)
          * [Collegare un sensore a pedale a un centro di lavoro nell’app Produzione di Odoo](general/iot/devices/footswitch.html#link-a-footswitch-to-a-work-center-in-the-odoo-manufacturing-app)
        * Collegare una stampante
          * [Connessione](general/iot/devices/printer.html#connection)
          * Collegare una stampante
            * [Collegare ordini di lavoro a una stampante](general/iot/devices/printer.html#link-work-orders-to-a-printer)
            * Collegare resoconti a una stampante
              * [Cancella la cache della stampante del dispositivo](general/iot/devices/printer.html#clear-device-printer-cache)
          * Potenziali problemi
            * [La stampante non viene individuata](general/iot/devices/printer.html#the-printer-is-not-detected)
            * [La stampante emette un testo casuale](general/iot/devices/printer.html#the-printer-outputs-random-text)
            * La stampante viene individuata ma non riconosciuta correttamente
              * [Casi speciali configurazione Epson](general/iot/devices/printer.html#epson-configuration-special-case)
            * Problema di stampa DYMO LabelWriter
              * [DYMO LabelWriter non stampa](general/iot/devices/printer.html#dymo-labelwriter-not-printing)
              * [Ritardo stampa DYMO LabelWriter](general/iot/devices/printer.html#dymo-labelwriter-print-delay)
            * [La stampante Zebra non stampa nulla](general/iot/devices/printer.html#the-zebra-printer-does-not-print-anything)
          * Problemi lettore codici a barre
            * [I caratteri letti dal lettore di codici a barre non corrispondono al codice a barre](general/iot/devices/printer.html#the-characters-read-by-the-barcode-scanner-do-not-match-the-barcode)
            * [Non accade nulla al momento della scansione di un codice a barre](general/iot/devices/printer.html#nothing-happens-when-a-barcode-is-scanned)
            * [Il lettore di codici a barre viene rilevato come tastiera](general/iot/devices/printer.html#the-barcode-scanner-is-detected-as-a-keyboard)
            * [Il lettore di codici a barre elabora i caratteri del codice singolarmente](general/iot/devices/printer.html#the-barcode-scanner-processes-barcode-characters-individually)
        * Collegare una bilancia
          * [Bilance Ariva S](general/iot/devices/scale.html#ariva-s-scales)
  * [Comunicazione in Odoo via e-mail](general/email_communication.html)
    * Utenti Odoo online e Odoo.sh
      * [Utilizzare un altro dominio](general/email_communication.html#using-another-domain)
    * [Utenti on-premise](general/email_communication.html#on-premise-users)
    * Utilizzare un server e-mail fornito da terze parti
      * Gestire messaggi in entrata
        * Alias e-mail
          * [Alias specifici per modello](general/email_communication/email_servers_inbound.html#model-specific-aliases)
          * [Catchall](general/email_communication/email_servers_inbound.html#catchall)
          * [Rimbalzo](general/email_communication/email_servers_inbound.html#bounce)
        * [Ricevere e-mail con la configurazione predefinita di Odoo](general/email_communication/email_servers_inbound.html#receive-emails-with-odoo-s-default-configuration)
        * [Usa sottodomini Odoo multipli](general/email_communication/email_servers_inbound.html#use-multiple-odoo-subdomains)
        * Utilizzare un dominio personalizzato per i messaggi in entrata
          * [Reindirizzamento](general/email_communication/email_servers_inbound.html#redirections)
          * [Server e-mail in entrata](general/email_communication/email_servers_inbound.html#incoming-mail-servers)
          * [Record MX](general/email_communication/email_servers_inbound.html#mx-record)
        * [Loop e-mail infiniti](general/email_communication/email_servers_inbound.html#infinite-email-loops)
        * [Autorizzare i parametri di sistema del dominio alias](general/email_communication/email_servers_inbound.html#allow-alias-domain-system-parameter)
        * [Rilevamento dell’arrivo di una parte locale](general/email_communication/email_servers_inbound.html#local-part-based-incoming-detection)
      * Gestire messaggi in uscita
        * [Inviare e-mail con la configurazione predefinita di Odoo](general/email_communication/email_servers_outbound.html#sending-emails-with-odoo-s-default-configuration)
        * Utilizzare un dominio personalizzato per inviare e-mail
          * [Utilizzare un dominio personalizzato con server e-mail di Odoo](general/email_communication/email_servers_outbound.html#using-a-custom-domain-with-odoos-email-server)
          * Inviare e-mail con un server SMTP esterno
            * [Valori della parte locale](general/email_communication/email_servers_outbound.html#local-part-values)
        * Configurare server diversi per e-mail di transazione e di massa
          * Server e-mail personalizzati
            * [Filtro mittente](general/email_communication/email_servers_outbound.html#from-filtering)
          * [Utilizzare un server e-mail esterno e il server predefinito di Odoo](general/email_communication/email_servers_outbound.html#using-an-external-email-server-and-odoos-default-server)
        * [Utilizzare un dominio personalizzato con un server e-mail esterno](general/email_communication/email_servers_outbound.html#using-a-custom-domain-with-an-external-email-server)
        * [Restrizione Port](general/email_communication/email_servers_outbound.html#port-restriction)
        * [Dominio alias](general/email_communication/email_servers_outbound.html#alias-domain)
        * [Sistema di notifica](general/email_communication/email_servers_outbound.html#notification-system)
        * [Utilizzare un unico indirizzo e-mail per e-mail in uscita](general/email_communication/email_servers_outbound.html#using-a-unique-email-address-for-all-outgoing-emails)
      * Configurare record DNS per inviare e-mail in Odoo
        * [SPF (Sender Policy Framework)](general/email_communication/email_domain.html#spf-sender-policy-framework)
        * [DKIM (DomainKeys Identified Mail)](general/email_communication/email_domain.html#dkim-domainkeys-identified-mail)
        * [DMARC (Domain-based Message Authentication, Reporting and Conformance)](general/email_communication/email_domain.html#dmarc-domain-based-message-authentication-reporting-and-conformance)
        * [Documentazione SPF, DKIM e DMARC di fornitori comuni](general/email_communication/email_domain.html#spf-dkim-and-dmarc-documentation-of-common-providers)
      * Collegare Microsoft Outlook 365 a Odoo utilizzando Azure OAuth
        * Configurazione nel portale Microsoft Azure
          * [Creare una nuova applicazione](general/email_communication/azure_oauth.html#create-a-new-application)
          * [Autorizzazioni API](general/email_communication/azure_oauth.html#api-permissions)
        * Assegnare utenti e gruppi
          * [Creare credenziali](general/email_communication/azure_oauth.html#create-credentials)
        * Installazione in Odoo
          * [Inserire le credenziali Microsoft Outlook](general/email_communication/azure_oauth.html#enter-microsoft-outlook-credentials)
          * Configurare server e-mail in uscita
            * [Configurazione con un signolo server e-mail in uscita](general/email_communication/azure_oauth.html#configuration-with-a-single-outgoing-mail-server)
            * Configurazione specifica per l’utente (utenti multipli)
              * [Imposta](general/email_communication/azure_oauth.html#setup)
          * [Configurare server e-mail in entrata](general/email_communication/azure_oauth.html#configure-incoming-email-server)
      * Collegare Gmail a Odoo utilizzando Google OAuth
        * Installazione in Google
          * [Creare un nuovo progetto](general/email_communication/google_oauth.html#create-a-new-project)
          * [Schermata di consenso OAuth](general/email_communication/google_oauth.html#oauth-consent-screen)
          * [Modificare la registrazione dell’applicazione](general/email_communication/google_oauth.html#edit-app-registration)
          * [Creare credenziali](general/email_communication/google_oauth.html#create-credentials)
        * Installazione in Odoo
          * [Inserire le credenziali Google](general/email_communication/google_oauth.html#enter-google-credentials)
          * [Configurare server e-mail in uscita](general/email_communication/google_oauth.html#configure-outgoing-email-server)
        * FAQ Google OAuth
          * [Produzione vs test stato pubblicazione](general/email_communication/google_oauth.html#production-vs-testing-publishing-status)
          * [Nessun utente di prova aggiunto](general/email_communication/google_oauth.html#no-test-users-added)
          * [Modulo Gmail non aggiornato](general/email_communication/google_oauth.html#gmail-module-not-updated)
          * [Tipo di applicazione](general/email_communication/google_oauth.html#application-type)
      * API Mailjet
        * Configurazione in Mailjet
          * [Creare credenziali API](general/email_communication/mailjet_api.html#create-api-credentials)
          * [Aggiungere indirizzi mittente verificati](general/email_communication/mailjet_api.html#add-verified-sender-address-es)
          * Aggiungere un dominio
            * [Configurazione nel DNS del dominio](general/email_communication/mailjet_api.html#setup-in-the-domain-s-dns)
            * [Tornare alle informazioni dell’account Mailjet](general/email_communication/mailjet_api.html#return-to-mailjet-account-information)
        * [Configurazione in Odoo](general/email_communication/mailjet_api.html#set-up-in-odoo)
      * Problemi e-mail comuni e soluzioni
        * [Odoo non è un fornitore di servizi e-mail](general/email_communication/faq.html#odoo-is-not-an-email-provider)
        * E-mail in uscita
          * [Modificare l’indirizzo e-mail dell’account utente amministratore](general/email_communication/faq.html#changing-the-email-address-of-the-admin-user-account)
          * Errore nella consegna
            * Messaggi di errore comuni
              * [Limite giornaliero raggiunto](general/email_communication/faq.html#daily-limit-reached)
              * [Errore SMTP](general/email_communication/faq.html#smtp-error)
              * [Nessun errore popolato](general/email_communication/faq.html#no-error-populated)
          * Tempo di esecuzione
            * [Campagne E-mail marketing bloccate nella coda](general/email_communication/faq.html#email-marketing-campaigns-stuck-in-the-queue)
        * E-mail in arrivo
          * [E-mail non ricevuta](general/email_communication/faq.html#email-is-not-received)
        * [Informazioni per il supporto Odoo](general/email_communication/faq.html#information-for-odoo-support)
  * Integrazioni
    * [Plugin e-mail](general/integrations/mail_plugins.html)
      * Plug-in Outlook
        * Configurazione
          * [Abilitare il plug-in e-mail](general/integrations/mail_plugins/outlook.html#enable-mail-plugin)
          * [Installare il plug-in Outlook](general/integrations/mail_plugins/outlook.html#install-the-outlook-plugin)
          * [Collegare il database](general/integrations/mail_plugins/outlook.html#connect-the-database)
          * [Aggiungere una scorciatoia al plug-in](general/integrations/mail_plugins/outlook.html#add-a-shortcut-to-the-plugin)
          * [Utilizzare il plug-in](general/integrations/mail_plugins/outlook.html#using-the-plugin)
      * Plugin Gmail
        * Utenti Odoo online
          * [Installare il plugin Gmail](general/integrations/mail_plugins/gmail.html#install-the-gmail-plugin)
          * [Configurare il database Odoo](general/integrations/mail_plugins/gmail.html#configure-the-odoo-database)
          * [Configurare la casella di posta Gmail](general/integrations/mail_plugins/gmail.html#configure-the-gmail-inbox)
        * Utenti Odoo on premise
          * [Installare il plugin Gmail](general/integrations/mail_plugins/gmail.html#id1)
          * [Configurare il database Odoo](general/integrations/mail_plugins/gmail.html#id2)
          * [Configurare la casella di posta Gmail](general/integrations/mail_plugins/gmail.html#id3)
      * Tariffazione
        * [Servizio IAP generazione lead](general/integrations/mail_plugins.html#lead-generation-iap-service)
    * [Unsplash](general/integrations/unsplash.html)
    * [Geolocalizzazione](general/integrations/geolocation.html)
    * Google Traduttore
      * Console Google API
        * [Creare un nuovo progetto](general/integrations/google_translate.html#create-a-new-project)
        * [Libreria API](general/integrations/google_translate.html#api-library)
        * [Creare credenziali](general/integrations/google_translate.html#create-credentials)
      * [Configurazione Odoo](general/integrations/google_translate.html#odoo-configuration)
      * [Tradurre nel chatter](general/integrations/google_translate.html#translate-chatter)
  * Modalità sviluppatore (modalità di debug)
    * [Attivazione](general/developer_mode.html#activation)
    * [Strumenti di sviluppo e menu tecnico](general/developer_mode.html#developer-tools-and-technical-menu)



[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/general.rst)

### Navigazione

  * [indice](../genindex.html "Indice generale")
  * [moduli](../py-modindex.html "Indice del modulo Python") |
  * [successivo](general/apps_modules.html "App e Moduli") |
  * [precedente](studio/approval_rules.html "Regole di approvazione") |
  * [Odoo 17.0 documentazione](../index-2.html) »
  * [Documentazione Utente](../applications.html) »
  * Impostazioni generali


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