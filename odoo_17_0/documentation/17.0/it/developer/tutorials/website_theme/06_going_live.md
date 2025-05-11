# Chapter 6 - Going live — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../howtos.html "How-to guides") |
  * [precedente](05_dynamic_templates.html "Chapter 5 - Dynamic templates") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [Tutorials](../../tutorials.html) »
  * [Build a website theme](../website_theme.html) »
  * Chapter 6 - Going live



# Chapter 6 - Going live¶

## Translations¶

Congratulations! Your client has a beautifully designed homepage and contact page, and the eCommerce is fully adapted to the Airproof design. Amazing!

Now, the client wants the website translated into French. To do so:

  1. Add French to the website in the settings and enable the language switcher in the header via presets.

  2. Then for the translation itself, you have two options. We shall therefore test both:

     * Translate the content of the homepage carousel through the backend.

     * But for the menu, make the translations through the frontend.

  3. Export the French `.po` file for your Airproof module and place it in the `/i18n` translations folder.

  4. If you would like, you can add more translations directly by editing the `.po` file. (Using Poedit software, your code editor, or another translation tool.)




Vedi anche

See reference documentation on [Backend](../../howtos/website_themes/translations.html#website-themes-translations-backend) and [Frontend](../../howtos/website_themes/translations.html#website-themes-translations-frontend) translations, and how to [Export](../../howtos/website_themes/translations.html#website-themes-translations-export) them.

Nota

  * Be careful when using Poedit, as it doesn’t handle tags with styles well and generates an `.mo` file.

  * To see the changes made directly via the `.po` file, you will need to manually import the file.




Solutions

Take a look at what the file [i18n/fr_BE.po](https://github.com/odoo/tutorials/blob/17.0/website_airproof/i18n/fr_BE.po) of our Airproof example looks like.

## Module import¶

Great job! The website is now completely finished and your module is ready for installation in the client’s SaaS database.

Just before that, test the import process on a new database.

Vedi anche

See reference documentation on how to [deploy a module](../../howtos/website_themes/going_live.html) on an Odoo SaaS database.

Suggerimento

  * Ensure the `base_import_module` is installed on the database before the module installation.

  * Verify all required applications are installed.

  * Skip the theme installation steps and start from scratch.

  * Manually import translations after module installation, as they won’t apply automatically.




## Conclusion¶

Congratulations on completing the **Build a module for a website theme** tutorial! You’ve successfully navigated through every stage, from setting up your development environment to launching a fully customized Odoo website theme.

Throughout this journey, you’ve mastered:

✅ **Theme module creation** \- setting up the structure, declaring Odoo and Bootstrap variables.

✅ **Website building** \- creating pages, adding media, and constructing dynamic building blocks.

✅ **Advanced customization** \- implementing custom SCSS, JavaScript, headers, footers, and unique design elements.

✅ **Visual enhancements** \- designing background shapes, gradients, and animations for an engaging user experience.

✅ **eCommerce optimization** \- adapting shop and product templates for a seamless shopping experience.

✅ **Final preparations** \- managing translations and ensuring a smooth module import.

With these skills, you’re now ready to design and develop professional, fully customized website themes. Well done!

We can’t wait to see the amazing themes you’ll create in the future.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/developer/tutorials/website_theme/06_going_live.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../howtos.html "How-to guides") |
  * [precedente](05_dynamic_templates.html "Chapter 5 - Dynamic templates") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [Tutorials](../../tutorials.html) »
  * [Build a website theme](../website_theme.html) »
  * Chapter 6 - Going live


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration