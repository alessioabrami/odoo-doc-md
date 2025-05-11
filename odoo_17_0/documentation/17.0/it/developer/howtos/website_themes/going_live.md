# Going live — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../web_services.html "Web Services") |
  * [precedente](translations.html "Translations") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [How-to guides](../../howtos.html) »
  * [Website themes](../website_themes.html) »
  * Going live



# Going live¶

Once all the web design and development work finished, it’s time to deploy it on a development or production database.

## Module import¶

### Odoo SaaS¶

Follow these steps the first time you import a module:

  1. Create a ZIP file of your module.

  2. Connect to the project database.

  3. Enable the [developer mode](../../../applications/general/developer_mode.html#developer-mode).

  4. Go to Apps, search for `base_import_module`, and install it if necessary.

  5. Click on Import Module in the menu.

  6. Upload your ZIP file, tick Force init, and click the Import App button.




If you need to re-import a module after making some changes, follow the same steps, but before importing the module, open the developer menu and select Become Superuser. To leave the Superuser mode, log out and log back in.

Importante

  * Don’t forget to untick Force init if you import a module for the second time. Otherwise, existing data might be lost. ([Related to noupdate=1](pages.html#website-themes-pages-theme-pages-noupdate)).

  * The ZIP file size must be less than 50 MB.




Vedi anche

  * [Odoo eLearning: Register a Free Domain Name](https://www.odoo.com/slides/slide/register-a-free-domain-name-1663)




### Odoo.sh¶

Go to Apps and click on Update Apps List in the menu. Search for your module in the list and install it.

Vedi anche

[Introduction to Odoo.sh](../../../administration/odoo_sh/overview/introduction.html)

## What’s next?¶

After importing and installing the module and before going live, make sure to check the SEO and redirects as well as your domain name.

Vedi anche

**SEO & Redirects**

  * [Search Engine Optimization (SEO)](../../../applications/websites/website/pages/seo.html)

  * [URL redirect mapping](../../../applications/websites/website/pages.html#website-url-redirection)




**Domain name**

  * [Configurare un nome di dominio esistente](../../../applications/websites/website/configuration/domain_names.html#domain-name-existing)




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/developer/howtos/website_themes/going_live.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../web_services.html "Web Services") |
  * [precedente](translations.html "Translations") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [How-to guides](../../howtos.html) »
  * [Website themes](../website_themes.html) »
  * Going live


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration