+--------+-----------------+
| issue  | title           |
+--------+-----------------+
| 68_    | Receive funds   |
+--------+-----------------+

.. _68: https://github.com/gnosis/safe/issues/68

Receive funds
===============

1. `Main`_
2. `User Interface`_
3. `External Communication`_
4. Other_

.. _Main:

.. contents:: Table of Contents
    :depth: 3

1. Problem Definition
---------------------

- User wants to receive funds
- User should be able to share their wallet address via different ways
    - Via QR code for scanning.
    - Copy to clipboard.
    - Via other services on their phone.
- There should be a way to double check if the other person has the
  correct shared address.

2. Inputs
-----------

- Address of the currently selected Safe.

3. Outputs
------------

- Address is clearly visible.
- Identicon is visible.
- QR code can be scanned.
- Address can be shared via other apps
- Address can by copied to clipboard.


4. Use Case Scenarios
-----------------------

4.1. Happy Case
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

4.2. Happy Case sharing via 3rd party app
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

inherits from `4.1. Happy Case`_

Steps
+++++
4. Open system share dialog
5. Select 3rd part app to share

Postconditions
++++++++++++++

- Address was shared to 3rd party app

.. _`User Interface`: 02_user_interface.rst
.. _`External Communication`: 03_external_communication.rst
.. _Other: 04_other.rst
