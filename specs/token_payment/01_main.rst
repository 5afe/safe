==========================================================
Token payment
==========================================================

=====  =============  =========  ==========
epic       title       author     created
=====  =============  =========  ==========
`89`_  Token payment  tschubotz  2019-05-15
=====  =============  =========  ==========

.. _89: https://github.com/gnosis/safe/issues/89

.. sectnum::
.. contents:: Table of Contents
    :local:


What is this feature about? (1 sentence)
----------------------------------------

This feature will enable users to pay transaction fees with tokens like DAI, OWL or others.


Why is it needed? What is the value? For whom do we build it?
----------------------------------------------------------------

Currently, all transaction fees have to be paid in ETH ("gas"). That means, for all transactions, a user needs ETH. They are unable to make transactions without ETH, even if they own a significant amount of funds in tokens. 
Users were asking for this features. One of the reasons is, that they would like to pay fees with a stable token like DAI or OWL in order to be more independent from the volatile ETH price.
Additionally, this creates a use case for GNO holders to use their OWL, which is important for Gnosis as a company.


High-level overview of the feature
----------------------------------

We use meta-transactions anyway already, i.e. our relay service pays for transaction fees in ETH and then gets refunded in ETH from the user's Safe as part of the transaction. We would change this, so that the refund happens in a token.
There will a list of tokens that the relay service accepts as payment. We will also have to incorporate a price oracle to determine the fee amount. DutchX will be one price oracle.

This feature affects the following flows & screens:

- `Safe creation`_
- `Send funds`_
- `Connect browser extension`_
- `Replace browser extension`_
- `Replace recovery phrase`_
- `Recover Safe`_
- `Menu`_

.. _`Safe creation`: 02_create_safe.rst
.. _`Menu`: 03_settings.rst
.. _`Send funds`: 04_send_funds.rst
.. _`Connect browser extension`: 05_connect_browser_extension.rst
.. _`Replace browser extension`: 06_replace_browser_extension.rst
.. _`Replace recovery phrase`: 07_replace_recovery_phrase.rst
.. _`Recover Safe`: 08_recover_safe.rst


The payment method is set per Safe but can be changed before making a transaction and also via the menu. 

The smart contracts and the backend are already ready for this change. We "just" have to incorporate this into the frontends now.

