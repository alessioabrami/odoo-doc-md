# RST guidelines and cheat sheet — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [precedente](content_guidelines.html "Content guidelines") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Contributing](../../contributing.html) »
  * [Documentation](../documentation.html) »
  * RST guidelines and cheat sheet



# RST guidelines and cheat sheet¶

Importante

We strongly recommend reading the [Content guidelines](content_guidelines.html) and main [Documentation](../documentation.html) pages before contributing.

Follow the RST guidelines below when contributing to the documentation to help maintain consistency with the rest of the documentation and facilitate the review process for the team:

  * Use formatting.

  * Be consistent with indentation.

  * Start a new line before the 100th character.




For hyperlinks:

  * Use relative links for internal URLs.

  * Do not break hyperlink targets when refactoring.

  * Do not use non-descriptive hyperlink labels.




## Formatting¶

Use specific formatting to improve clarity and readability. For example, apply Menu selection for menu paths, GUI element for other user interface elements, such as fields, buttons, and options, Note for notes, Example for examples, etc.

Nota

Add a blank line between different block elements, such as paragraphs, lists, and directives to ensure proper rendering and formatting.

## Hyperlinks¶

### Internal URLs: relative links¶

If you need to reference an internal documentation page or a file that is not located in the same directory as the current page, always use _relative file paths_ instead of _absolute file paths_. This ensures that links remain valid even with version updates, folder name changes, and directory structure reorganizations.

An absolute file path indicates the target’s location from the root directory. A relative file path uses smart notations (such as `../` that redirects to the parent folder) to indicate the target’s location _relative_ to that of the source document.

Example

Nota

The purpose of the following example is to illustrate the difference between absolute and relative links. Always use Documentation page hyperlinks when referencing documentation pages.

Given the following source file tree:
    
    
    documentation
    ├── content
    │   └── applications
    │   │   └── sales
    │   │   │   └── sales
    │   │   │   │   └── products_prices
    │   │   │   │   │   └── products
    │   │   │   │   │   │   └── import.rst
    │   │   │   │   │   │   └── variants.rst
    │   │   │   │   │   └── prices.rst
    

A reference to `prices.rst` and `variants.rst` could be made from `import.rst` as follows:

  1. Absolute:

>      * `documentation/content/applications/sales/sales/products_prices/prices.rst`
> 
>      * `documentation/content/applications/sales/sales/products_prices/products/variants.rst`

  2. Relative:

>      * `../prices.rst`
> 
>      * `variants.rst`




### Refactoring: hyperlink targets¶

When refactoring (improving without adding new content) section headings or hyperlink targets, take care not to break any hyperlink reference to these targets or update them accordingly.

### Hyperlink labels¶

Do not use non-descriptive labels for hyperlinks.

Example

**Good example (descriptive label):**

Please refer to the [Accounting documentation](../../applications/finance/accounting.html).

**Bad example (non-descriptive label):**

Please refer to [this page](../../applications/finance/accounting.html).

## Indentation¶

Use only spaces (never tabs).

Use as many spaces at the beginning of an indented line as needed to align it with the first character of the markup in the line above. This usually implies three spaces, but you only need two for bulleted lists, for example.

Example

The first `:` is below the `i` (three spaces):
    
    
    .. image:: media/example.png
       :alt: example
    

The `:titlesonly:` and page references start below the `t` (three spaces):
    
    
    .. toctree::
       :titlesonly:
    
       payables/supplier_bills
       payables/pay
    

Continuation lines resume below the `I`’s of «Invoice» (two spaces):
    
    
    - Invoice on ordered quantity: invoice the full order as soon as the sales order is confirmed.
    - Invoice on delivered quantity: invoice on what was delivered even if it is a partial
      delivery.
    

## 100th-character limit¶

In RST, it is possible to break a line without forcing a line break on the rendered HTML. Make use of this feature to write **lines of maximum 100 characters**. It is not necessary to leave a trailing whitespace at the end of a line to separate words.

Suggerimento

  * You can safely break a line on any space, even inside markups such as `menuselection` and `doc`.

  * Some external hyperlinks may exceed 100 characters, but leaving them on a single line is acceptable.




Example
    
    
    To register your seller account in Odoo, go to :menuselection:`Sales --> Configuration -->
    Settings --> Amazon Connector --> Amazon Accounts` and click :guilabel:`Create`. You can find
    the **Seller ID** under the link :guilabel:`Your Merchant Token`.
    

