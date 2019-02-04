==========================================================
Connect browser extension
==========================================================

=====  =========================  =========  ==========
epic             title             author     created
=====  =========================  =========  ==========
`73`_  Connect browser extension  tschubotz  2019-02-04
=====  =========================  =========  ==========

.. _73: https://github.com/gnosis/safe/issues/73

.. _Main:


#. `Main`_
#. `User Interface`_
#. `Technical Details`_

.. sectnum::
.. contents:: Table of Contents
    :local:
    :depth: 2


Problem Definition
-------------------------------

* User has set up their Safe without a browser extension connected but needs a way to enable 2FA.
* User has set up their Safe without a browser extension connected but needs a way to interact with desktop dapps now.

Inputs
-----------

* Existing Safe
* Installed browser extension

Outputs
------------

* Browser extension is added as owner of the Safe on-chain.
* Browser extension and mobile app can send & receive push notifications concerning transactions.

Use Case Scenarios
-----------------------

Happy Case
~~~~~~~~~~~~~~~~~

Preconditions
+++++++++++++

* User has an existing Safe without a connected browser extension.
* User has installed the browser extension on their Chrome browser

Steps
+++++

1. User opens settings
2. User selects "Connect browser extension"
3. User scans QR code in their browser extension.
4. User reviews transaction
5. User submits transaction with biometric auth or via password.


Postconditions
++++++++++++++

* User ends up on the transaction list.
* Transaction has been submitted to the blockchain.
* Upon sucessful transaction, browser extension is connected.


Invalid QR code scanned
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Inherits from the `Happy Case`_

Steps
+++++

3. User scans invalid QR code

Postconditions
++++++++++++++

- User sees error


Insufficient funds
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Inherits from the `Happy Case`_

Steps
+++++

3. User sees insufficient funds

Postconditions
++++++++++++++

- User cannot continue


.. _`User Interface`: 02_user_interface.rst
.. _`Technical Details`: 03_technical_details.rst

