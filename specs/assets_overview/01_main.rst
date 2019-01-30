=====  ===============  =========  ==========
epic        title        author     created
=====  ===============  =========  ==========
`64`_  Assets overview  tschubotz  2019-01-22
=====  ===============  =========  ==========

.. _64: https://github.com/gnosis/safe/issues/64

.. _Main:


#. `Main`_
#. `User Interface`_
#. `Technical Details`_

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
- Enabled tokens.


Outputs
------------

- Amount of ETH stored.
- Amount of enabeld tokens stored.
- Identicon of the Safe address.
- Shortened Safe address (0x12...3456)
- Safe name (only for Android right now, since iOS doesn't support multiple
  Safes. yet.)


Use Case Scenarios
-----------------------

Happy Case
~~~~~~~~~~~~~~~

Preconditions
+++++++++++++

- Safe exists on the device.

Steps
+++++

1. User sees up to date ETH balance
2. User sees up to date balances of all enabled tokens.
3. User can scroll to see all available tokens balances.
4. User see identicon and shortened Safe address.
5. User sees Safe name (If multiple Safes are supported)
6. User taps an asset row.

Postconditions
++++++++++++++

- "Send ETH/token" flow is started.


Happy Case - Receive funds
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

inherits from `Happy Case`_

Steps
+++++

6. User taps identicon.

Postconditions
++++++++++++++

- "Receive funds" screen is opened.

.. _`User Interface`: 02_user_interface.rst
.. _`Technical Details`: 03_technical_details.rst
