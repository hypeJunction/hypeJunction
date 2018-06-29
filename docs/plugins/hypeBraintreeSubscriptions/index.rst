hypeBraintreeSubscriptions
==========================

Braintree integration for hypeSubscriptions

Currencies
~~~~~~~~~~

If you are using multiple currencies, make sure to set up a Braintree merchant account for each currency.

Subscriptions
~~~~~~~~~~~~~

Braintree API does not allow plans to be created via API calls, so you will need to setup your plans via Braintree control panel and then import them. Plans will be matched by their plan_id, so you can duplicate your existing plans on Braintree.

