# WhatsApp — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](voip.html "VoIP \(Voice over Internet Protocol\)") |
  * [precedente](data_cleaning.html "Pulizia dati") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
  * [Produttività](../productivity.html) »
  * WhatsApp



# WhatsApp¶

**WhatsApp** is an instant messaging and voice-over-IP app that allows users to send messages, make calls, and share content. Businesses can use [WhatsApp Business](https://developers.facebook.com/products/whatsapp/) to communicate with their customers by text, send documents and provide support.

Avvertimento

WhatsApp is an Odoo Enterprise-only application that does not work in Odoo Community edition. To sign up for Odoo Enterprise edition, click here: [Odoo Free Trial](https://www.odoo.com/trial).

Vedi anche

For more information on migrating from Odoo Community version to Odoo Enterprise version see this documentation: [Passare da Community a Enterprise](../../administration/on_premise/community_to_enterprise.html).

With the **Odoo WhatsApp** app, a company can connect a WhatsApp Business Account (WABA) to an Odoo database, which allows for the following:

  * Receive and reply to WhatsApp messages directly from an Odoo database

  * Create new templates with dynamic placeholders/variables

  * Send pre-approved templates that use dynamic variables, such as:

    * Quotations from the **Sales** app

    * Receipts and invoices from the **Point of Sale** app

    * Tickets from the **Events** app




Vedi anche

  * [Meta Business: create message templates for the WhatsApp Business account](https://www.facebook.com/business/help/2055875911147364).

  * [Meta Business: connect a phone number to the WhatsApp Business account](https://www.facebook.com/business/help/456220311516626).

  * [Meta Business: change the WhatsApp Business display name](https://www.facebook.com/business/help/378834799515077).




WhatsApp is a messaging service operated by Meta, which is the parent company of Facebook. WhatsApp is commonly used as a communication tool in many countries and by many businesses. This documentation will cover the integration of a WhatsApp Business Account with Odoo. The company’s Meta account is configured in Odoo via an API connection.

The WhatsApp connector supports two flows: company initiated, and customer initiated. A company can initiate a discussion by sending a template to one or more people. Once the template is sent, the recipient can answer in order to trigger a discussion between the sender and the receiver (a **Discuss** chat window appears if the customer answers within 15 days).

If the discussion is initiated by the client (e.g. by sending to the company’s public WhatsApp number), then Odoo will open a group chat with all operators responsible for this WhatsApp channel.

Suggerimento

It is recommended to set up multiple WhatsApp accounts for different departments. For example, the help desk team and sales teams can chat on different channels.

Vedi anche

[`Magic Sheet - WhatsApp configuration PDF`](../../_downloads/11ce28a681218b0096ef936c639d798d/magic-sheet-whatsapp.pdf)

## WhatsApp configuration in a Meta¶

A WhatsApp integration with Odoo uses a standard API connection, and is configured on Meta in the following steps:

  1. Create a Meta business account

  2. Create a Meta developer account

  3. Setup an _app_ and WhatsApp _product_ on Meta’s developer console

  4. Test the API connection.




Once connected, messages are then sent and received through Odoo’s _Discuss_ application using the WhatsApp API.

### Meta business account setup¶

To create a Business account with Meta (owner of Facebook) navigate to: [Facebook Business Manager](https://business.facebook.com/overview). Begin by clicking Create account and then enter the business name, the administrator’s name, and a work email address. Then click Next, and a pop-up window will appear prompting to confirm the email address. After confirming, click Done to close the window.

Next, follow the instructions in the email sent by Facebook to confirm the creation of the business account and to complete the setup process.

Vedi anche

[Set up a Meta business account](https://www.facebook.com/business/help/1710077379203657?id=180505742745347).

Importante

If the business account is linked to a personal Facebook account then the administrator must toggle between the personal account to the business account for the remainder of the configuration.

To toggle to the business account navigate to the [Facebook Developer Console](https://developers.facebook.com/) and click on the _account name_ in the upper right corner. Under the Business Accounts heading, click on the desired business that the WhatsApp configuration should take place in. This is the account for which Odoo will send and receive WhatsApp messages.

Importante

In order to create a Meta business account, the user must already have a personal Facebook account that has existed for a minimum of one hour prior to setting up the Facebook Business account. Trying to create the business account prior to this time will result in an error.

### App creation¶

On the [Meta for Developers](https://developers.facebook.com/) dashboard, sign in with the Meta developer account. If no account is configured yet, link a Facebook account to create a Meta developer account.

Nota

A Facebook _developer_ account is different than a Facebook _business_ account. While developer accounts are made up of personal Facebook accounts, business accounts are **not** as they represent a business and manage all of the business’s assets in Meta, such as apps.

Vedi anche

[Set up the WhatsApp Business Platform](https://www.facebookblueprint.com/student/collection/409587/path/360218).

Click on My Apps in the top-right corner after successfully signing in to the Meta developer account. This will redirect the administrator to all the apps the developer has configured in this specific developer account. Click on Create App to begin the process of configuring a new Meta application.

### App type¶

On the Create an app page, select Other under the section labeled, Looking for something else?, and then click Next to be directed to another page in order to select the app type. Then, click on the first option listed under the Select an app type label, titled Business. This selection allows for the creation and management of the WhatsApp API.

Now, click Next to configure the app, as desired. When the app _type_ has been configured, the administrator will move onto the app _details_ section.

### App details¶

On the Details section of the Create an app process, enter `Odoo` in the field under the Add an app name label.

Nota

The app name can be changed at a later time in the settings, if necessary.

Avvertimento

Trademarks and branded elements may not be used in this text section. These include the Meta group of companies. Do not include the word: `WhatsApp` or the system will flag this in error.

Next, enter the developer email address in the field under the App contact email label.

Lastly, set the Business Account - Optional field to the Meta business account profile, using the drop-down menu. To finish, click Create app. This action will create the app and prompts the _Meta Platform Terms_ and _Developer Policies_ agreements.

To accept the agreements, enter the Facebook password for security purposes, and click Submit to finalize the app creation. The browser will then direct to the Meta for Developers dashboard.

Nota

If the Meta business account is prohibited from advertising, claiming an app is not allowed. To resolve this issue navigate to <https://business.facebook.com/business> for assistance.

For more information, see [Meta’s documentation on advertising restrictions](https://www.facebook.com/business/help/975570072950669).

### Add a WhatsApp product to the app¶

Now that the basic structure of the app has been created, a product will need to be added to the app. Begin by accessing the Meta app dashboard by navigating to <https://developers.facebook.com/apps>, and clicking on the app that is being configured.

On the next page: since WhatsApp is used, click Set up next to the box containing WhatsApp, located towards the bottom of the page.

Vedi anche

[Meta’s WhatsApp developer documentation](https://developers.facebook.com/docs/whatsapp/).

The page then directs to the configuration page for the WhatsApp Business Platform API. Use the drop-down menu to select the Meta business to be configured for the Select a Meta Business Account option, and then click Continue to confirm the selection.

Nota

When Continue is clicked, the administrator agrees to Meta’s terms and conditions as linked on the Meta App Dashboard.

Nota

Once the WhatsApp product is added to the app, Meta will provide a WhatsApp test phone number with 5 test messages.

### Start using the WhatsApp API¶

After finishing the previous WhatsApp product wizard, and clicking Continue, the browser should have directed to the WhatsApp Quickstart page; this Quickstart page is where to begin configuring the WhatsApp API by adding a phone number and then sending an initial test message.

Nota

If the browser is not on the Quickstart page for WhatsApp, navigate to <https://developers.facebook.com/apps> and click on the app that is being configured, (the app name is `Odoo` if the instructions above were followed).

Then, in the menu on the left-hand side of the page, click the v (menu toggle) icon next to the WhatsApp section heading. A small menu will open, containing the following options:

  * Quickstart

  * API Setup

  * Configuration




Click the Quickstart option, and then click Start using the API.

#### API Setup¶

After clicking on Start using the API, the page navigates to the API Setup. Now that the test number has been created, a test message can be sent to confirm that WhatsApp is working properly. To begin, navigate to the section on the page labeled Send and receive messages and click the drop-down menu next to To, under Step 1 Select phone numbers.

Now, select the only option available: Manage phone number list. Follow the steps and add up to five numbers to send the free test messages to. After entering the appropriate country code and phone number, click on Next.

Importante

Adding a phone number to send to in this step will allow for a successful test to be sent by the terminal. This is critical to ensure the WhatsApp API is working.

A verification code from WhatsApp Business is then sent to the phone number, which needs to be input on the next screen to verify ownership of the number. Enter the verification code and click Next to verify the number.

#### Send a test message via terminal¶

Next, send a test message via the terminal. Under the section labeled Step 2 Send messages with the API, click Send Message. A test message will then be sent to the phone number that was set in the previous section.

Upon successfully receiving the message to the number, move onto the next section to produce and configure webhooks.

## WhatsApp configuration in Odoo¶

The next steps configured in this section are all within the Odoo database. A few different values for a token, phone number, and account IDs all need to be configured in Odoo; these values are necessary in order to create a Callback URL and Webhook Verify Token, which are then used to configure the webhooks (in order to receive messages back into the database).

In Odoo, navigate to WhatsApp app ‣ Configuration ‣ WhatsApp Business Accounts. Then click New to configure the WhatsApp business account in Odoo.

In another browser tab, navigate to https://developers.facebook.com ‣ My Apps ‣ WhatsApp ‣ API Configuration, and then copy the following values from the Meta developer console into the corresponding fields in Odoo:

Nome | Meta Console | Odoo Interface  
---|---|---  
Telefono | Phone number ID | Phone Number ID  
Token | Temporary access token | Access Token  
ID app | App ID | App ID  
ID account | WhatsApp Business Account ID | Account ID  
  
To retrieve the App Secret, navigate to the Meta developer console, <https://developers.facebook.com/apps> and select the app that Odoo is being configured in. Then in the left-side menu, under App settings, select Basic.

Next, click Show next to the field App secret, and enter the account password to verify ownership. Copy the App secret and then paste that copied value into the App Secret field on the Odoo WhatsApp Business Account configuration dashboard.

To complete the setup of the WhatsApp business account in Odoo, click Test Connection. A successful message in green will populate in the upper-right corner of the dashboard if the configuration is set correctly.

### Configuring webhooks¶

To configure the webhooks for WhatsApp in Odoo, navigate to <https://developers.facebook.com/apps> and select the app that Odoo is being configured in. Next under the WhatsApp menu heading on the left side of the screen, click on the API Setup menu item. Finally go to the section marked Step 3: Configure webhooks to receive messages and click on Configure webhooks.

Suggerimento

Another way to configure _Webhooks_ is to navigate to <https://developers.facebook.com/apps> and select the app that Odoo is being configured in. Then select Webhooks in the left hand menu.

On the Webhook configuration page, click on Edit, where both the Callback URL and Webhook Verify Token values from Odoo are added.

Nota

Both the Callback URL and Webhook Verify Token values were automatically populated after clicking on Test Connection in the previous step.

In a separate browser window, retrieve the necessary values in Odoo by navigating to WhatsApp app ‣ Configuration ‣ WhatsApp Business Accounts and select the account that is being configured. Locate the values under the section labeled Receiving Messages.

Copy and paste the Callback URL from Odoo into the Callback URL field in Meta. Similarly, copy and paste the Webhook Verify Token into the Verify Token field on the Meta developer console, as well.

Finally, click Verify and save to record the values in the Meta developer console.

#### Webhook fields¶

Now input individual webhook fields into Meta’s developer console, under the Webhook fields section. Click Manage and when the pop-up window appears, check the boxes in the Subscribe column for the following field names:

  * `account_update`

  * `message_template_quality_update`

  * `message_template_status_update`

  * `messages`

  * `template_category_update`




After making the selections, click Done.

The finished Webhooks configuration will appear like this in the Meta developer console:

Importante

The Webhook fields will only appear once the subscription is confirmed using the Callback URL and Webhook Verify Token.

Vedi anche

[Meta’s WhatsApp documentation on setting webhooks](https://developers.facebook.com/docs/whatsapp/cloud-api/guides/set-up-webhooks).

#### Add phone number¶

To configure the phone number to use for WhatsApp in Odoo, navigate back to the Meta developer console (<https://developers.facebook.com/apps>) and again select the app that Odoo is being configured in. Under the WhatsApp menu heading on the left side of the screen, click on the API Setup menu item. From there, go to the section marked: Step 5: Add a phone number, and click on Add phone number.

In the fields, enter a Business name as well as a Business website or profile page.

Suggerimento

The Business website or profile page field can be a social media page’s URL.

Complete filling out the business information by next selecting the country that the company does business in from the drop-down menu in the Country section. Add an address if desired, however, this information is optional. After adding the location, click Next to continue.

The following page contains information for the WhatsApp Business profile. Complete the following sections, accordingly:

  * WhatsApp Business Profile Display Name

  * Timezone

  * Category

  * Business description (optional)




Once these sections are complete, click Next. The page refreshes and then prompts the administrator to Add a phone number for WhatsApp in the respective field. Here, enter the phone number to configure in WhatsApp.

Vedi anche

[Migrate an Existing WhatsApp Number to a Business Account](https://developers.facebook.com/docs/whatsapp/cloud-api/get-started/migrate-existing-whatsapp-number-to-a-business-account).

Next, choose a verification method for the phone number. Select either Text message or Phone call, and then click Next proceed.

The phone number entered will receive either a text or a phone call by WhatsApp with a code, depending on the verification method chosen. Enter that verification code into the Verification code field and click Next to finish.

Avvertimento

If a payment method has not been added, this is necessary to proceed. [Visit Meta’s documentation on how to add a payment method in Meta’s Business Manager](https://www.facebook.com/business/help/915454841921082?id=180505742745347). This is part of Meta’s fraud detection system, in order to ensure that the account/company are real a payment method is required to proceed.

Vedi anche

[Meta for Developers: Add a Phone Number](https://developers.facebook.com/docs/whatsapp/cloud-api/get-started/add-a-phone-number).

#### Permanent token¶

After configuration and testing are complete, a permanent token should be created to replace the Temporary token.

Vedi anche

[Meta for Developers: System User Access Tokens](https://developers.facebook.com/docs/whatsapp/business-management-api/get-started#system-user-access-tokens).

Begin by navigating to <https://business.facebook.com/> and then go to Business settings ‣ User ‣ System Users. Select an existing system user or create a new system user by clicking on Add.

Assets now must be added to the system user and then a permanent token can be generated.

Avvertimento

This is a mandatory step. If the permanent token is not added, the Odoo database shows a token error.

Click on Add assets, and when the pop-up window appears select Apps under the Select asset type. Then, select the Odoo app and toggle the permissions to _On_ under the Full control option. Set this new permission setting by clicking Save Changes, to which a confirmation window will appear, acknowledging the addition of the asset to the system user. Finish by clicking Done.

Next, the permanent token gets generated. Click on Generate new token, and a pop-up window will appear asking which app this token should be generated for. Select the App that this token is for. Then determine the expiration date of either 60 days or Never.

Finally, when Meta asks which permissions should the system user allow, add all of the following permissions:

  * `business_management`

  * `whatsapp_business_messaging`

  * `whatsapp_business_management`




When permissions are set, click Generate token. Copy the token value that populates on the screen that follows.

With that token value, update the Access Token field in the WhatsApp business account in Odoo by navigating to WhatsApp app ‣ Configuration ‣ WhatsApp Business Accounts.

## Go live with the Meta app¶

Finally, to launch the app, the Meta app must be set to Live in the Meta developer console. Navigate to <https://developers.facebook.com/apps> and click on the app that is being configured. In the top menu, toggle the App Mode field from Development to Live.

Importante

If the app status is not set to _live_ , then the database will only be able to contact the test numbers specified in the developer console.

Avvertimento

A privacy policy URL must be set in order for the app to be set to live. Go to the Meta developer console, <https://developers.facebook.com/apps> and select the app that Odoo is being configured in. Then, using the menu on the left side of the screen, go to App Settings ‣ Basic. Then, enter the privacy policy hyperlink address under the Privacy Policy URL field of the form. Click Save changes to apply the privacy policy to the app.

Once the app has gone live in the Meta developer console, a confirmation email is sent to the administrator.

## WhatsApp templates¶

WhatsApp templates are saved messages that are used repeatedly to send messages from the database. They allow users to send quality communications, without having to compose the same text repeatedly.

La creazione di modelli diversi realizzati su misura per situazioni specifiche permette agli utenti di scegliere il messaggio giusto per il pubblico giusto. Tutto questo permette di aumentare la qualità del messaggio e il tasso di coinvolgimento con il cliente.

WhatsApp templates can be created on both the Odoo and Meta consoles. The following process will overview the process for creating templates in Odoo and then afterward in Meta.

Importante

WhatsApp has an approval process that must be completed before the template can be used. Meta template approval.

### Creating templates in Odoo¶

To access and create WhatsApp templates, begin by navigating to the WhatsApp app ‣ Templates dashboard.

At the bottom of an individual template’s form, there are three tabs: Body, Buttons, and Variables; these three tabs combined create the WhatsApp template.

The text is entered into the Body tab, and dynamic content that is called out in the Body tab is specified in the Variables tab. Every piece of dynamic content (e.g., placeholders) in the message (body) is specifically called out and specified in the Variables tab.

Templates are prefabricated layouts that allow users to send professional looking messages to customers. These templates are capable of containing dynamic data that will populate in the end message using variables that are set in the template configuration. For example, messages can contain the end user’s name, call out specific products, or reference a sales order, to name a few convenient and impactful variables.

To create a WhatsApp template, go to the WhatsApp app ‣ Templates dashboard and click New. On the form, enter a Name for the template, and select a Language.

Importante

In order to complete this next task, administrator access rights are needed to edit the Applies to field. See this [access rights documentation](../general/users/access_rights.html) for more information.

In the Account drop-down menu, select the _WhatsApp business account_ in Odoo that this template should link to. Next, under the Applies to field select the _model_ the server action will apply to for this template.

Suggerimento

These models can also be accessed in [developer mode](../general/developer_mode.html#developer-mode). On a contact form (or similar relevant form in Odoo), navigate to the model that is referenced, and hover over any field name. A box of backend information will reveal itself with the specific Odoo Model name in the backend. Search (using the front-end name) for this model in the Applies to drop-down menu in the WhatsApp template.

Avvertimento

Often when changing the model or Applies to field, the Phone Field may produce an error The Phone Field should always be set to the `Phone` or `Mobile` model.

To search available fields, type in the front-end name in the search box. This finds a result from all of the available fields for the model (Applies to) that the template is created for.

Nota

In order to find specific fields, multiple levels may need to be navigated in the search results box. Use the > (right chevron) and ⬅️ (left arrow) icons to navigate between the menu levels.

Change the Category to fit either a Marketing, Utility, or Authentication category. In most instances the first two options are used, unless the user would like to send a password reset or something security related. Set to Marketing should there be anything promotional being sent and set to Utility should there be general transactional messages being sent (i.e., sales order, event ticket, etc).

Importante

Specifying an incorrect category can cause a flag/rejected status from Meta during the approval process.

Add any Users that are allowed to use this template. In the right-side column, a Header type can be configured along with a Header message, as well.

The available Header types are as follows:

  * Testo

  * Immagine

  * Video

  * Documento

  * Location (variables need to be set)




Navigate to the Body tab to configure the main message of the template.

When all the necessary changes are made to the template, click on the Submit for approval button in the upper-left corner. This will cause the status of the template to change to Pending.

The status will remain in Pending until a decision has been made by Meta, whereby a confirmation email will then be sent indicating that the template has been approved (or rejected). The templates will then need to be synced from the Odoo database.

See this section for more information on syncing templates.

Suggerimento

Consider the preconfigured demo data templates available in Odoo to use or modify. These templates can be used as-is or modified to suit a specific business need.

To use these templates, navigate to WhatsApp app ‣ Templates and select a preconfigured template. Click Submit for Approval to start the approval process. An email gets sent to the administrator of the Meta account when the template has been approved.

#### Pulsanti¶

Buttons can be added into the message from the Buttons tab. Enter the Type (either Visit Website, Call Number, or Quick Reply), and then specify the Button Text, Call Number or Website URL (including Url Type), depending on the Type of button.

Nota

Buttons can also be added on the Meta business console. See Meta’s WhatsApp template dashboard by navigating to <https://business.facebook.com/wa/manage/home>. Then go to Account tools ‣ Message templates.

#### Using placeholders and variables¶

Dynamic variables reference certain fields within the Odoo database to produce unique data in the WhatsApp message when using a template. Dynamic variables are encoded to display fields from within the database, referencing fields from within a model.

Example

Many companies like to customize their WhatsApp messages with a personalized piece of customer information to grab attention. This can be accomplished in Odoo by referencing a field within a model by setting a dynamic variable. For example, a customer’s name can be referenced in the email from the Customer field on the Sales Order model.

Dynamic variables can be added in to the Body by adding placeholders in the _text_. To add a placeholder in the _message body_ enter the following text `{{1}}`. For the second placeholder enter `{{2}}` and increase incrementally as more placeholders are added to the text.

Example

 _The following is the text from payment receipt template body:_

Dear {{1}},

Here is your invoice _{{2}}_ from _{{3}}_ for a total of _{{4}}{{5}}_.

To review your invoice or pay online: {{6}}

Thank you

Vedi anche

WhatsApp templates.

These placeholders must be configured on the Variables tab of the template before submitting for approval from Meta. To edit the dynamic variables on a template, first change the Type to Field of Model. This allows Odoo to reference a field within a model to produce unique data in the message being sent.

Next, edit the Field of the dynamic variables. The Applies to field in the template should be edited prior to ensure the correct model and field are referenced.

To search the available fields, type in the front-end name of the field in the search box. This will find a result from all of the available fields for the model (Applies to) that the template is created for. There may be multiple levels that need to be configured.

Example

The following is an example of the variables set for the above placeholders in the payment receipt noted above:

Nome | Valore | Tipo | Campo  
---|---|---|---  
body - {{1}} | Azure Interior | Campo modello | `Partner`  
body - {{2}} | INV/2022/00001 | Campo modello | `Number`  
body - {{3}} | La mia azienda | Campo modello | `Company`  
body - {{4}} | $ | Campo modello | `Currency > Symbol`  
body - {{5}} | 4000 | Campo modello | `Amount`  
body - {{6}} | https://.. | Portal link |   
  
Example

For example, in the Body tab, if the following is typed, «Hello {{1}},», then `{{1}}` must be set in the Variables tab. For this specific case, the message should greet the customer by name, so the `{{1}}` should be configured to populate the `{{1}}` Field with the Customer name.

Avvertimento

Customizing WhatsApp templates is out of the scope of Odoo Support.

#### Meta template approval¶

After updating the dynamic variables on the template, the template needs to be submitted to Meta for approval again. Click Submit for Approval to start the approval process. An email will be sent to the administrator of the Meta account when the template has been approved.

Following the approval from Meta, sync the templates again in the Odoo database. See this documentation: Syncing templates.

Suggerimento

To see the status to Meta’s WhatsApp template dashboard by navigating to <https://business.facebook.com/wa/manage/home>. Then go to Account tools ‣ Message templates.

#### Syncing templates¶

Templates must be synced on the Odoo database once they are approved by the Meta team. To do so, begin by navigating to WhatsApp app ‣ Configuration ‣ WhatsApp Business Accounts and select the configuration that should be synced. Under the section marked Sending messages, towards the bottom, click on Sync Templates. Meta will update the templates that are approved so that they can be utilized with various apps in the database.

A successful message in green appears in the upper-right corner with the number of templates updated.

Suggerimento

Templates can also be synced individually from the template itself. Navigate to the WhatsApp app ‣ Templates dashboard and select the template to sync. Then, click on the Sync Template button located in the top menu of the template’s form.

### Creating templates in Meta¶

First, navigate to [Meta’s WhatsApp template dashboard](https://business.facebook.com/wa/manage/home), and then go to Account tools ‣ Message templates.

To create a WhatsApp template, click on the blue Create template button, and then select the Category. The options listed include: Marketing, Utility, and Authentication. In most instances the first two options are used, unless the user would like to send a password reset or something security related.

Enter the Name of the template and then select the Language for the template.

Nota

Multiple languages can be selected by typing the language names and selecting the other languages as needed.

After making the appropriate selections, click on Continue in the upper-right corner. The page redirects to the Edit template page. Here the Header, Body, Footer and Buttons are configured. To the right of the template is a preview of what the template will look like in production.

When all the necessary changes are made to the template, click on the Submit button in the upper-right corner. A confirmation window appears to confirm the language— click Confirm to approve and then another window appears stating that the template gets submitted to Meta for review and approval.

The Status of the template will remain in In review until a decision has been made by Meta. Once an email confirmation is received approving the template, the templates will need to be synced from within the Odoo database.

Vedi anche

For more information on configuring templates on the Meta developer console visit [Meta’s WhatsApp template documentation](https://developers.facebook.com/docs/whatsapp/business-management-api/message-templates/).

## Notifiche¶

Notifications in WhatsApp are handled similar to a message conversation in Odoo. A pop-up window appears with the received conversation from the customer. By default, notifications are set in the WhatsApp business account configuration in Odoo.

Notification settings can be adjusted by navigating to WhatsApp app ‣ Configuration ‣ WhatsApp Business Accounts. From there, select the account and scroll down to the Control section where notifications are handled. Under the Notify users heading, type in the field which users should be notified for this particular WhatsApp channel.

Nota

Once a conversation is initiated between a user and a customer, notifications to all the users specified in the WhatsApp business account configuration will not occur. Only notifications to the users in the conversation will occur. Should the user not respond within 15 days, the customer’s reply after the 15 days will populate once again to all the users specified in the WhatsApp configuration.

## Adding users to chat¶

Users can be added to a WhatsApp chat by expanding the WhatsApp pop-up window. WhatsApp conversations are located in the _Discuss_ app. Click on the 👤+ (add user) icon next to it, and a window appears to invite users to the conversation.

## WhatsApp API FAQ¶

### Verification¶

As of February 1, 2023, if the Meta app requires advanced level access to permissions, a complete business verification may need to be completed. This includes submitting office business documents to Meta. [See this documentation](https://developers.facebook.com/docs/development/release/business-verification).

Vedi anche

[Meta’s WhatsApp access verification documentation](https://developers.facebook.com/docs/development/release/access-verification/).

### Template errors¶

Editing templates can cause tracebacks and errors unless the exact process is followed above, here: (WhatsApp templates).

#### Duplicate validation error¶

When syncing the templates there may be an instance when there are multiple templates with the same name on Meta’s business manager and in Odoo. This causes a duplicate validation error. To correct this issue, rename the duplicate template name on Odoo and sync the templates once again by following the steps here: Syncing templates.

### Token errors¶

#### User error¶

Should the temporary token not be replaced with a permanent token a user error will populate in Odoo when testing the connection after sending fails. To correct this issues see Permanent token.

#### System user error 100¶

Should the system user be an Employee when setting up the permanent token, a user error 100 will populate.

To correct this error, create an Admin system user, following the process outlined here: Permanent token.

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/applications/productivity/whatsapp.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](voip.html "VoIP \(Voice over Internet Protocol\)") |
  * [precedente](data_cleaning.html "Pulizia dati") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Documentazione utente](../../applications.html) »
  * [Produttività](../productivity.html) »
  * WhatsApp


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
  *[EDI]: Electronic Data Exchange
  *[SDD]: SEPA Direct Debit
  *[PLE]: Programa de Libros Electrónico
  *[BoM]: Bill of Materials
  *[MO]: Manufacturing Order
  *[MPS]: Master Production Schedule
  *[OEE]: overall equipment effectiveness
  *[RFQ]: request for quotation
  *[RfQ]: Request for Quotation
  *[RfQs]: Requests for Quotation
  *[IU]: Interfaccia Utente
  *[UoM]: Unit of Measure
  *[PoS]: Point of Sale
  *[FBM]: Fulfilled by Merchant
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
  *[SVLs]: stock move layers
  *[SP]: Scrap Order
  *[DO]: Delivery Order
  *[RFQs]: requests for quotation
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
  *[CSV]: Valori separati da virgola
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
  *[CIS]: Construction Industry Scheme
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
  *[GSTIN]: Goods and Services Tax Identification Number
  *[TDS]: tax deducted at source
  *[TCS]: tax collected at source
  *[HMRC]: HM Revenue and Customs
  *[SVL]: stock move layer
  *[JIT]: just-in-time
  *[FAQs]: Frequently Asked Questions