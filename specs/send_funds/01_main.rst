==========================================================
Send funds
==========================================================

=====  ==========  =========  ==========
epic     title      author     created
=====  ==========  =========  ==========
`66`_  Send funds  tschubotz  2019-03-27
=====  ==========  =========  ==========

.. _66: https://github.com/gnosis/safe/issues/66

.. _Main:


#. `Main`_
#. `User Interface`_

.. sectnum::
.. contents:: Table of Contents
    :local:
    :depth: 2


Problem Definition
-------------------------------

- Users have funds in their Safes that they would like to transfer.
- Funds are ETH and other ERC20 tokens.

Inputs
-----------

- Fund to transfer.
- Amount
- Transaction fee
- Destination address
- 2FA confirmation

Outputs
------------

- Transfer transaction is submitted to the blockchain.

Use Case Scenarios
-----------------------

Happy Case - No 2FA
~~~~~~~~~~~~~~~~~~~

.. _happy_case_preconditions:

Preconditions
+++++++++++++

- Safe exists on the device
- No 2FA device is configured.
- User is on the assets overview screen
- User has funds.

.. _happy_case_steps:

Steps
+++++

1. Select funds to transfer.

2. Enter valid recipient address.

3. Enter amount which does not exceed the funds stored.

4. Network fees are loaded

5. Continue

6. Review transaction details

7. Submit transaction

8. Enter password or use biometric authentication, if configured.

9. See confirmation screen.

10. Continue

.. _happy_case_step_3

Postconditions
++++++++++++++

.. _happy_case_postconditions:

- Transaction has been submitted to the blockchain
- User ends up on the transaction list
- User sees the pending transaction on top of the transaction list.


Happy case - With 2FA
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Inherits from the `Happy Case - No 2FA`_

Preconditions
+++++++++++++

- Safe exists on the device
- 2FA device is configured.
- User is on the assets overview screen
- User has funds.

Steps
++++++

6. 1. Review transaction details

   2. Confirm with 2FA device

   3. Wait to receive confirmation



Invalid recipient address
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Inherits from the `Happy Case - No 2FA`_

Steps
++++++

2. Enter invalid recipient address

Postconditions
++++++++++++++

- User sees error message.
- User cannot advance to the next step without entering a valid address.


Invalid amount
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Inherits from the `Happy Case - No 2FA`_

Steps
++++++

3. Enter amount that exceed the funds stored

Postconditions
++++++++++++++

- User sees error message.
- User cannot advance to the next step without entering a lower value that does   not exceed the funds


2FA rejects
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Inherits from the `Happy Case - With 2FA`_

Steps
++++++

6. 1. Review transaction details

   2. Reject with 2FA device

Postconditions
++++++++++++++

- User sees error message.
- User cannot advance to the next step without getting 2FA confirmation.
- User can resend the confirmation request to the 2FA device.

.. _`User Interface`: 02_user_interface.rst
.. _`About Use Case Scenarios`: ../common/about_use_case_scenarios.rst
