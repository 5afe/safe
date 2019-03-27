==========================================================
Manage tokens
==========================================================

====  =============  ===================  ==========
epic      title            author          created
====  =============  ===================  ==========
58_   Manage tokens  rmeissner,tschubotz  2019-01-23
====  =============  ===================  ==========

.. _58: https://github.com/gnosis/safe/issues/58

.. _Main:

#. `Main`_
#. `User Interface`_

.. sectnum::
.. contents:: Table of Contents
    :local:
    :depth: 2

Problem Definition
-------------------------------

- A user has more funds than just ETH. So there needs to be a way to display them.
- A user should be able only display the ones that they want to.


Outputs
------------

- Selected tokens for asset overview

Use Case Scenarios
-----------------------

Default tokens
~~~~~~~~~~~~~~~~~~~~

Preconditions
++++++++++++++

- Safe app is setup with a password.
- There are tokens with the default flag set to true.

Steps
+++++

1. Go through Safe creation flow

2. Wait until the Safe creation finished and the asset overview is opened.

Postconditions
++++++++++++++

- User sees ETH.
- User sees all enabled default tokens sorted alphabetically from A-Z by symbol.

Enable token
~~~~~~~~~~~~~~~~~~~~

Preconditions
++++++++++++++

- Safe app is setup and Safe exists on the device.
- There are tokens that could be enabled.

Steps
+++++

1. Go to manage tokens

2. Enable token

3. Go back to the assets overview

Postconditions
++++++++++++++

- User sees the token and its balance on the assets overview.

Hide token
~~~~~~~~~~~~~~~~~~~~

Preconditions
++++++++++++++

- Safe app is setup and Safe exists on the device.
- There is a token enabled.

Steps
+++++

1. Go to manage tokens

2. User sees a list of all enabled tokens.

3. Hide the token

4. Go back to the assets overview

Postconditions
++++++++++++++

- User does not see the token anymore.

Search for tokens
~~~~~~~~~~~~~~~~~~~~

Preconditions
++++++++++++++

- Safe app is setup and Safe exists on the device.
- There are tokens that could be enabled.

Steps
+++++

1. Go to manage tokens

2. Enter a search term

Postconditions
++++++++++++++

- User sees all tokens that include the search term either in there name or in their symbol.
- Matching tokens are shown in alphabetical order from A-Z by their token symbol.

Reorder tokens
~~~~~~~~~~~~~~~

Preconditions
++++++++++++++

- Safe app is setup and Safe exists on the device.
- There are several tokens enabled.

Steps
+++++

1. Go to manage tokens

2. Reorder enabled tokens

3. Go back to the assets overview.

Postconditions
++++++++++++++

- The order of the tokens on the assets overview matches the new order.


.. _`User Interface`: 02_user_interface.rst
