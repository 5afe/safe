==========================================================
Receive funds
==========================================================

=====  =============  =========  ==========
 68        title      tschubotz   created
=====  =============  =========  ==========
`68`_  Receive funds  tschubotz  2019-01-17
=====  =============  =========  ==========

.. _68: https://github.com/gnosis/safe/issues/68

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

- User wants to receive funds
- User should be able to share their wallet address via different ways
    - Via QR code for scanning.
    - Copy to clipboard.
    - Via other services on their phone.
- There should be a way to double check if the other person has the
  correct shared address.

Inputs
-----------

- Address of the currently selected Safe.

Outputs
------------

- Complete checksummed address is visible (with our usual
  address highlighting).
- Identicon is visible.
- QR code can be scanned straight away.
- Address can be shared via other apps
- Address can by copied to clipboard.


Use Case Scenarios
-----------------------

Happy Case
~~~~~~~~~~~~~~~

Preconditions
+++++++++++++

- Safe exists on the device.

Steps
+++++

1. Open receive screen
2. See address
3. See identicon
4. Copy address to clipboard

Postconditions
++++++++++++++

- Address is in the clipboard.

Happy Case sharing via 3rd party app
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

inherits from `Happy Case`_

Steps
+++++
4. Open system share dialog
5. Select 3rd part app to share

Postconditions
++++++++++++++

- Address was shared to 3rd party app
