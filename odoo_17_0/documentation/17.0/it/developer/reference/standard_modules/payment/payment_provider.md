# Payment Provider — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](payment_token.html "Payment Token") |
  * [precedente](payment_method.html "Payment Method") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Developer](../../../../developer.html) »
  * [Reference](../../../reference.html) »
  * [Standard modules](../../standard_modules.html) »
  * [Payment](../payment.html) »
  * Payment Provider



# Payment Provider¶

_class _odoo.addons.payment.models.payment_provider.PaymentProvider[[sorgente]](https://github.com/odoo/odoo/blob/17.0/addons/payment/models/payment_provider.py#L14)¶
    

_compute_feature_support_fields()[[sorgente]](https://github.com/odoo/odoo/blob/17.0/addons/payment/models/payment_provider.py#L261)¶
    

Compute the feature support fields based on the provider.

Feature support fields are used to specify which additional features are supported by a given provider. These fields are as follows:

  * `support_express_checkout`: Whether the «express checkout» feature is supported. `False` by default.

  * `support_manual_capture`: Whether the «manual capture» feature is supported. `False` by default.

  * `support_refund`: Which type of the «refunds» feature is supported: `None`, `'full_only'`, or `'partial'`. `None` by default.

  * `support_tokenization`: Whether the «tokenization feature» is supported. `False` by default.




For a provider to specify that it supports additional features, it must override this method and set the related feature support fields to the desired value on the appropriate `payment.provider` records.

Ritorna
    

None

_compute_view_configuration_fields()[[sorgente]](https://github.com/odoo/odoo/blob/17.0/addons/payment/models/payment_provider.py#L225)¶
    

Compute the view configuration fields based on the provider.

View configuration fields are used to hide specific elements (notebook pages, fields, etc.) from the form view of payment providers. These fields are set to `True` by default and are as follows:

  * `show_credentials_page`: Whether the «Credentials» notebook page should be shown.

  * `show_allow_tokenization`: Whether the `allow_tokenization` field should be shown.

  * `show_allow_express_checkout`: Whether the `allow_express_checkout` field should be shown.

  * `show_pre_msg`: Whether the `pre_msg` field should be shown.

  * `show_pending_msg`: Whether the `pending_msg` field should be shown.

  * `show_auth_msg`: Whether the `auth_msg` field should be shown.

  * `show_done_msg`: Whether the `done_msg` field should be shown.

  * `show_cancel_msg`: Whether the `cancel_msg` field should be shown.

  * `require_currency`: Whether the `available_currency_ids` field shoud be required.




For a provider to hide specific elements of the form view, it must override this method and set the related view configuration fields to `False` on the appropriate `payment.provider` records.

Ritorna
    

None

_get_compatible_providers(_company_id_ , _partner_id_ , _amount_ , _currency_id =None_, _force_tokenization =False_, _is_express_checkout =False_, _is_validation =False_, _** kwargs_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/addons/payment/models/payment_provider.py#L497)¶
    

Search and return the providers matching the compatibility criteria.

The compatibility criteria are that providers must: not be disabled; be in the company that is provided; support the country of the partner if it exists; be compatible with the currency if provided. If provided, the optional keyword arguments further refine the criteria.

Parametri
    

  * **company_id** ([_int_](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")) – The company to which providers must belong, as a `res.company` id.

  * **partner_id** ([_int_](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")) – The partner making the payment, as a `res.partner` id.

  * **amount** ([_float_](https://docs.python.org/3/library/functions.html#float "\(in Python v3.13\)")) – The amount to pay. `0` for validation transactions.

  * **currency_id** ([_int_](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")) – The payment currency, if known beforehand, as a `res.currency` id.

  * **force_tokenization** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – Whether only providers allowing tokenization can be matched.

  * **is_express_checkout** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – Whether the payment is made through express checkout.

  * **is_validation** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – Whether the operation is a validation.

  * **kwargs** ([_dict_](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")) – Optional data. This parameter is not used here.



Ritorna
    

The compatible providers.

Tipo di ritorno
    

payment.provider

_get_redirect_form_view(_is_validation =False_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/addons/payment/models/payment_provider.py#L665)¶
    

Return the view of the template used to render the redirect form.

For a provider to return a different view depending on whether the operation is a validation, it must override this method and return the appropriate view.

Note: `self.ensure_one()`

Parametri
    

**is_validation** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – Whether the operation is a validation.

Ritorna
    

The view of the redirect form template.

Tipo di ritorno
    

record of `ir.ui.view`

_get_validation_amount()[[sorgente]](https://github.com/odoo/odoo/blob/17.0/addons/payment/models/payment_provider.py#L618)¶
    

Return the amount to use for validation operations.

For a provider to support tokenization, it must override this method and return the validation amount. If it is `0`, it is not necessary to create the override.

Note: `self.ensure_one()`

Ritorna
    

The validation amount.

Tipo di ritorno
    

[float](https://docs.python.org/3/library/functions.html#float "\(in Python v3.13\)")

_get_validation_currency()[[sorgente]](https://github.com/odoo/odoo/blob/17.0/addons/payment/models/payment_provider.py#L632)¶
    

Return the currency to use for validation operations.

The validation currency must be supported by both the provider and the payment method. If the payment method is not passed, only the provider’s supported currencies are considered. If no suitable currency is found, the provider’s company’s currency is returned instead.

For a provider to support tokenization and specify a different validation currency, it must override this method and return the appropriate validation currency.

Note: `self.ensure_one()`

Ritorna
    

The validation currency.

Tipo di ritorno
    

recordset of `res.currency`

_is_tokenization_required(_** kwargs_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/addons/payment/models/payment_provider.py#L593)¶
    

Return whether tokenizing the transaction is required given its context.

For a module to make the tokenization required based on the payment context, it must override this method and return whether it is required.

Parametri
    

**kwargs** ([_dict_](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")) – The payment context. This parameter is not used here.

Ritorna
    

Whether tokenizing the transaction is required.

Tipo di ritorno
    

[bool](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")

_should_build_inline_form(_is_validation =False_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/addons/payment/models/payment_provider.py#L605)¶
    

Return whether the inline payment form should be instantiated.

For a provider to handle both direct payments and payments with redirection, it must override this method and return whether the inline payment form should be instantiated (i.e. if the payment should be direct) based on the operation (online payment or validation).

Parametri
    

**is_validation** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – Whether the operation is a validation.

Ritorna
    

Whether the inline form should be instantiated.

Tipo di ritorno
    

[bool](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")

_get_removal_values()[[sorgente]](https://github.com/odoo/odoo/blob/17.0/addons/payment/models/payment_provider.py#L706)¶
    

Return the values to update a provider with when its module is uninstalled.

For a module to specify additional removal values, it must override this method and complete the generic values with its specific values.

Ritorna
    

The removal values to update the removed provider with.

Tipo di ritorno
    

[dict](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/developer/reference/standard_modules/payment/payment_provider.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](payment_token.html "Payment Token") |
  * [precedente](payment_method.html "Payment Method") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Developer](../../../../developer.html) »
  * [Reference](../../../reference.html) »
  * [Standard modules](../../standard_modules.html) »
  * [Payment](../payment.html) »
  * Payment Provider


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: Optical Character Recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-app purchases