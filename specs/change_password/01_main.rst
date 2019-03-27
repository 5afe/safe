=====  ===============  =========  ==========
epic        title        author     created
=====  ===============  =========  ==========
`74`_  Change password  tschubotz  2019-01-17
=====  ===============  =========  ==========

.. _74: https://github.com/gnosis/safe/issues/74

.. _Main:


#. `Main`_
#. `User Interface`_

.. sectnum::
.. contents:: Table of Contents
    :local:
    :depth: 2

Problem Definition
---------------------

* User wants to change the current app password.
* Current password could be compromised and hence needs to be changed.

Inputs
-----------

.. _`password requirements`: ../common/password_requirements.rst

- Current password.
- New password that matches the `password requirements`_
- Repeat new password

  - Needs to match

Outputs
------------

- Changed password
- Error messages

  - Wrong current password entered
  - New password does not meet requirements
  - Repeated new password does not match.


Use Case Scenarios
-----------------------

Happy Case
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


Happy Case with biometric authentication
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

inherits from `Happy Case`_

Preconditions
+++++++++++++

- App is setup with a password
- App is setup with biometric authentication
- User knows the password.

Postconditions
++++++++++++++

- User is on the settings screen.
- App password is changed.
- User can unlock the app with the new password.
- User can unlock the app with the biometric authentication.
- User cannot unlock the app with another password.
- User can confirm transactions with the new password.
- User can confirm transactions with biometric authentication.
- User cannot confirm transactions with another password.


Wrong password
~~~~~~~~~~~~~~~~~~~

inherits from `Happy Case`_

Steps
+++++

4. User sees error that password is not correct.
5. [No further steps]

Postconditions
++++++++++++++

- User is still on the screen to enter the current password.
- App password is not changed.
- User can still unlock the app with the old password.
- User can still confirm transactions with the old password.


Password does not meet requirements
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

inherits from `Happy Case`_

4. User enters invalid new password
5. User sees error that password does not meet password requirements.

Postconditions
++++++++++++++

- User is still on the screen to enter a new password.
- App password is not changed.
- User can still unlock the app with the old password.
- User can still confirm transactions with the old password.


Password does not match
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

inherits from `Happy Case`_

5. User does not repeat the new password correct.
6. User sees error that the new password does not match.

Postconditions
++++++++++++++

- User is still on the screen to repeat the new password.
- App password is not changed.
- User can still unlock the app with the old password.
- User can still confirm transactions with the old password.


.. _`User Interface`: 02_user_interface.rst
