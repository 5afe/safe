==========================================================
Address book
==========================================================

=====  ============  ===================  ==========
epic      title            author          created
=====  ============  ===================  ==========
`81`_  Address book  fmrsabino/tschubotz  2019-02-27
=====  ============  ===================  ==========

.. _81: https://github.com/gnosis/safe/issues/81

.. _Main:


#. `Main`_
#. `User Interface`_

.. sectnum::
.. contents:: Table of Contents
    :local:
    :depth: 2

Problem Definition
-------------------------------

- User wants to reduce the probability of sending to a wrong address
- User can recognize names better than full addresses
- User wants an easy way to reuse often used addresses
- User wants to associate addresses to names

Inputs
-----------

- Ethereum addresses
- Address book entry names

Outputs
------------

- Address book entries
    - Identicon
    - Name
      - Maximum 200 characters (Could be any length, just to limit input)
    - Ethereum address

Use Case Scenarios
-----------------------

Happy Case
~~~~~~~~~~~~~~~~~

.. _happy_case_preconditions:

Preconditions
+++++++++++++

- User went through Safe setup
- App is unlocked
- At least 1 address book entry exists

.. _happy_case_steps:

Steps
+++++

1. User opens settings
2. User selects "Address Book". 
3. User see all address book entries sorted by their name, ascending.
4. User selects an address book entry

.. _happy_case_postconditions:

Postconditions
++++++++++++++

- Address book entry is displayed
  - Name
  - Identicon
  - QR code
  - Address


Share entry address
~~~~~~~~~~~~~~~~~~~~

Inherits from the `Happy Case`_

Steps
+++++

5. User selects share button

Postconditions
++++++++++++++

- Share sheet opens
- User can share the address book entry address with any third party service


Add entry 
~~~~~~~~~~~~~~~~~~~~

Inherits from the `Happy Case`_

Steps
+++++

1. User opens settings
2. User selects "Address Book". 
3. User selects "+"
4. User enters a valid name
5. User enters a valid address
6. User selects "Done"

Postconditions
++++++++++++++

- Entry is saved
- User is on the details view of that new entry


Add entry - Error
~~~~~~~~~~~~~~~~~~~~

Inherits from the `Add entry `_

Steps
+++++

4. User enters an invalid name
5. User enters an invalid address

Postconditions
++++++++++++++

- "Done" is disabled
- User sees error about invalid name
- User sees error about invalid address


Edit entry
~~~~~~~~~~~~~~~~~~~~

Inherits from the `Happy Case`_

Steps
+++++

5. User selects "Edit"
6. User changes name
7. User changes address
8. User selects "Done"

Postconditions
++++++++++++++

- User is on detail view again
- Entry is updated


Delete entry
~~~~~~~~~~~~~~~~~~~~

Inherits from the `Happy Case`_

Steps
+++++

5. User selects "Edit"
6. User selects "Delete entry"
7. User confirms

Postconditions
++++++++++++++

- Entry is deleted
- User is on address book list


Search for entries
~~~~~~~~~~~~~~~~~~~~

Preconditions
+++++++++++++

- User is on address book list
- At least 1 address book entry exists

Steps
+++++

1. User enters text into search bar

Postconditions
++++++++++++++

- Search results are update on each change of the search term
- Entries who's name or address contain the search term are displayed.


Send to address book entry
~~~~~~~~~~~~~~~~~~~~~~~~~~~

Inherits from the `Happy Case`_

Steps
+++++

1. Select funds to send
2. Tap recipient field
3. Action sheet opens
4. Tap "Address book" 
5. Select entry

Postconditions
++++++++++++++

- User is back on the Send funds screen
- Address book entry is filled in.
- User can finish the send funds process regularly


Add entry from transaction details
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Preconditions
+++++++++++++

- App is unlocked
- At least 1 transaction exists
- User is on transaction list

Steps
+++++

1. Select transaction
2. User taps 3 dots
3. User taps "Add to Address book"
4. "New entry" screens opens
5. User fills in details
6. User select "Done"

Postconditions
++++++++++++++

- User is back on transaction details
- User now sees the address book name on the transaction details in addition to the shortened address.


Send again from transaction details
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Preconditions
+++++++++++++

- App is unlocked
- At least 1 transaction exists
- User is on transaction list

Steps
+++++

1. Select transaction
2. User taps 3 dots
3. User taps "Send ETH again" (Should be the respective token symbol)

Postconditions
++++++++++++++

- Send funds flow is started
- Address is preselected.
- User can go through Send funds flows regularly.

.. _`User Interface`: 02_user_interface.rst