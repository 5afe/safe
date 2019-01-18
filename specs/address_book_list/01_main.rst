+--------+------------------+
| issue  | title            |
+--------+------------------+
| 81_    | Address Book List|
+--------+------------------+

.. sectnum::

.. _81: https://github.com/gnosis/safe/issues/81


Address Book List
=================

Problem Definition
-------------------------------

- User can recognize names better than full addresses
- User wants to associate addresses to names
- User can see the address book entries and their details
- The address book is not synced (ie.: it is part of the local storage only)

Inputs
-----------

- Address book entries stored locally (local database) 

Outputs
------------

- Formatted list to be displayed to the user. Each entry has:
    - Identicon
    - Name
    - Ethereum address

Use Case Scenarios
-----------------------

Happy Case
~~~~~~~~~~~~~~~~~

.. _happy_case_preconditions:

Preconditions
+++++++++++++

- User went through application setup
- Application is unlocked

.. _happy_case_steps:

Steps
+++++

1. Open side menu

2. Select "Address Book"

.. _happy_case_postconditions:

Postconditions
++++++++++++++

- Address book entries are displayed


Database error
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Inherits from the `Happy Case`_

.. Inherits from
    means that this scenario takes all the preconditions,
    steps and postconditions from another use case and possibly extends
    or overrides them with new values.

Postconditions
++++++++++++++
- Error loading entries from database. An error message is therefore displayed.


.. _`Address Book List`: 01_address_book_list.rst
.. _`Add Address`: 02_add_address.rst
