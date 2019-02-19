=====  ===============  =========  ==========
epic        title        author     created
=====  ===============  =========  ==========
`74`_  Change password  tschubotz  2019-01-17
=====  ===============  =========  ==========

.. _74: https://github.com/gnosis/safe/issues/74

.. _Main:


#. `Main`_
#. `User Interface`_
#. `Technical Details`_

.. sectnum::
.. contents:: Table of Contents
    :local:
    :depth: 2

1. Problem Definition
---------------------

* User wants to change the current app password.
* Current password could be compromised and hence needs to be changed.

2. Inputs
-----------

- Current password.
- New password
    - Minimum 8 characters (>=8)
    - At least 1 number
    - At least 1 letter
    - No more than 2 identical characters in a row
      (e.g. 111 is not allowed, 11 is fine)
    - Maximum lenght?
- Repeat new password
    - Needs to match

3. Outputs
------------

- Changed password
- Error messages
  - Wrong current password entered
  - New password does not meet requirements
  - Repeated new password does not match.


4. Use Case Scenarios
-----------------------

4.1. Happy Case
~~~~~~~~~~~~~~~

Preconditions
+++++++++++++

- App is setup with a password
- User has correct password.

Steps
+++++

1. Open app Settings
2. Open "Change password"
3. Enter the current password
4. Enter valid new password
5. Repeat new password
6. Save

Postconditions
++++++++++++++

- User is on the settings screen.
- App password is changed.
- User can unlock the app with the new password.
- User cannot unlock the app with another password.
- User can confirm transactions with the new password.
- User cannot confirm transactions with another password.


4.2. Happy Case with fingerprint
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

inherits from `4.1. Happy Case`_

Preconditions
+++++++++++++

- App is setup with a password
- App is setup with fingerprint
- User knows the password.

Postconditions
++++++++++++++

- User is on the settings screen.
- App password is changed.
- User can unlock the app with the new password.
- User can unlock the app with the fingerprint.
- User cannot unlock the app with another password.
- User can confirm transactions with the new password.
- User can confirm transactions with the fingerprint.
- User cannot confirm transactions with another password.


4.3. Wrong password
~~~~~~~~~~~~~~~~~~~

inherits from `4.1. Happy Case`_

Steps
+++++

4. User sees error that password is not correct.

Postconditions
++++++++++++++

- User is on still on the screen to enter the current password.
- App password is not changed.
- User can still unlock the app with the old password.
- User can still confirm transactions the old password.


4.4. Password does not meet requirements
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

inherits from `4.1. Happy Case`_

4. User enters invalid new password
5. User sees error that password does not meet password requirements.

Postconditions
++++++++++++++

- User is on still on the screen to enter a new password.
- App password is not changed.
- User can still unlock the app with the old password.
- User can still confirm transactions the old password.


4.5. Password does not match
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

inherits from `4.1. Happy Case`_

5. User does not repeat the new password correct.
6. User sees error that password does not match.

Postconditions
++++++++++++++

- User is on still on the screen to repeat the new password.
- App password is not changed.
- User can still unlock the app with the old password.
- User can still confirm transactions the old password.


.. _`User Interface`: 02_user_interface.rst
.. _`Technical Details`: 03_technical_details.rst
