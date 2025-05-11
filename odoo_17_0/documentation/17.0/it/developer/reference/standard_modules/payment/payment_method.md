# Payment Method — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](payment_provider.html "Payment Provider") |
  * [precedente](../payment.html "Payment") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Developer](../../../../developer.html) »
  * [Reference](../../../reference.html) »
  * [Standard modules](../../standard_modules.html) »
  * [Payment](../payment.html) »
  * Payment Method



# Payment Method¶

_class _odoo.addons.payment.models.payment_method.PaymentMethod[[sorgente]](https://github.com/odoo/odoo/blob/17.0/addons/payment/models/payment_method.py#L8)¶
    

_get_compatible_payment_methods(_provider_ids_ , _partner_id_ , _currency_id =None_, _force_tokenization =False_, _is_express_checkout =False_, _** kwargs_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/addons/payment/models/payment_method.py#L199)¶
    

Search and return the payment methods matching the compatibility criteria.

The compatibility criteria are that payment methods must: be supported by at least one of the providers; support the country of the partner if it exists; be primary payment methods (not a brand). If provided, the optional keyword arguments further refine the criteria.

Parametri
    

  * **provider_ids** ([_list_](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)")) – The list of providers by which the payment methods must be at least partially supported to be considered compatible, as a list of `payment.provider` ids.

  * **partner_id** ([_int_](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")) – The partner making the payment, as a `res.partner` id.

  * **currency_id** ([_int_](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")) – The payment currency, if known beforehand, as a `res.currency` id.

  * **force_tokenization** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – Whether only payment methods supporting tokenization can be matched.

  * **is_express_checkout** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – Whether the payment is made through express checkout.

  * **kwargs** ([_dict_](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")) – Optional data. This parameter is not used here.



Ritorna
    

The compatible payment methods.

Tipo di ritorno
    

payment.method

_get_from_code(_code_ , _mapping =None_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/addons/payment/models/payment_method.py#L257)¶
    

Get the payment method corresponding to the given provider-specific code.

If a mapping is given, the search uses the generic payment method code that corresponds to the given provider-specific code.

Parametri
    

  * **code** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – The provider-specific code of the payment method to get.

  * **mapping** ([_dict_](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")) – A non-exhaustive mapping of generic payment method codes to provider-specific codes.



Ritorna
    

The corresponding payment method, if any.

Type
    

payment.method

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/developer/reference/standard_modules/payment/payment_method.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](payment_provider.html "Payment Provider") |
  * [precedente](../payment.html "Payment") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Developer](../../../../developer.html) »
  * [Reference](../../../reference.html) »
  * [Standard modules](../../standard_modules.html) »
  * [Payment](../payment.html) »
  * Payment Method


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: Optical Character Recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-app purchases