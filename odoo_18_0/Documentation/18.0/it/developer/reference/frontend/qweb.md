# QWeb Templates — Odoo 18.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](odoo_editor.html "Odoo Editor") |
  * [precedente](mobile.html "Mobile JavaScript") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [Reference](../../reference.html) »
  * [Web framework](../frontend.html) »
  * QWeb Templates



# QWeb Templates¶

QWeb is the primary [templating](https://en.wikipedia.org/wiki/Template_processor) engine used by Odoo2. It is an XML templating engine1 and used mostly to generate [HTML](https://en.wikipedia.org/wiki/HTML) fragments and pages.

Template directives are specified as XML attributes prefixed with `t-`, for instance `t-if` for Conditionals, with elements and other attributes being rendered directly.

To avoid element rendering, a placeholder element `<t>` is also available, which executes its directive but doesn’t generate any output in and of itself:
    
    
    <t t-if="condition">
        <p>Test</p>
    </t>
    

will result in:
    
    
    <p>Test</p>
    

if `condition` is true, but:
    
    
    <div t-if="condition">
        <p>Test</p>
    </div>
    

will result in:
    
    
    <div>
        <p>Test</p>
    </div>
    

## Data output¶

QWeb’s output directive `out` will automatically HTML-escape its input, limiting [XSS](https://en.wikipedia.org/wiki/Cross-site_scripting) risks when displaying user-provided content.

`out` takes an expression, evaluates it and injects the result in the document:
    
    
    <p><t t-out="value"/></p>
    

rendered with the value `value` set to `42` yields:
    
    
    <p>42</p>
    

See Advanced Output for more advanced topics (e.g. injecting raw HTML, etc…).

## Conditionals¶

QWeb has a conditional directive `if`, which evaluates an expression given as attribute value:
    
    
    <div>
        <t t-if="condition">
            <p>ok</p>
        </t>
    </div>
    

The element is rendered if the condition is true:
    
    
    <div>
        <p>ok</p>
    </div>
    

but if the condition is false it is removed from the result:
    
    
    <div>
    </div>
    

The conditional rendering applies to the bearer of the directive, which does not have to be `<t>`:
    
    
    <div>
        <p t-if="condition">ok</p>
    </div>
    

will give the same results as the previous example.

Extra conditional branching directives `t-elif` and `t-else` are also available:
    
    
    <div>
        <p t-if="user.birthday == today()">Happy birthday!</p>
        <p t-elif="user.login == 'root'">Welcome master!</p>
        <p t-else="">Welcome!</p>
    </div>
    

## Loops¶

QWeb has an iteration directive `foreach` which take an expression returning the collection to iterate on, and a second parameter `t-as` providing the name to use for the «current item» of the iteration:
    
    
    <t t-foreach="[1, 2, 3]" t-as="i">
        <p><t t-out="i"/></p>
    </t>
    

will be rendered as:
    
    
    <p>1</p>
    <p>2</p>
    <p>3</p>
    

Like conditions, `foreach` applies to the element bearing the directive’s attribute, and
    
    
    <p t-foreach="[1, 2, 3]" t-as="i">
        <t t-out="i"/>
    </p>
    

is equivalent to the previous example.

`foreach` can iterate on an array (the current item will be the current value) or a mapping (the current item will be the current key). Iterating on an integer (equivalent to iterating on an array between 0 inclusive and the provided integer exclusive) is still supported but deprecated.

In addition to the name passed via `t-as`, `foreach` provides a few other variables for various data points:

Avvertimento

`$as` will be replaced by the name passed to `t-as`

`_$as_ _all` (deprecated)
    

the object being iterated over

Nota

This variable is only available on JavaScript QWeb, not Python.

`_$as_ _value`
    

the current iteration value, identical to `$as` for lists and integers, but for mappings it provides the value (where `$as` provides the key)

`_$as_ _index`
    

the current iteration index (the first item of the iteration has index 0)

`_$as_ _size`
    

the size of the collection if it is available

`_$as_ _first`
    

whether the current item is the first of the iteration (equivalent to `_$as_ _index == 0`)

`_$as_ _last`
    

whether the current item is the last of the iteration (equivalent to `_$as_ _index + 1 == _$as_ _size`), requires the iteratee’s size be available

`_$as_ _parity` (deprecated)
    

either `"even"` or `"odd"`, the parity of the current iteration round

`_$as_ _even` (deprecated)
    

a boolean flag indicating that the current iteration round is on an even index

`_$as_ _odd` (deprecated)
    

a boolean flag indicating that the current iteration round is on an odd index

These extra variables provided and all new variables created into the `foreach` are only available in the scope of the `foreach`. If the variable exists outside the context of the `foreach`, the value is copied at the end of the foreach into the global context.
    
    
    <t t-set="existing_variable" t-value="False"/>
    <!-- existing_variable now False -->
    
    <p t-foreach="[1, 2, 3]" t-as="i">
        <t t-set="existing_variable" t-value="True"/>
        <t t-set="new_variable" t-value="True"/>
        <!-- existing_variable and new_variable now True -->
    </p>
    
    <!-- existing_variable always True -->
    <!-- new_variable undefined -->
    

## attributes¶

QWeb can compute attributes on-the-fly and set the result of the computation on the output node. This is done via the `t-att` (attribute) directive which exists in 3 different forms:

`t-att-_$name_`
    

an attribute called `$name` is created, the attribute value is evaluated and the result is set as the attribute’s value:
    
    
    <div t-att-a="42"/>
    

will be rendered as:
    
    
    <div a="42"></div>
    

`t-attf-_$name_`
    

same as previous, but the parameter is a [format string](../../glossary.html#term-format-string) instead of just an expression, often useful to mix literal and non-literal string (e.g. classes):
    
    
    <t t-foreach="[1, 2, 3]" t-as="item">
        <li t-attf-class="row {{ (item_index % 2 === 0) ? 'even' : 'odd' }}">
            <t t-out="item"/>
        </li>
    </t>
    

will be rendered as:
    
    
    <li class="row even">1</li>
    <li class="row odd">2</li>
    <li class="row even">3</li>
    

Suggerimento

There are two equivalent syntaxes for format strings: `"plain_text {{code}}"` (aka jinja-style) and `"plain_text #{code}"` (aka ruby-style).

`t-att=mapping`
    

if the parameter is a mapping, each (key, value) pair generates a new attribute and its value:
    
    
    <div t-att="{'a': 1, 'b': 2}"/>
    

will be rendered as:
    
    
    <div a="1" b="2"></div>
    

`t-att=pair`
    

if the parameter is a pair (tuple or array of 2 element), the first item of the pair is the name of the attribute and the second item is the value:
    
    
    <div t-att="['a', 'b']"/>
    

will be rendered as:
    
    
    <div a="b"></div>
    

## setting variables¶

QWeb allows creating variables from within the template, to memoize a computation (to use it multiple times), give a piece of data a clearer name, …

This is done via the `set` directive, which takes the name of the variable to create. The value to set can be provided in two ways:

  * a `t-value` attribute containing an expression, and the result of its evaluation will be set:
        
        <t t-set="foo" t-value="2 + 1"/>
        <t t-out="foo"/>
        

will print `3`

  * if there is no `t-value` attribute, the node’s body is rendered and set as the variable’s value:
        
        <t t-set="foo">
            <li>ok</li>
        </t>
        <t t-out="foo"/>
        




## calling sub-templates¶

QWeb templates can be used for top-level rendering, but they can also be used from within another template (to avoid duplication or give names to parts of templates) using the `t-call` directive:
    
    
    <t t-call="other-template"/>
    

This calls the named template with the execution context of the parent, if `other_template` is defined as:
    
    
    <p><t t-value="var"/></p>
    

the call above will be rendered as `<p/>` (no content), but:
    
    
    <t t-set="var" t-value="1"/>
    <t t-call="other-template"/>
    

will be rendered as `<p>1</p>`.

However, this has the problem of being visible from outside the `t-call`. Alternatively, content set in the body of the `call` directive will be evaluated _before_ calling the sub-template, and can alter a local context:
    
    
    <t t-call="other-template">
        <t t-set="var" t-value="1"/>
    </t>
    <!-- "var" does not exist here -->
    

The body of the `call` directive can be arbitrarily complex (not just `set` directives), and its rendered form will be available within the called template as a magical `0` variable:
    
    
    <div>
        This template was called with content:
        <t t-out="0"/>
    </div>
    

being called thus:
    
    
    <t t-call="other-template">
        <em>content</em>
    </t>
    

will result in:
    
    
    <div>
        This template was called with content:
        <em>content</em>
    </div>
    

## Advanced Output¶

By default, `out` should HTML-escape content which needs to be escaped, protecting the system against [XSS](https://en.wikipedia.org/wiki/Cross-site_scripting)

Content which does _not_ need to be escaped will instead be injected as-is in the document, and may become part of the document’s actual markup.

The only cross-platform «safe» content is the output of t-call or a t-set used with a «body» (as opposed to `t-value` or `t-valuef`).

### Python¶

Usually you should not have to care too much: APIs for which it makes sense should generate «safe» content automatically, and things should work transparently.

For the cases where things need to be clearer though the following APIs output safe content which will by default not be (re-)escaped when injected into templates:

  * [`HTML fields`](../backend/orm.html#odoo.fields.Html "odoo.fields.Html").

  * `html_escape()` and `markupsafe.escape()` (they are aliases, and have no risk of double-escaping).

  * `html_sanitize()`.

  * `markupsafe.Markup`.

Avvertimento

`markupsafe.Markup` is an unsafe API, it’s an _assertion_ that you want the content to be markup-safe but necessarily can not check that, it should be used with care.

  * `to_text()` does not mark the content as safe, but will not strip that information from safe content.




### forcing double-escaping¶

If content is marked as safe but for some reason needs to be escaped anyway (e.g. printing the markup of an HTML fields), it can just be converted back to a normal string to «strip» the safety flag e.g. `str(content)` in Python and `String(content)` in Javascript.

Nota

Because `Markup` is a much richer type than `Markup()`, some operations will strip the safety information from a `Markup()` but not a `Markup` e.g. string concatenation (`'' + content`) in Python will result in a `Markup` with the other operand having been properly escaped, while in Javascript will yield a `String()` where the other operand was _not_ escaped before the concatenation.

### Deprecated output directives¶

`esc`
    

An alias for `out`, would originally HTML-escape its input. Not yet formally deprecated as the only difference between `out` and `esc` is that the latter is a bit unclear / incorrect.

`raw`
    

A version of `out` which _never_ escapes its content. Content is emitted as-is, whether it’s safe or not.

Deprecato dalla versione 15.0: Use `out` with a `markupsafe.Markup` value instead.

`t-raw` was deprecated because as the code _producting_ the content evolves it can be hard to track that it’s going to be used for markup, leading to more complicated reviews and more dangerous lapses.

## Python¶

### Exclusive directives¶

#### Asset bundles¶

#### «smart records» fields formatting¶

The `t-field` directive can only be used when performing field access (`a.b`) on a «smart» record (result of the `browse` method). It is able to automatically format based on field type, and is integrated in the website’s rich text editing.

`t-options` can be used to customize fields, the most common option is `widget`, other options are field- or widget-dependent.

### Debugging¶

`t-debug`
    

with an empty value, invokes the [`breakpoint()`](https://docs.python.org/3/library/functions.html#breakpoint "\(in Python v3.13\)") builtin function, which usually invokes a debugger ([`pdb`](https://docs.python.org/3/library/pdb.html#module-pdb "\(in Python v3.13\)") by default).

The behaviour can be configured via [`PYTHONBREAKPOINT`](https://docs.python.org/3/using/cmdline.html#envvar-PYTHONBREAKPOINT "\(in Python v3.13\)") or [`sys.breakpointhook()`](https://docs.python.org/3/library/sys.html#sys.breakpointhook "\(in Python v3.13\)").

### Rendering cache:¶

`t-cache="key_cache"` tags part of template to be cached at rendering time. Every sub-directives will be call only during the first rendering. It means that the sql queries excecuted during the rendering of those sub-directives are also done only once.

`t-nocache="documentation"` tags part of template to be render every time. The content can only use the root values.

#### Why and when to use `t-cache`?¶

This directive is used to speed up the rendering, by caching parts of the final document, which may save queries to the database. However, it should be used sparingly, as `t-cache` will inevitably complicate templates (and their understanding of `t-set` for example).

However, in order to actually save database queries, it might be necessary to render the template with values that are evaluated lazily. If those lazy values are used in a cached part, they will not be evaluated if the part is available in cache.

The `t-cache` directive is useful for template parts using values that depend on a limited amount of data. We recommend to analyze the rendering of the template with the profiler (by activating the «**Add qweb directive context** » option). Passing lazy values to the rendering in controllers allow you to display the directives using these values and triggering the queries.

A concern of using such a cache are making it available to different users (different users should render the cached parts the same way). Another potential issue is to invalidate its entries when necessary. For the latter, the **key expression** should be chosen wisely. Using the `write_date` of a recordset can make a cache key out-of-date without having to discard it explicitly from the cache, for instance.

One should also pay attention to the fact that the values in `t-cache` parts are scoped. This implies that if there are `t-set` directives in this part of the template, the rendering of what comes after it could be different than if there was no `t-cache` directive.

#### What if there is a `t-cache` inside a `t-cache`?¶

The parts are cached. Each containing only the string corresponding to its rendering. Thus, the `t-cache` inside will probably be read less often, its cache key will not necessarily be used. If this must be the case, then you may need to add a `t-nocache` (on the same node or a parent).

#### What is `t-nocache` used for?¶

If you want to cache part of a template with `t-cache` but a small piece must remain dynamic and be evaluated at cache times. However, the part in `t-nocache` will not have access to the `t-set` value of the template. Only the values ​​provided by the controller are accessible there. For example, the menu is cached because it’s the same all the time and takes time to render (using the performance devtools with the qweb context lets you investigate). However, in the menu, we want the ecommerce cart to be always up to date. So there is a `t-nocache` to keep this part dynamic.

#### The base of `t-cache`¶

The `t-cache` directive allows you to store the rendered result of a template. The **key expression** (eg 42: `t-cache="42"`) will be evaluated as a python expression. This will be used to generate the **cache key**. So there can be different **cache values** (cached render part) for the same template part. If the **key expression** is a tuple or a list, it will be searched when generating the **cache key**. If one or more recordsets are returned by the **key expression** , then the model, ids and their corresponding write_date will be used to generate the **cache key**. Special case: If the **key expression** returns a Falsy value, then the content will not be cached.

Example:
    
    
    <div t-cache="record,bool(condition)">
        <span t-if="condition" t-field="record.partner_id.name">
        <span t-else="" t-field="record.partner_id" t-options-widget="contact">
    </div>
    

In this case, there may be values ​​(string) in the cache corresponding to each record already returned with a true condition, as well as for the false condition. And if a module modifies the record, the write_date being modified, the cached value is discarded.

#### `t-cache` and scoped values (`t-set`, `t-foreach`…)¶

Values in `t-cache` are scoped, this involves a change in behavior between having or not having `t-cache` on one of the parent nodes. Don’t forget to take into account that Odoo uses a lot of templates, `t-call` and view inheritance. Adding a `t-cache` can therefore modify the rendering of a template that you do not see when editing. (`t-foreach` it’s like a `t-set` for each iteration)

Example:
    
    
    <div>
        <t t-set="a" t-value="1"/>
        <inside>
            <t t-set="a" t-value="2"/>
            <t t-out="a"/>
        </inside>
        <outside t-out="a"/>
    
        <t t-set="b" t-value="1"/>
        <inside t-cache="True">
            <t t-set="b" t-value="2"/>
            <t t-out="b"/>
        </inside>
        <outside t-out="b"/>
    </div>
    

Will render:
    
    
    <div>
        <inside>2</inside>
        <outside>2</inside>
    
        <inside>2</inside>
        <outside>1</inside>
    </div>
    

#### The base of `t-nocache`¶

The template part contained in a node with a `t-nocache` attribute is not cached. This content is therefore **dynamic** and is rendered systematically. However the available values are those provided by the controller (when calling the `_render` method).

Example:
    
    
    <section>
        <article t-cache="record">
            <title><t t-out="record.name"/> <i t-nocache="">(views: <t t-out="counter"/>)</i></titlle>
            <content t-out="record.description"/>
        </article>
    </section>
    

Will render (counter = 1):
    
    
    <section>
        <article>
            <title>The record name <i>(views: 1)</i></titlle>
            <content>Record description</content>
        </article>
    </section>
    

Here the `<i>` tag that contains the container will always be rendered. While the rest is as a single string in the cache.

#### `t-nocache` and scoped root values (`t-set`, `t-foreach`…)¶

The contents of the `t-nocache` tag can be used for documentation and to explain why the directive is added. The values are scoped into `t-nocache`, these values are root values only (values provided by the controller and/or when calling the `_render` method of `ir.qweb`). `t-set` can be done in the template part, but will not be available elsewhere.

Example:
    
    
    <section>
        <t t-set="counter" t-value="counter * 10"/>
        <header t-nocache="">
            <t t-set="counter" t-value="counter + 5"/>
            (views: <t t-out="counter"/>)
        </header>
        <article t-cache="record">
            <title><t t-out="record.name"/> <i t-nocache="">(views: <t t-out="counter"/>)</i></titlle>
            <content t-out="record.description"/>
        </article>
        <footer>(views: <t t-out="counter"/>)</footer>
    </section>
    

Will render (counter = 1):
    
    
    <section>
        <header>
            (views: 6)
        </header>
        <article>
            <title>The record name <i>(views: 1)</i></titlle>
            <content>Record description</content>
        </article>
        <footer>(views: 10)</footer>
    </section>
    

Here the `<i>` tag that contains the container will always be rendered. While the rest is as a single string in the cache. The counter is not updated by the `t-set` out of the `t-nocache`

#### `t-nocache-*` add some primitive values in the cache¶

In order to be able to use values generated in the template, it is possible to cache them. The directive is used as `t-nocache-*="expr"` where `*` is the name of the chosen value and `expr` the python expression so the result will be cached. The cached value must be primitive type.

Example:
    
    
    <section t-cache="records">
        <article t-foreach="records" t-as="record">
            <header>
                <title t-field="record.get_method_title()"/>
            </header>
            <footer t-nocache="This part has a dynamic counter and must be rendered all the time."
                    t-nocache-cached_value="record.get_base_counter()">
                <span t-out="counter + cached_value"/>
            </footer>
        </article>
    </section>
    

The value `cached_value` is cached with the cached template part of `t-cache="records"` and add to the scoped root values each time.

### Helpers¶

#### Request-based¶

Most Python-side uses of QWeb are in controllers (and during HTTP requests), in which case templates stored in the database (as [views](../user_interface/view_architectures.html#reference-view-architectures-qweb)) can be trivially rendered by calling `odoo.http.HttpRequest.render()`:
    
    
    response = http.request.render('my-template', {
        'context_value': 42
    })
    

This automatically creates a [`Response`](../backend/http.html#odoo.http.Response "odoo.http.Response") object which can be returned from the controller (or further customized to suit).

#### View-based¶

At a deeper level than the previous helper is the `_render` method on `ir.qweb` (use the datable) and the public module method `render` (don’t use the database):

_render(_id_[, _values_])¶
    

Renders a QWeb view/template by database id or [external id](../../glossary.html#term-external-id). Templates are automatically loaded from `ir.qweb` records.

`_prepare_environment` method sets up a number of default values in the rendering context. The `http_routing` and `website` addons, also default values they need. You can use `minimal_qcontext=False` option to avoid this default value like the public method `render`:

`request`
    

the current [`Request`](../backend/http.html#odoo.http.Request "odoo.http.Request") object, if any

`debug`
    

whether the current request (if any) is in `debug` mode

`quote_plus`
    

url-encoding utility function

[`json`](https://docs.python.org/3/library/json.html#module-json "\(in Python v3.13\)")
    

the corresponding standard library module

[`time`](https://docs.python.org/3/library/time.html#module-time "\(in Python v3.13\)")
    

the corresponding standard library module

[`datetime`](https://docs.python.org/3/library/datetime.html#module-datetime "\(in Python v3.13\)")
    

the corresponding standard library module

[relativedelta](https://labix.org/python-dateutil#head-ba5ffd4df8111d1b83fc194b97ebecf837add454)
    

see module

`keep_query`
    

the `keep_query` helper function

Parametri
    

  * **values** – context values to pass to QWeb for rendering

  * **engine** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – name of the Odoo model to use for rendering, can be used to expand or customize QWeb locally (by creating a «new» qweb based on `ir.qweb` with alterations)




render(_template_name_ , _values_ , _load_ , _** options_)¶
    

`load(ref)()`
    

returns etree object, ref

## Javascript¶

### Exclusive directives¶

#### Defining templates¶

The `t-name` directive can only be placed at the top-level of a template file (direct children to the document root):
    
    
    <templates>
        <t t-name="template-name">
            <!-- template code -->
        </t>
    </templates>
    

It takes no other parameter, but can be used with a `<t>` element or any other. With a `<t>` element, the `<t>` should have a single child.

The template name is an arbitrary string, although when multiple templates are related (e.g. called sub-templates) it is customary to use dot-separated names to indicate hierarchical relationships.

#### Template inheritance¶

Template inheritance is used to either:
    

  * Alter existing templates in-place, e.g. to add information to templates



created by other modules.
    

  * Create a new template from a given parent template



Template inheritance is performed via the use of two directives:
    

  * `t-inherit` which is the name of the template to inherit from,

  * `t-inherit-mode` which is the behaviour of the inheritance: it can either be set to `primary` to create a new child template from the parented one or to `extension` to alter the parent template in place.




An optional `t-name` directive can also be specified. It will be the name of the newly created template if used in primary mode, else it will be added as a comment on the transformed template to help retrace inheritances.

For the inheritance itself, the changes are done using xpaths directives. See the [XPATH](https://developer.mozilla.org/en-US/docs/Web/XPath) documentation for the complete set of available instructions.

Primary inheritance (child template):
    
    
    <t t-name="child.template" t-inherit="base.template" t-inherit-mode="primary">
        <xpath expr="//ul" position="inside">
            <li>new element</li>
        </xpath>
    </t>
    

Extension inheritance (in-place transformation):
    
    
    <t t-inherit="base.template" t-inherit-mode="extension">
        <xpath expr="//tr[1]" position="after">
            <tr><td>new cell</td></tr>
        </xpath>
    </t>
    

#### Old inheritance mechanism (deprecated)¶

Template inheritance is performed via the `t-extend` directive which takes the name of the template to alter as parameter.

The directive `t-extend` will act as a primary inheritance when combined with `t-name` and as an extension one when used alone.

In both cases the alteration is then performed with any number of `t-jquery` sub-directives:
    
    
    <t t-extend="base.template">
        <t t-jquery="ul" t-operation="append">
            <li>new element</li>
        </t>
    </t>
    

The `t-jquery` directives takes a [CSS selector](https://api.jquery.com/category/selectors/). This selector is used on the extended template to select _context nodes_ to which the specified `t-operation` is applied:

`append`
    

the node’s body is appended at the end of the context node (after the context node’s last child)

`prepend`
    

the node’s body is prepended to the context node (inserted before the context node’s first child)

`before`
    

the node’s body is inserted right before the context node

`after`
    

the node’s body is inserted right after the context node

`inner`
    

the node’s body replaces the context node’s children

`replace`
    

the node’s body is used to replace the context node itself

`attributes`
    

the nodes’s body should be any number of `attribute` elements, each with a `name` attribute and some textual content, the named attribute of the context node will be set to the specified value (either replaced if it already existed or added if not)

No operation
    

if no `t-operation` is specified, the template body is interpreted as javascript code and executed with the context node as `this`

Avvertimento

while much more powerful than other operations, this mode is also much harder to debug and maintain, it is recommended to avoid it

### debugging¶

The javascript QWeb implementation provides a few debugging hooks:

`t-log`
    

takes an expression parameter, evaluates the expression during rendering and logs its result with `console.log`:
    
    
    <t t-set="foo" t-value="42"/>
    <t t-log="foo"/>
    

will print `42` to the console

`t-debug`
    

triggers a debugger breakpoint during template rendering:
    
    
    <t t-if="a_test">
        <t t-debug=""/>
    </t>
    

will stop execution if debugging is active (exact condition depend on the browser and its development tools)

`t-js`
    

the node’s body is javascript code executed during template rendering. Takes a `context` parameter, which is the name under which the rendering context will be available in the `t-js`’s body:
    
    
    <t t-set="foo" t-value="42"/>
    <t t-js="ctx">
        console.log("Foo is", ctx.foo);
    </t>
    

### Helpers¶

core.qweb¶
    

(core is the `web.core` module) An instance of `QWeb2.Engine()` with all module-defined template files loaded, and references to standard helper objects `_` (underscore), `_t` (translation function) and [JSON](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON).

`core.qweb.render` can be used to easily render basic module templates

### API¶

_class _QWeb2.Engine()¶
    

The QWeb «renderer», handles most of QWeb’s logic (loading, parsing, compiling and rendering templates).

Odoo Web instantiates one for the user in the core module, and exports it to `core.qweb`. It also loads all the template files of the various modules into that QWeb instance.

A `QWeb2.Engine()` also serves as a «template namespace».

QWeb2.Engine.QWeb2.Engine.render(_template_[, _context_])¶
    

Renders a previously loaded template to a String, using `context` (if provided) to find the variables accessed during template rendering (e.g. strings to display).

Parametri
    

  * **template** (`String()`) – the name of the template to render

  * **context** (`Object()`) – the basic namespace to use for template rendering



Ritorna
    

String

The engine exposes an other method which may be useful in some cases (e.g. if you need a separate template namespace with, in Odoo Web, Kanban views get their own `QWeb2.Engine()` instance so their templates don’t collide with more general «module» templates):

QWeb2.Engine.QWeb2.Engine.add_template(_templates_)¶
    

Loads a template file (a collection of templates) in the QWeb instance. The templates can be specified as:

An XML string
    

QWeb will attempt to parse it to an XML document then load it.

A URL
    

QWeb will attempt to download the URL content, then load the resulting XML string.

A `Document` or `Node`
    

QWeb will traverse the first level of the document (the child nodes of the provided root) and load any named template or template override.

A `QWeb2.Engine()` also exposes various attributes for behavior customization:

QWeb2.Engine.QWeb2.Engine.prefix¶
    

Prefix used to recognize directives during parsing. A string. By default, `t`.

QWeb2.Engine.QWeb2.Engine.debug¶
    

Boolean flag putting the engine in «debug mode». Normally, QWeb intercepts any error raised during template execution. In debug mode, it leaves all exceptions go through without intercepting them.

QWeb2.Engine.QWeb2.Engine.jQuery¶
    

The jQuery instance used during template inheritance processing. Defaults to `window.jQuery`.

QWeb2.Engine.QWeb2.Engine.preprocess_node¶
    

A `Function`. If present, called before compiling each DOM node to template code. In Odoo Web, this is used to automatically translate text content and some attributes in templates. Defaults to `null`.

1
    

it is similar in that to [Genshi](https://genshi.edgewall.org/), although it does not use (and has no support for) [XML namespaces](https://en.wikipedia.org/wiki/XML_namespace)

2
    

although it uses a few others, either for historical reasons or because they remain better fits for the use case. Odoo 9.0 still depends on [Jinja](http://jinja.pocoo.org/) and [Mako](https://www.makotemplates.org/).

[ __Edit on GitHub](https://github.com/odoo/Documentation/edit/18.0/content/developer/reference/frontend/qweb.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](odoo_editor.html "Odoo Editor") |
  * [precedente](mobile.html "Mobile JavaScript") |
  * [Odoo 18.0 documentazione](../../../index-2.html) »
  * [Developer](../../../developer.html) »
  * [Reference](../../reference.html) »
  * [Web framework](../frontend.html) »
  * QWeb Templates


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: Optical Character Recognition
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