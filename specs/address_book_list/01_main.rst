+--------+------------------+
| issue  | title            |
+--------+------------------+
| 81_    | Address Book List|
+--------+------------------+

.. sectnum::

.. _81: https://github.com/gnosis/safe/issues/81


Address Book List
=================

.. contents:: Table of Contents
    :local:
    :depth: 2

Problem Definition
-------------------------------

- User can recognize names better than full addresses
- User wants to associate addresses to names
- User can see the address book entries and their details
- User can search the address book entries
- The address book is not synced (ie.: it is part of the local storage only)

Inputs
-----------

- Address book entries stored locally (local database)
- Search with name or Ethereum address

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

Detailed Entry View
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Inherits from the `Happy Case`_

.. Inherits from
    means that this scenario takes all the preconditions,
    steps and postconditions from another use case and possibly extends
    or overrides them with new values.

3. Selecting an item from the list opens a detailed view of that specific entry.

Postconditions
++++++++++++++
- User is in the detailed view of the clicked entry.

More details defined in the "Address Book Details Spec"

Add Entry
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Inherits from the `Happy Case`_

.. Inherits from
    means that this scenario takes all the preconditions,
    steps and postconditions from another use case and possibly extends
    or overrides them with new values.

3. User clicks on the button to add a new entry

Postconditions
++++++++++++++
- User is in the view to enter a new entry

More details defined in the "Add Address Book Entry Spec"

Search Entry
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Inherits from the `Happy Case`_

.. Inherits from
    means that this scenario takes all the preconditions,
    steps and postconditions from another use case and possibly extends
    or overrides them with new values.

3. User clicks on the button to search all the entries
4. User types the address or name for the entry he/she is looking for

Postconditions
++++++++++++++
- List is updated with only the entries that match the search criteria.

More details defined in the "Address Book Search Spec"


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
