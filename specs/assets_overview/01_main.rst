=====  ===============  =========  ==========
epic        title        author     created
=====  ===============  =========  ==========
`64`_  Assets overview  tschubotz  2019-01-22
=====  ===============  =========  ==========

.. _64: https://github.com/gnosis/safe/issues/64

.. _Main:


#. `Main`_
#. `User Interface`_

.. sectnum::
.. contents:: Table of Contents
    :local:
    :depth: 2

Problem Definition
---------------------

- User needs to see an overview of all their assets (ETH + ERC20 tokens)
- User needs a way to start the transfer funds flow
- User needs a way to receive funds.

Inputs
-----------

- Existing Safe.
- List of enabled tokens (Can be empty).


Outputs
------------

- Amount of ETH stored.
- Amount of enabled tokens stored.
- Identicon of the Safe address.
- `Short Safe address`_
- Safe name if multiple safes are supported

.. _`Short Safe address`: ../common/format_addresses.rst#full-checksummed-address


Use Case Scenarios
-----------------------

Happy Case
~~~~~~~~~~~~~~~

Preconditions
+++++++++++++

- Safe exists on the device.

Steps
+++++

1. User sees current ETH balance
2. User sees current balances of all enabled tokens.
3. User can scroll to see all available tokens balances.
4. User sees identicon and shortened Safe address.
5. User sees Safe name (If multiple Safes are supported)
6. User taps an asset row.

Postconditions
++++++++++++++

- "Send ETH/token" flow is started.


Reload balances
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

inherits from `Happy Case`_

Steps
+++++

6. User pulls to reload.

Postconditions
++++++++++++++

- User sees loading indicator.
- Balances are reloaded.


Receive funds
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

inherits from `Happy Case`_

Steps
+++++

6. User taps identicon.

Postconditions
++++++++++++++

- "Receive funds" screen is opened.


Manage tokens
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

inherits from `Happy Case`_

Steps
+++++

6. User taps "Add token".

Postconditions
++++++++++++++

- "Manage token" screen is opened.


No internet - first time
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

inherits from `Happy Case`_

Steps
+++++

1. User opens the assets overview screen.

Postconditions
++++++++++++++

- User sees indication that there is no internet connection.


No internet - balances loaded before
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

inherits from `No internet - first time`_

Steps
+++++

1. User opens the assets overview screen.

Postconditions
++++++++++++++

- User sees indication that there is no internet connection.
- User sees cached balanes from before.


.. _`User Interface`: 02_user_interface.rst
