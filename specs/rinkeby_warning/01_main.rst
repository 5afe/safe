==========================================================
Rinkeby warning
==========================================================

======  ===============  =========  ==========
 epic        title        author     created
======  ===============  =========  ==========
`116`_  Rinkeby warning  tschubotz  2019-01-30
======  ===============  =========  ==========

.. _116: https://github.com/gnosis/safe/issues/116

.. _Main:

#. `Main`_
#. `User Interface`_

.. sectnum::
.. contents:: Table of Contents
    :local:
    :depth: 2

Problem Definition
-------------------------------

- Users don't understand the difference between a test network and the
  Ethereum mainnet.
- User sent mainnet funds to a Rinkeby Safe.

Inputs
-----------

- App type (Mainnet / Rinkeby)

Outputs
------------

- User is aware that their are using an app on a test network.

Use Case Scenarios
-----------------------

Happy Case
~~~~~~~~~~~~~~~~~

.. _happy_case_preconditions:

Preconditions
+++++++++++++

- User has the app installed.

.. _happy_case_steps:

Steps
+++++

1. Open app
2. User sees Rinkeby warning
3. User taps the warning label
4. Browser with https://faucet.rinkeby.io opens
5. User goes back


.. _happy_case_postconditions:

Postconditions
++++++++++++++

- User is back on the start screen


Happy Case - Safe creation
~~~~~~~~~~~~~~~~~~~~~~~~~~

Preconditions
+++++++++++++

- User has set up the app.
- User is on the screen where they can start creating their first Safe.

Steps
+++++

1. User sees Rinkeby warning
2. User taps the warning label
3. Browser with https://faucet.rinkeby.io opens
4. User goes back

Postconditions
++++++++++++++

- User is back on the screen to start creating a Safe.


**Further use case scenarios are omitted since this is just about adding
a label. Please refer to `User Interface`_ for details about where to add
the label.**

.. _`User Interface`: 02_user_interface.rst
