# Payment Token — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](payment_transaction.html "Payment Transaction") |
  * [precedente](payment_provider.html "Payment Provider") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Developer](../../../../developer.html) »
  * [Reference](../../../reference.html) »
  * [Standard modules](../../standard_modules.html) »
  * [Payment](../payment.html) »
  * Payment Token



# Payment Token¶

_class _odoo.addons.payment.models.payment_token.PaymentToken[[sorgente]](https://github.com/odoo/odoo/blob/17.0/addons/payment/models/payment_token.py#L9)¶
    

_get_available_tokens(_providers_ids_ , _partner_id_ , _is_validation =False_, _** kwargs_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/addons/payment/models/payment_token.py#L113)¶
    

Return the available tokens linked to the given providers and partner.

For a module to retrieve the available tokens, it must override this method and add information in the kwargs to define the context of the request.

Parametri
    

  * **providers_ids** ([_list_](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)")) – The ids of the providers available for the transaction.

  * **partner_id** ([_int_](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")) – The id of the partner.

  * **is_validation** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – Whether the transaction is a validation operation.

  * **kwargs** ([_dict_](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")) – Locally unused keywords arguments.



Ritorna
    

The available tokens.

Tipo di ritorno
    

payment.token

_build_display_name(_* args_, _max_length =34_, _should_pad =True_, _** kwargs_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/addons/payment/models/payment_token.py#L138)¶
    

Build a token name of the desired maximum length with the format `•••• 1234`.

The payment details are padded on the left with up to four padding characters. The padding is only added if there is enough room for it. If not, it is either reduced or not added at all. If there is not enough room for the payment details either, they are trimmed from the left.

For a module to customize the display name of a token, it must override this method and return the customized display name.

Note: `self.ensure_one()`

Parametri
    

  * **args** ([_list_](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)")) – The arguments passed by QWeb when calling this method.

  * **max_length** ([_int_](https://docs.python.org/3/library/functions.html#int "\(in Python v3.13\)")) – The desired maximum length of the token name. The default is `34` to fit the largest IBANs.

  * **should_pad** ([_bool_](https://docs.python.org/3/library/functions.html#bool "\(in Python v3.13\)")) – Whether the token should be padded.

  * **kwargs** ([_dict_](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")) – Optional data used in overrides of this method.



Ritorna
    

The padded token name.

Tipo di ritorno
    

[str](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")

_get_specific_create_values(_provider_code_ , _values_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/addons/payment/models/payment_token.py#L62)¶
    

Complete the values of the `create` method with provider-specific values.

For a provider to add its own create values, it must overwrite this method and return a dict of values. Provider-specific values take precedence over those of the dict of generic create values.

Parametri
    

  * **provider_code** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – The code of the provider managing the token.

  * **values** ([_dict_](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")) – The original create values.



Ritorna
    

The dict of provider-specific create values.

Tipo di ritorno
    

[dict](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")

_handle_archiving()[[sorgente]](https://github.com/odoo/odoo/blob/17.0/addons/payment/models/payment_token.py#L101)¶
    

Handle the archiving of tokens.

For a module to perform additional operations when a token is archived, it must override this method.

Ritorna
    

None

get_linked_records_info()[[sorgente]](https://github.com/odoo/odoo/blob/17.0/addons/payment/models/payment_token.py#L177)¶
    

Return a list of information about records linked to the current token.

For a module to implement payments and link documents to a token, it must override this method and add information about linked document records to the returned list.

The information must be structured as a dict with the following keys:

  * `description`: The description of the record’s model (e.g. «Subscription»).

  * `id`: The id of the record.

  * `name`: The name of the record.

  * `url`: The url to access the record.




Note: `self.ensure_one()`

Ritorna
    

The list of information about the linked document records.

Tipo di ritorno
    

[list](https://docs.python.org/3/library/stdtypes.html#list "\(in Python v3.13\)")

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/developer/reference/standard_modules/payment/payment_token.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](payment_transaction.html "Payment Transaction") |
  * [precedente](payment_provider.html "Payment Provider") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Developer](../../../../developer.html) »
  * [Reference](../../../reference.html) »
  * [Standard modules](../../standard_modules.html) »
  * [Payment](../payment.html) »
  * Payment Token


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: Optical Character Recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-app purchases