## Headings¶

For each formatting line (e.g., `===`), write as many symbols (`=`) as there are characters in the header.

The symbols used for the formatting are, in fact, not important. Only the order in which they are written matters, as it determines the size of the decorated heading. This means that you may encounter different heading formatting and in a different order, in which case you should follow the formatting in place in the document. In any other case, use the formatting shown below.

Heading size | Formatting  
---|---  
H1 | 
    
    
    =======
    Heading
    =======
      
  
H2 | 
    
    
    Heading
    =======
      
  
H3 | 
    
    
    Heading
    -------
      
  
H4 | 
    
    
    Heading
    ~~~~~~~
      
  
H5 | 
    
    
    Heading
    *******
      
  
H6 | 
    
    
    Heading
    ^^^^^^^
      
  
Importante

Each document must have **exactly one H1 heading**.

## Markups¶

### Emphasis (italic)¶

To emphasize a part of the text. The text is rendered in italic.

Fill out the information _before_ saving the form.  
---  
      
    
    Fill out the information *before* saving the form.
      
  
### Strong emphasis (bold)¶

To emphasize a part of the text. The text is rendered in bold.

A **subdomain** is a domain that is a part of another domain.  
---  
      
    
    A **subdomain** is a domain that is a part of another domain.
      
  
### Technical term (literal)¶

To write a technical term or a specific value to insert. The text is rendered in literal.

Insert the IP address of your printer, for example, `192.168.1.25`.  
---  
      
    
    Insert the IP address of your printer, for example, `192.168.1.25`.
      
  
### Definitions¶

Use the `dfn` markup to define a term.

The documentation is written in RST and needs to be built (converted to HTML) to display nicely.  
---  
      
    
    The documentation is written in RST and needs to be built (:dfn:`converted to HTML`) to
    display nicely.
      
  
### Abbreviations¶

Use the `abbr` markup to write a self-defining abbreviation that is displayed as a tooltip.

Odoo uses OCR and artificial intelligence technologies to recognize the content of the documents.  
---  
      
    
    Odoo uses :abbr:`OCR (optical character recognition)` and artificial intelligence
    technologies to recognize the content of the documents.
      
  
### GUI element¶

Use the `guilabel` markup to identify any text of the interactive user interface (e.g., labels).

Update your credentials, then click on Save.  
---  
      
    
    Update your credentials, then click on :guilabel:`Save`.
      
  
Nota

Avoid using the `guilabel` markup when referring to a concept or general term.

Example

  * **Good example:**

To create a credit note, go to Accounting ‣ Customers ‣ Invoices, open the invoice, and click Credit Note.

  * **Bad example:**

To create a Credit Note, go to Accounting ‣ Customers ‣ Invoices, open the Invoice, and click Credit Note.




### Menu selection¶

Use the `menuselection` markup to guide users through a sequence of menus, starting with the app’s name.

To review sales performance, go to Sales ‣ Reporting ‣ Dashboard.  
---  
      
    
    To review sales performance, go to :menuselection:`Sales --> Reporting --> Dashboard`.
      
  
Nota

Only include actual menu items in the `menuselection` markup:

  * Use the GUI element markup for other user interface elements, such as buttons and section titles:
        
        To configure the bill control policy, navigate to :menuselection:`Purchase --> Configuration
        --> Settings`, and scroll down to the :guilabel:`Invoicing` section. Under :guilabel:`Bill
        Control`, select either :guilabel:`Ordered quantities` or :guilabel:`Received quantities`.
        

  * Do not include menu section names. For example, in the screenshot below, `Journals` should not be included in the menu path Accounting ‣ Accounting ‣ Journal Entries:




### File¶

Use the `file` markup to indicate a file path or name.

Create redirections using the `redirects.txt` file found at the root of the repository.  
---  
      
    
    Create redirections using the :file:`redirects.txt` file found at the root of the
    repository.
      
  
### Command¶

Use the `command` markup to highlight a command.

Run the command **make clean html** to delete existing built files and build the documentation to HTML.  
---  
      
    
    Run the command :command:`make clean html` to delete existing built files and build the
    documentation to HTML.
      
  
### Icons¶

