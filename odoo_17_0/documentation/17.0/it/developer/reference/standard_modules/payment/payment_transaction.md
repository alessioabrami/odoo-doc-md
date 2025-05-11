# Payment Transaction — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../cli.html "Command-line interface \(CLI\)") |
  * [precedente](payment_token.html "Payment Token") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Developer](../../../../developer.html) »
  * [Reference](../../../reference.html) »
  * [Standard modules](../../standard_modules.html) »
  * [Payment](../payment.html) »
  * Payment Transaction



# Payment Transaction¶

_class _odoo.addons.payment.models.payment_transaction.PaymentTransaction[[sorgente]](https://github.com/odoo/odoo/blob/17.0/addons/payment/models/payment_transaction.py#L23)¶
    

_compute_reference(_provider_code_ , _prefix =None_, _separator ='-'_, _** kwargs_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/addons/payment/models/payment_transaction.py#L320)¶
    

Compute a unique reference for the transaction.

The reference corresponds to the prefix if no other transaction with that prefix already exists. Otherwise, it follows the pattern `{computed_prefix}{separator}{sequence_number}` where:

  * `{computed_prefix}` is:

    * The provided custom prefix, if any.

    * The computation result of `_compute_reference_prefix()` if the custom prefix is not filled, but the kwargs are.

    * `'tx-{datetime}'` if neither the custom prefix nor the kwargs are filled.

  * `{separator}` is the string that separates the prefix from the sequence number.

  * `{sequence_number}` is the next integer in the sequence of references sharing the same prefix. The sequence starts with `1` if there is only one matching reference.




Example

  * Given the custom prefix `'example'` which has no match with an existing reference, the full reference will be `'example'`.

  * Given the custom prefix `'example'` which matches the existing reference `'example'`, and the custom separator `'-'`, the full reference will be `'example-1'`.

  * Given the kwargs `{'invoice_ids': [1, 2]}`, the custom separator `'-'` and no custom prefix, the full reference will be `'INV1-INV2'` (or similar) if no existing reference has the same prefix, or `'INV1-INV2-n'` if `n` existing references have the same prefix.




Parametri
    

  * **provider_code** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – The code of the provider handling the transaction.

  * **prefix** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – The custom prefix used to compute the full reference.

  * **separator** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – The custom separator used to separate the prefix from the suffix.

  * **kwargs** ([_dict_](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")) – Optional values passed to `_compute_reference_prefix()` if no custom prefix is provided.



Ritorna
    

The unique reference for the transaction.

Tipo di ritorno
    

[str](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")

_compute_reference_prefix(_provider_code_ , _separator_ , _** values_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/addons/payment/models/payment_transaction.py#L401)¶
    

Compute the reference prefix from the transaction values.

Note: This method should be called in sudo mode to give access to the documents (invoices, sales orders) referenced in the transaction values.

Parametri
    

  * **provider_code** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – The code of the provider handling the transaction.

  * **separator** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – The custom separator used to separate parts of the computed reference prefix.

  * **values** ([_dict_](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")) – The transaction values used to compute the reference prefix.



Ritorna
    

The computed reference prefix.

Tipo di ritorno
    

[str](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")

_get_post_processing_values()[[sorgente]](https://github.com/odoo/odoo/blob/17.0/addons/payment/models/payment_transaction.py#L915)¶
    

Return a dict of values used to display the status of the transaction.

For a provider to handle transaction status display, it must override this method and return a dict of values. Provider-specific values take precedence over those of the dict of generic post-processing values.

The returned dict contains the following entries:

  * `provider_code`: The code of the provider.

  * `provider_name`: The name of the provider.

  * `reference`: The reference of the transaction.

  * `amount`: The rounded amount of the transaction.

  * `currency_id`: The currency of the transaction, as a `res.currency` id.

  * `state`: The transaction state: `draft`, `pending`, `authorized`, `done`, `cancel`, or `error`.

  * `state_message`: The information message about the state.

  * `operation`: The operation of the transaction.

  * `is_post_processed`: Whether the transaction has already been post-processed.

  * `landing_route`: The route the user is redirected to after the transaction.

  * Additional provider-specific entries.




Note: `self.ensure_one()`

Ritorna
    

The dict of processing values.

Tipo di ritorno
    

[dict](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")

_get_specific_create_values(_provider_code_ , _values_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/addons/payment/models/payment_transaction.py#L219)¶
    

Complete the values of the `create` method with provider-specific values.

For a provider to add its own create values, it must overwrite this method and return a dict of values. Provider-specific values take precedence over those of the dict of generic create values.

Parametri
    

  * **provider_code** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – The code of the provider that handled the transaction.

  * **values** ([_dict_](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")) – The original create values.



Ritorna
    

The dict of provider-specific create values.

Tipo di ritorno
    

[dict](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")

_get_specific_processing_values(_processing_values_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/addons/payment/models/payment_transaction.py#L490)¶
    

Return a dict of provider-specific values used to process the transaction.

For a provider to add its own processing values, it must overwrite this method and return a dict of provider-specific values based on the generic values returned by this method. Provider-specific values take precedence over those of the dict of generic processing values.

Parametri
    

**processing_values** ([_dict_](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")) – The generic processing values of the transaction.

Ritorna
    

The dict of provider-specific processing values.

Tipo di ritorno
    

[dict](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")

_get_specific_rendering_values(_processing_values_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/addons/payment/models/payment_transaction.py#L504)¶
    

Return a dict of provider-specific values used to render the redirect form.

For a provider to add its own rendering values, it must overwrite this method and return a dict of provider-specific values based on the processing values (provider-specific processing values included).

Parametri
    

**processing_values** ([_dict_](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")) – The processing values of the transaction.

Ritorna
    

The dict of provider-specific rendering values.

Tipo di ritorno
    

[dict](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")

_get_tx_from_notification_data(_provider_code_ , _notification_data_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/addons/payment/models/payment_transaction.py#L672)¶
    

Find the transaction based on the notification data.

For a provider to handle transaction processing, it must overwrite this method and return the transaction matching the notification data.

Parametri
    

  * **provider_code** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – The code of the provider handling the transaction.

  * **notification_data** ([_dict_](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")) – The notification data sent by the provider.



Ritorna
    

The transaction, if found.

Tipo di ritorno
    

recordset of `payment.transaction`

_handle_notification_data(_provider_code_ , _notification_data_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/addons/payment/models/payment_transaction.py#L659)¶
    

Match the transaction with the notification data, update its state and return it.

Parametri
    

  * **provider_code** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – The code of the provider handling the transaction.

  * **notification_data** ([_dict_](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")) – The notification data sent by the provider.



Ritorna
    

The transaction.

Tipo di ritorno
    

recordset of `payment.transaction`

_process_notification_data(_notification_data_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/addons/payment/models/payment_transaction.py#L685)¶
    

Update the transaction state and the provider reference based on the notification data.

This method should usually not be called directly. The correct method to call upon receiving notification data is `_handle_notification_data()`.

For a provider to handle transaction processing, it must overwrite this method and process the notification data.

Note: `self.ensure_one()`

Parametri
    

**notification_data** ([_dict_](https://docs.python.org/3/library/stdtypes.html#dict "\(in Python v3.13\)")) – The notification data sent by the provider.

Ritorna
    

None

_send_capture_request(_amount_to_capture =None_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/addons/payment/models/payment_transaction.py#L567)¶
    

Request the provider handling the transaction to capture the payment.

For partial captures, create a child transaction linked to the source transaction.

For a provider to support authorization, it must override this method and make an API request to capture the payment.

Note: `self.ensure_one()`

Parametri
    

**amount_to_capture** ([_float_](https://docs.python.org/3/library/functions.html#float "\(in Python v3.13\)")) – The amount to capture.

Ritorna
    

The created capture child transaction, if any.

Tipo di ritorno
    

`payment.transaction`

_send_payment_request()[[sorgente]](https://github.com/odoo/odoo/blob/17.0/addons/payment/models/payment_transaction.py#L531)¶
    

Request the provider handling the transaction to make the payment.

This method is exclusively used to make payments by token, which correspond to both the `online_token` and the `offline` transaction’s `operation` field.

For a provider to support tokenization, it must override this method and make an API request to make a payment.

Note: `self.ensure_one()`

Ritorna
    

None

_send_refund_request(_amount_to_refund =None_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/addons/payment/models/payment_transaction.py#L548)¶
    

Request the provider handling the transaction to refund it.

For a provider to support refunds, it must override this method and make an API request to make a refund.

Note: `self.ensure_one()`

Parametri
    

**amount_to_refund** ([_float_](https://docs.python.org/3/library/functions.html#float "\(in Python v3.13\)")) – The amount to be refunded.

Ritorna
    

The refund transaction created to process the refund request.

Tipo di ritorno
    

recordset of `payment.transaction`

_send_void_request(_amount_to_void =None_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/addons/payment/models/payment_transaction.py#L588)¶
    

Request the provider handling the transaction to void the payment.

For partial voids, create a child transaction linked to the source transaction.

For a provider to support authorization, it must override this method and make an API request to void the payment.

Note: `self.ensure_one()`

Parametri
    

**amount_to_void** ([_float_](https://docs.python.org/3/library/functions.html#float "\(in Python v3.13\)")) – The amount to be voided.

Ritorna
    

The created void child transaction, if any.

Tipo di ritorno
    

payment.transaction

_set_authorized(_state_message =None_, _extra_allowed_states =()_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/addons/payment/models/payment_transaction.py#L718)¶
    

Update the transactions” state to `authorized`.

Parametri
    

  * **state_message** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – The reason for setting the transactions in the state `authorized`.

  * **extra_allowed_states** ([_tuple_](https://docs.python.org/3/library/stdtypes.html#tuple "\(in Python v3.13\)") _[_[_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _]_) – The extra states that should be considered allowed target states for the source state “authorized”.



Ritorna
    

The updated transactions.

Tipo di ritorno
    

recordset of `payment.transaction`

_set_canceled(_state_message =None_, _extra_allowed_states =()_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/addons/payment/models/payment_transaction.py#L753)¶
    

Update the transactions” state to `cancel`.

Parametri
    

  * **state_message** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – The reason for setting the transactions in the state `cancel`.

  * **extra_allowed_states** ([_tuple_](https://docs.python.org/3/library/stdtypes.html#tuple "\(in Python v3.13\)") _[_[_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _]_) – The extra states that should be considered allowed target states for the source state “canceled”.



Ritorna
    

The updated transactions.

Tipo di ritorno
    

recordset of `payment.transaction`

_set_done(_state_message =None_, _extra_allowed_states =()_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/addons/payment/models/payment_transaction.py#L735)¶
    

Update the transactions” state to `done`.

Parametri
    

  * **state_message** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – The reason for setting the transactions in the state `done`.

  * **extra_allowed_states** ([_tuple_](https://docs.python.org/3/library/stdtypes.html#tuple "\(in Python v3.13\)") _[_[_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _]_) – The extra states that should be considered allowed target states for the source state “done”.



Ritorna
    

The updated transactions.

Tipo di ritorno
    

recordset of `payment.transaction`

_set_error(_state_message_ , _extra_allowed_states =()_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/addons/payment/models/payment_transaction.py#L771)¶
    

Update the transactions” state to `error`.

Parametri
    

  * **state_message** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – The reason for setting the transactions in the state `error`.

  * **extra_allowed_states** ([_tuple_](https://docs.python.org/3/library/stdtypes.html#tuple "\(in Python v3.13\)") _[_[_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _]_) – The extra states that should be considered allowed target states for the source state “error”.



Ritorna
    

The updated transactions.

Tipo di ritorno
    

recordset of `payment.transaction`

_set_pending(_state_message =None_, _extra_allowed_states =()_)[[sorgente]](https://github.com/odoo/odoo/blob/17.0/addons/payment/models/payment_transaction.py#L701)¶
    

Update the transactions” state to `pending`.

Parametri
    

  * **state_message** ([_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)")) – The reason for setting the transactions in the state `pending`.

  * **extra_allowed_states** ([_tuple_](https://docs.python.org/3/library/stdtypes.html#tuple "\(in Python v3.13\)") _[_[_str_](https://docs.python.org/3/library/stdtypes.html#str "\(in Python v3.13\)") _]_) – The extra states that should be considered allowed target states for the source state “pending”.



Ritorna
    

The updated transactions.

Tipo di ritorno
    

recordset of `payment.transaction`

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/developer/reference/standard_modules/payment/payment_transaction.rst)

### Navigazione

  * [indice](../../../../genindex.html "Indice generale")
  * [moduli](../../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../../cli.html "Command-line interface \(CLI\)") |
  * [precedente](payment_token.html "Payment Token") |
  * [Odoo 17.0 documentazione](../../../../index-2.html) »
  * [Developer](../../../../developer.html) »
  * [Reference](../../../reference.html) »
  * [Standard modules](../../standard_modules.html) »
  * [Payment](../payment.html) »
  * Payment Transaction


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: Optical Character Recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-app purchases