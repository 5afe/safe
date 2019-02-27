==========================================================
Create password
==========================================================

=====  ===============  =========  ==========
epic        title        author     created
=====  ===============  =========  ==========
`65`_  Create password  tschubotz  2019-01-22
=====  ===============  =========  ==========

.. _65: https://github.com/gnosis/safe/issues/65

.. _Main:


#. `Main`_
#. `User Interface`_

.. sectnum::
.. contents:: Table of Contents
    :local:
    :depth: 2

Problem Definition
---------------------

- We need the user to set a password for the app so:
    - Nobody can open the app or confirm transactions without the password.
    - We can encrypt the private key of the device.
- Most devices have a fingerprint sensor. Users should be able to use it
  additionally to the password.
- We need the user to agree to the Terms and Privacy Policy.

Inputs
-----------

- New password
    - Minimum 8 characters (>=8)
    - At least 1 number
    - At least 1 letter
    - No more than 2 identical characters in a row
      (e.g. 111 is not allowed, 11 is fine)
    - Maximum length?
- Repeat new password
    - Needs to match
- Biometric authentication info of the user
- Terms of Use & Privacy Policy.

Outputs
------------

- User agreed to Terms of Use and Privacy Policy.
- Password is set.
- Biometric authentication is potentially enabled.
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

- App is installed and started on start screen.

Steps
+++++

1. User taps "Create password"
2. User taps "Privacy Policy" so Privacy Policy opens
3. User goes back so they are back in the Gnosis Safe app.
4. User taps "Terms of Use" so Terms of Use opens
5. User goes back so they are back in the Gnosis Safe app.
6. User taps "Agree"
7. User enters valid password.
8. User proceeds to next screen.
9. User repeats the new password.
10. User confirms with biometric information.
11. User proceeds.

Postconditions
++++++++++++++

- User is on the home screen and can create or restore a Safe.
- App password is set
- User can unlock the app with the new password.
- User cannot unlock the app with another password.
- User can unlock the app with the fingerprint.


Happy Case no fingerprint
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

inherits from `Happy Case`_

Steps
+++++

10. User skips fingerprint setup

Postconditions
++++++++++++++

- User is on the home screen and can create or restore a Safe.
- App password is set
- User can unlock the app with the new password.
- User cannot unlock the app with another password.
- User cannot unlock the app with the fingerprint.


Password does not meet requirements
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

inherits from `Happy Case`_

Steps
+++++

7. User enters invalid new password
8. User sees error that password does not meet password requirements.

Postconditions
++++++++++++++

- User is still on the screen to enter a new password.
- App password is not set.
- If user would "kill" the app, then they would have to start over again
  with the very start screen.
- User cannot continue with invalid password


Password does not match
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

inherits from `Happy Case`_

Steps
+++++

9. User does not repeat the new password correctly.
10. User sees error that password does not match.

Postconditions
++++++++++++++

- User is still on the screen to repeat the new password.
- App password is not set.
- If user would "kill" the app, then they would have to start over again
  with the very start screen.
- User cannot continue with not matching password.


.. _`User Interface`: 02_user_interface.rst