Use the `icon` markup to add the class name of an icon. There are two icon sets used in Odoo: [FontAwesome4](https://fontawesome.com/v4/icons/) and [Odoo UI](../../developer/reference/user_interface/icons.html). Follow the icon with its name as a GUI element in brackets as a descriptor.

The graph view is represented by the __(area chart) icon. The pivot view is represented by the __icon.  
---  
      
    
    The graph view is represented by the :icon:`fa-area-chart` :guilabel:`(area chart)` icon.
    The pivot view is represented by the :icon:`oi-view-pivot` icon.
      
  
## Lists¶

### Bulleted list¶

  * This is a bulleted list.
  * It has two items, the second item uses two lines.

  
---  
      
    
    - This is a bulleted list.
    - It has two items, the second
      item uses two lines.
      
  
### Numbered list¶

  1. This is a numbered list.
  2. Numbering is automatic.

  
---  
      
    
    #. This is a numbered list.
    #. Numbering is automatic.
      
  
  6. Use this format to start the numbering with a number other than one.
  7. The numbering is automatic from there.

  
---  
      
    
    6. Use this format to start the numbering
       with a number other than one.
    #. The numbering is automatic from there.
      
  
Suggerimento

Prefer the use of autonumbered lists with `#.` instead of `1.`, `2.`, etc. for better code resilience.

### Nested lists¶

Suggerimento

  * Add a blank line before the nested elements in lists.

  * Indent nested lists properly, with sub-items aligned under their parent item.




  * This is the first item of a bulleted list.
    1. It has a nested numbered list
    2. with two items.

  
---  
      
    
    - This is the first item of a bulleted list.
    
      #. It has a nested numbered list
      #. with two items.
      
  
## Hyperlinks¶

### External hyperlinks¶

External hyperlinks are links to a URL with a custom label. They follow the syntax: ``label <URL>`_`.

Nota

  * Use documentation page hyperlinks when targeting another documentation page.

  * Do not use non-descriptive hyperlink labels.




For instance, [this is an external hyperlink to Odoo’s website](https://www.odoo.com/).  
---  
      
    
    For instance, `this is an external hyperlink to Odoo's website <https://www.odoo.com>`_.
      
  
### External hyperlink aliases¶

External hyperlink aliases allow creating shortcuts for external hyperlinks. The definition syntax is as follows: `.. _target: URL`. There are two ways to reference them, depending on the use case:

  1. `target_` creates a hyperlink with the target name as label and the URL as reference. Note that the `_` moved after the target.

  2. ``label <target_>`_` the label replaces the name of the target, and the target is replaced by the URL.


A [proof-of-concept](https://en.wikipedia.org/wiki/Proof_of_concept) is a simplified version, a prototype of what is expected to agree on the main lines of expected changes. [PoC](https://en.wikipedia.org/wiki/Proof_of_concept) is a common abbreviation.  
---  
      
    
    .. _proof-of-concept: https://en.wikipedia.org/wiki/Proof_of_concept
    
       A proof-of-concept_ is a simplified version, a prototype of what is expected to agree on
       the main lines of expected changes. `PoC <proof-of-concept_>`_ is a common abbreviation.
      
  
### Custom anchors¶

Custom anchors follow the same syntax as external hyperlink aliases but without any URL. They allow referencing a specific part of a RST file by using the target as an anchor. When users click the reference, they are taken to the part of the documentation page where the target is defined.

The definition syntax is: `.. _target:`. There are two ways to reference them, both using the `ref` markup:

  1. `:ref:`target`` creates a hyperlink to the anchor with the heading defined below as label.

  2. `:ref:`label <target>`` creates a hyperlink to the anchor with the given label.




Importante

As targets are visible from the entire documentation when referenced with the `ref` markup, prefix the target name with the **app/section name** and the **file name** , separated by slashes, e.g., `accounting/taxes/configuration`.

Nota

  * Add custom anchors for all headings so they can be referenced from any documentation file or within Odoo using documentation links.

  * Notice that there is no `_` at the end, contrary to what is done with external hyperlinks.




Please refer to the Hyperlinks section to learn more about relative links.  
---  
      
    
     .. _contributing/rst/hyperlinks-guidelines:
    
     Hyperlinks
     ==========
    
    .. _contributing/rst/relative-links:
    
    Use relative links for internal URLs
    ------------------------------------
    
    Please refer to the :ref:`contributing/rst/hyperlinks-guidelines` section to learn more
    about :ref:`relative links <contributing/rst/relative-links>`.
      
  
### Documentation page hyperlinks¶

The `doc` markup allows referencing a documentation page wherever it is in the file tree through a relative file path. There are two ways to use the markup, both using the `doc` markup:

  1. `:doc:`path_to_doc_page`` creates a hyperlink to the documentation page with the title of the page as label.

  2. `:doc:`label <path_to_doc_page>`` creates a hyperlink to the documentation page with the given label.


Please refer to the [Accounting documentation](../../applications/finance/accounting.html) to learn more about [Fatture cliente](../../applications/finance/accounting/customer_invoices.html).  
---  
      
    
    Please refer to the :doc:`Accounting documentation <../../../applications/finance/accounting>`
    to learn more about :doc:`../../../applications/finance/accounting/customer_invoices`.
      
  
Importante

Use relative links for documentation page hyperlinks.

### File download hyperlinks¶

The `download` markup allows referencing files (that are not necessarily RST documents) within the source tree to be downloaded.

Download this [`module structure template`](../../_downloads/0dcc8373b2643d41999de20092ea71af/my_module.zip) to start building your module.  
---  
      
    
    Download this :download:`module structure template <rst_guidelines/my_module.zip>` to start building your module.
      
  
Nota

Store the file alongside other [media files](content_guidelines.html#contributing-content-media-files) and reference it using a relative link.

## Images¶

The `image` markup allows inserting images in a document.  
  
---  
      
    
    .. image:: rst_guidelines/create-invoice.png
       :alt: Create an invoice.
      
  
Suggerimento

  * Images should generally be aligned to the left, which is the default behavior. Use the `align` parameter to change the alignment, e.g., `:align: center`.

  * Use the `alt` parameter to add [ALT tags](content_guidelines.html#contributing-content-alt-tags), e.g., `:alt: Activating the developer mode in the Settings app`.

  * Use the `scale` parameter to scale the image, e.g., `:scale: 75%`.




Vedi anche

[Content guidelines for images](content_guidelines.html#contributing-content-images)

## Alert blocks (admonitions)¶

### See also¶

Vedi anche

  * [Accounting documentation](../../applications/finance/accounting.html)
  * [Fatture proforma](../../applications/sales/sales/invoicing/proforma.html)
  * [Google documentation on setting up Analytics for a website](https://support.google.com/analytics/answer/1008015?hl=en/)

  
---  
      
    
    .. seealso::
    - :doc:`Accounting documentation <../../../applications/finance/accounting>`
    - :doc:`../../../applications/sales/sales/invoicing/proforma`
    - `Google documentation on setting up Analytics for a website <https://support.google.com/analytics/answer/1008015?hl=en/>`_
      
  
### Note¶

NotaUse this alert block to draw the reader’s attention and highlight important additional information.  
---  
      
    
    .. note::
       Use this alert block to draw the reader's attention and highlight important additional information.
      
  
### Tip¶

SuggerimentoUse this alert block to inform the reader about a useful trick that requires an action.  
---  
      
    
    .. tip::
       Use this alert block to inform the reader about a useful trick that requires an action.
      
  
### Example¶

ExampleUse this alert block to show an example.  
---  
      
    
    .. example::
       Use this alert block to show an example.
      
  
### Exercise¶

ExerciseUse this alert block to suggest an exercise to the reader.  
---  
      
    
    .. exercise::
       Use this alert block to suggest an exercise to the reader.
      
  
### Important¶

ImportanteUse this alert block to notify the reader about important information.  
---  
      
    
    .. important::
       Use this alert block to notify the reader about important information.
      
  
### Warning¶

AvvertimentoUse this alert block to require the reader to proceed with caution with what is described in the warning.  
---  
      
    
    .. warning::
       Use this alert block to require the reader to proceed with caution with what is described in the warning.
      
  
### Danger¶

PericoloUse this alert block to bring the reader’s attention to a serious threat.  
---  
      
    
    .. danger::
       Use this alert block to bring the reader's attention to a serious threat.
      
  
### Custom¶

TitleCustomize this alert block with a **Title** of your choice.  
---  
      
    
    .. admonition:: Title
    
       Customize this alert block with a **Title** of your choice.
      
  
## Tables¶

### List tables¶

List tables use two-level bulleted lists to convert data into a table. The first level represents the rows and the second level represents the columns.

| Name | Country | Favorite color  
---|---|---  
Raúl | Montenegro | Purple  
Mélanie | France | Red  
      
    
    .. list-table::
       :header-rows: 1
       :stub-columns: 1
    
       * - Name
         - Country
         - Favorite colour
       * - Raúl
         - Montenegro
         - Purple
       * - Mélanie
         - France
         - Turquoise
      
  
### Grid tables¶

Grid tables represent the rendered table and are more visual to work with.

|  | Shirts | T-shirts  
---|---|---  
**Available colours** | Purple | Green  
Turquoise | Orange  
**Sleeves length** | Long sleeves | Short sleeves  
      
    
    +-----------------------+--------------+---------------+
    |                       | Shirts       | T-shirts      |
    +=======================+==============+===============+
    | **Available colours** | Purple       | Green         |
    |                       +--------------+---------------+
    |                       | Turquoise    | Orange        |
    +-----------------------+--------------+---------------+
    | **Sleeves length**    | Long sleeves | Short sleeves |
    +-----------------------+--------------+---------------+
      
  
Suggerimento

  * Use `=` instead of `-` to define header rows.

  * Remove `-` and `|` separators to merge cells.

  * Make use of [this convenient table generator](https://www.tablesgenerator.com/text_tables) to build tables. Then, copy-paste the generated formatting into your document.




## Code blocks¶

Use the `code-block` directive to show example code. Specify the language (e.g., python, xml, etc.) to format the code according to the language’s syntax rules.
    
    
    def main():
        print("Hello world!")
      
  
---  
      
    
    .. code-block:: python
    
       def main():
           print("Hello world!")
      
  
## Spoilers¶

Answer to the Ultimate Question of Life, the Universe, and Everything**42**  
---  
      
    
    .. spoiler:: Answer to the Ultimate Question of Life, the Universe, and Everything
    
       **42**
      
  
## Content tabs¶

Avvertimento

The `tabs` markup may not work well in some situations. In particular:

  * The tabs” headers cannot be translated.

  * A tab cannot contain headings.

  * An alert block cannot contain tabs.

  * A tab cannot contain custom anchors.




### Basic tabs¶

Basic tabs are useful to split the content into multiple options. The `tabs` markup is used to define sequence of tabs. Each tab is then defined with the `tab` markup followed by a label.

Odoo OnlineOdoo.shOn-premiseContent dedicated to Odoo Online users. Alternative for Odoo.sh users. Third version for On-premise users.  
---  
      
    
    .. tabs::
    
       .. tab:: Odoo Online
    
          Content dedicated to Odoo Online users.
    
       .. tab:: Odoo.sh
    
          Alternative for Odoo.sh users.
    
       .. tab:: On-premise
    
          Third version for On-premise users.
      
  
### Nested tabs¶

Tabs can be nested inside one another.

StarsMoons The SunProxima CentauriPolarisThe closest star to us. The second closest star to us. The North Star. The MoonTitanOrbits the Earth. Orbits Jupiter.  
---  
      
    
    .. tabs::
    
       .. tab:: Stars
    
          .. tabs::
    
             .. tab:: The Sun
    
                The closest star to us.
    
             .. tab:: Proxima Centauri
    
                The second closest star to us.
    
             .. tab:: Polaris
    
                The North Star.
    
       .. tab:: Moons
    
          .. tabs::
    
             .. tab:: The Moon
    
                Orbits the Earth.
    
             .. tab:: Titan
    
                Orbits Jupiter.
      
  
### Group tabs¶

Group tabs are special tabs that synchronize based on a group label. The last selected group is remembered and automatically selected when the user returns to the page or visits another page with the tabs group. The `group-tab` markup is used to define group tabs.

C++PythonJavaC++ Python Java C++PythonJava
    
    
    int main(const int argc, const char **argv) {
        return 0;
    }
    
    
    
    def main():
        return
    
    
    
    class Main {
        public static void main(String[] args) {}
    }
      
  
---  
      
    
    .. tabs::
    
       .. group-tab:: C++
    
          C++
    
       .. group-tab:: Python
    
          Python
    
       .. group-tab:: Java
    
          Java
    
    .. tabs::
    
       .. group-tab:: C++
    
          .. code-block:: c++
    
             int main(const int argc, const char **argv) {
                 return 0;
             }
    
       .. group-tab:: Python
    
          .. code-block:: python
    
             def main():
                 return
    
       .. group-tab:: Java
    
          .. code-block:: java
    
             class Main {
                 public static void main(String[] args) {}
             }
      
  
### Code tabs¶

Use the `code-tab` markup to create code tabs, which are essentially group tabs that treat the tabs” content as a code block. Specify the language to format the code according to the language’s syntax rules. If a label is set, it is used for grouping tabs instead of the language name.

Hello C++Hello PythonHello JavaScript
    
    
    #include <iostream>
    
    int main() {
        std::cout << "Hello World";
        return 0;
    }
    
    
    
    print("Hello World")
    
    
    
    console.log("Hello World");
      
  
---  
      
    
    .. tabs::
    
       .. code-tab:: c++ Hello C++
    
          #include <iostream>
    
          int main() {
              std::cout << "Hello World";
              return 0;
          }
    
       .. code-tab:: python Hello Python
    
          print("Hello World")
    
       .. code-tab:: javascript Hello JavaScript
    
          console.log("Hello World");
      
  
## Cards¶

#### [DocumentationUse this guide to acquire the tools and knowledge you need to write documentation. Step-by-step guide](../documentation.html)#### [Content guidelinesList of guidelines, tips, and tricks to help you create clear and effective content. ](content_guidelines.html)#### [RST guidelinesList of technical guidelines to observe when writing with reStructuredText. ](rst_guidelines.html)  
---  
      
    
    .. cards::
    
       .. card:: Documentation
          :target: ../documentation
          :tag: Step-by-step guide
          :large:
    
          Use this guide to acquire the tools and knowledge you need to write documentation.
    
       .. card:: Content guidelines
          :target: content_guidelines
    
          List of guidelines, tips, and tricks to help you create clear and effective content.
    
       .. card:: RST guidelines
          :target: rst_guidelines
    
          List of technical guidelines to observe when writing with reStructuredText.
      
  
## Document metadata¶

[Sphinx](https://en.wikipedia.org/wiki/Sphinx_\(documentation_generator\)) supports document-wide metadata markups that specify a behavior for the entire page. They must be placed between colons (`:`) at the top of the source file.

**Metadata** | **Purpose**  
---|---  
`show-content` | Make a toctree page accessible from the navigation menu.  
`show-toc` | Show the table of content on a page that has the `show-content` metadata markup.  
`hide-page-toc` | Hide the «On this page» sidebar and use full page width for the content.  
`nosearch` | Exclude the document from search results.  
`orphan` | Suppress the need to include the document in a toctree.  
`code-column` |  Show a dynamic side column that can be used to display interactive tutorials or code excerpts. For example, see [Promemoria contabile](../../applications/finance/accounting/get_started/cheat_sheet.html).  
`custom-css` | Link CSS files (comma-separated) to the file.  
`custom-js` | Link JS files (comma-separated) to the document.  
`classes` | Assign the specified classes to the `<main/>` element of the file.  
  
## Formatting tips¶

### Break the line but not the paragraph¶

A first long line that you break in two -> here <\- is rendered as a single line. A second line that follows a line break.  
---  
      
    
    | A first long line that you break in two
      -> here <- is rendered as a single line.
    | A second line that follows a line break.
      
  
### Escape markup symbols¶

Markup symbols escaped with backslashes (`\`) are rendered normally. For instance, `this \*\*line of text\*\* with \*markup\* symbols` is rendered as “this **line of text** with *markup* symbols”.

When it comes to backticks (```), which are used in many cases such as external hyperlinks, using backslashes for escaping is no longer an option because the outer backticks interpret enclosed backslashes and thus prevent them from escaping inner backticks. For instance, ``\`this formatting\``` produces an `[UNKNOWN NODE title_reference]` error. Instead, ````this formatting```` should be used to produce the following result: ``this formatting``.

Vedi anche

[Docutils documentation on reStructuredText directives and roles](https://docutils.sourceforge.io/docs/ref/rst/directives.html)

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/18.0/content/contributing/documentation/rst_guidelines.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [precedente](content_guidelines.html "Content guidelines") |
  * [Odoo 18.0 documentazione](../../index-2.html) »
  * [Contributing](../../contributing.html) »
  * [Documentation](../documentation.html) »
  * RST guidelines and cheat sheet


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
  *[MPS]: Master Production Schedule
  *[OEE]: overall equipment effectiveness
  *[RFQ]: request for quotation
  *[RfQ]: Request for Quotation
  *[RfQs]: Requests for Quotation
  *[IU]: Interfaccia Utente
  *[UoM]: Unit of Measure
  *[PoS]: Point of Sale
  *[FBM]: Fulfilled By Merchant
  *[FBA]: Fulfilled by Amazon
  *[API]: Application Programming Interface
  *[IVA]: imposta sul valore aggiunto
  *[MRR]: monthly recurring revenue
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
  *[RUT]: Registro único tributario
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