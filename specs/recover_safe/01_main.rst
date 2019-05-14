==========================================================
Recover Safe
==========================================================

=====  ============  =========  ==========
epic      title       author     created
=====  ============  =========  ==========
`90`_  Recover_Safe  tschubotz  2019-03-28
=====  ============  =========  ==========

.. _90: https://github.com/gnosis/safe/issues/90

.. _Main:


#. `Main`_
#. `User Interface`_

.. sectnum::
.. contents:: Table of Contents
    :local:
    :depth: 2

Problem Definition
-------------------------------

- Users are switching to a new phone and want to continue using their old Safe.
- Users deleted the Gnosis Safe app and would like to continue using their old Safe.

Inputs
-----------

- Safe address
- Recovery phrase
- 2FA device

Outputs
------------

- Safe is recovered and user can manage the Safe from their current device.

Use Case Scenarios
-----------------------

Recover Safe - No 2FA
~~~~~~~~~~~~~~~~~

Preconditions
+++++++++++++

- Safe app is setup with a password
- Safe has enough funds for recovery transaction.

Steps
+++++

1. User starts recovery

2. Read guidelines

3. Continue

4. Input Safe address

5. Input recovery phrase

6. Skip 2FA setup

7. Review transaction

8. Submit transaction

9. Wait for the transaction to finish

Postconditions
++++++++++++++

- User ends up on the assets overview screen
- No 2FA device is connected to the Safe
- Safe is successfully recovered
- Safe can be managed from the device

Recovery Safe - With 2FA
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Inherits from the `Recover Safe - No 2FA`_

Steps
+++++

6. 1. Scan QR code of browser extension

Postconditions
++++++++++++++

- User ends up on the assets overview screen
- 2FA device is connected to the Safe
- Safe is successfully recovered
- Safe can be managed from the device


Invalid Safe address
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Inherits from the `Recover Safe - No 2FA`_

Steps
+++++

4. Input invalid Safe address

Postconditions
++++++++++++++

- User cannot continue with invalid Safe address
- User sees error


Invalid Safe address
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Inherits from the `Recover Safe - No 2FA`_

Preconditions
+++++++++++++

- Safe app is setup with a password
- Safe exists on the device

Steps
+++++

4. Input address from existing Safe

Postconditions
++++++++++++++

- User cannot continue with the same Safe address
- User sees error


Scan invalid QR code
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Inherits from the `Recover Safe - No 2FA`_

Steps
+++++

6. Scan invalid QR code

Postconditions
++++++++++++++

- User cannot continue
- User sees error


Insufficient funds
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Inherits from the `Recover Safe - No 2FA`_

Preconditions
+++++++++++++

- Safe app is setup with a password
- Safe does not have enough funds for recovery transaction.

Steps
+++++

7. See hint that there are not enough funds

8. Transfer missing funds

9. Hint disappears, review transaction

10. Submit transaction

11. Wait for the transaction to finish

.. _`User Interface`: 02_user_interface.rst
