==========================================================
App settings
==========================================================

=====  ============  =========  ==========
epic      title       author     created
=====  ============  =========  ==========
`82`_  App settings  tschubotz  2019-01-18
=====  ============  =========  ==========

.. _82: https://github.com/gnosis/safe/issues/82

.. _Main:


#. `Main`_
#. `User Interface`_

.. sectnum::
.. contents:: Table of Contents
    :local:
    :depth: 2

Problem Definition
---------------------

- There are some app features that we need to provide the user access to.
    - Access Terms of Use
    - Access Privacy Policy
    - Change password
    - Enable/disable biometric authentication
    - Option to Give feedback (Send us an email)
    - Option to rate the app in the store.
    - View app version (For bug reporting)
    - View used open source licenses


Inputs
-----------

 - Depending on the use case: Password and biometrics information, Terms, Privacy Policy


Outputs
----------

Outputs depend on the selected option.

- Open webpage (Terms & Privacy Policy)
- Start change password flow
- Biometric auth has been enabled / disabled
- Open up email program (Give feedback)
- Open store for rating / writing review (Rate app)
- App version is displayed
- View used open source licenses


Use Case Scenarios
-----------------------

App version
~~~~~~~~~~~~~~~~

Preconditions
+++++++++++++

- App is set up with a password

Steps
+++++

1. Open app settings

Postconditions
++++++++++++++

- User can see the currently installed app version.

View Terms of Use
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Inherits from `App version`_

Steps
+++++

2. Select Terms of Use

Postconditions
++++++++++++++

- Browser opens with https://safe.gnosis.io/terms


View Privacy Policy
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Inherits from `View Terms of Use`_

Steps
+++++

2. Select Privacy Policy

Postconditions
++++++++++++++

- Browser opens with https://safe.gnosis.io/privacy


Start change password flow
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Inherits from `App version`_

Steps
+++++

2. Open "Change password"

Postconditions
++++++++++++++

- "`Change password`_" flow is started

.. _`Change password`: https://github.com/gnosis/safe/issues/74


Enable biometric auth
~~~~~~~~~~~~~~~~~~~~~~~

- *iOS: "Touch ID" or "Face ID"*
- *Android: "Fingerprint" or "Face ID"*

Preconditions
+++++++++++++

- App is set up with a password
- Biometric auth is disabled

Steps
+++++

1. Open app settings
2. Enable biometric auth
3. User has to confirm with biometric auth

Postconditions
++++++++++++++

- Biometric auth is enabled.
- User is still on settings page.


Disable biometric auth
~~~~~~~~~~~~~~~~~~~~~~~~

- *iOS: "Touch ID" or "Face ID"*
- *Android: "Fingerprint" or "Face ID"*

Preconditions
+++++++++++++

- App is set up with a password
- Biometric auth is enabled

Steps
+++++

1. Open app settings
2. Disable biometric auth

Postconditions
++++++++++++++

- Biometric auth is disabled.
- User is still on settings page.


Rate app
~~~~~~~~~~~~~

Inherits from `App version`_

Steps
+++++

2. Select "Rate app"

Postconditions
++++++++++++++

- Store is opened on a screen where user can rate and review the Gnosis Safe.


Give feedback
~~~~~~~~~~~~~~~

Inherits from `View Terms of Use`_

Steps
+++++

2. Select "Give feedback"
3. Email program opens with a prefilled email with the following text:

 App version: <iOS/Android> - <app_version>

 Safe addresses:
     0xFirstSafeAddress

     0xSecondSafeAddress

 Feedback:

4. Enter text
5. Send email


View open source licenses
~~~~~~~~~~~~~~~~~~~~~~~~~~

Inherits from `View Terms of Use`_

Steps
+++++

2. Select "Licenses"
3. Browser opens with licenses webpage.
4. User goes back

Licenses webpage:

- Android: https://safe.gnosis.io/licenses#android
- iOS: https://safe.gnosis.io/licenses#ios

.. _`User Interface`: 02_user_interface.rst
