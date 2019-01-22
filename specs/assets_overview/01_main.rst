+-------+----------------------+-----------+------------+
| issue | title                | author    | created    |
+-------+----------------------+-----------+------------+
| 71_   | Transaction overview | tschubotz | 2019-01-22 |
+-------+----------------------+-----------+------------+

.. _71: https://github.com/gnosis/safe/issues/71

Transaction overview
====================

1. `Main`_
2. `User Interface`_
3. `External Communication`_
4. Other_

.. _Main:

.. contents:: Table of Contents
    :depth: 3

1. Problem Definition
---------------------

- User needs to see an overview of past and current Safe transactions.
- User needs to see transaction details
    - Date & time
    - State (Pending, successful, failed)
    - Type (ETH transfer, ERC20 token transfer, data tx)
- User should be able to access the tx on Etherscan to get really all the info.


2. Inputs
-----------

- Existing Safe.
- Transactions of different types and in different states.


3. Outputs
------------

- Transactions and their details are displayed.


4. Use Case Scenarios
-----------------------

4.1. Happy Case
~~~~~~~~~~~~~~~

Preconditions
+++++++++++++

- Safe exists on the device.
- Transactions of different types and in different states exist.
- User is on the assets/token overview screen/tab.


Steps
+++++

1. User tabs the "Transactions" tab
2. User sees a list of all transactions.
3. User can scroll to see all available transactions.
4. User taps a transaction.
5. User sees transaction details.
6. User tap the Etherscan link, so a browser opens with transcation on
   Etherscan
7. User goes back.


Postconditions
++++++++++++++

- User ends up on the transaction details screen again.


4.2. Transcation state update on transaction list
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

inherits from `4.1. Happy Case`_

Steps
+++++

4. A transction switches it's state (e.g. is mined and now successful / failed)

Postconditions
++++++++++++++

- Transaction UI updates respective to the new state.


4.3. Transcation state update on transaction details
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

inherits from `4.1. Happy Case`_

Steps
+++++

6. A transction switches it's state (e.g. is mined and now successful / failed)

Postconditions
++++++++++++++

- Transaction details UI updates respective to the new state.

.. _`User Interface`: 02_user_interface.rst
.. _`External Communication`: 03_external_communication.rst
.. _Other: 04_other.rst
