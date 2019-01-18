+-------+--------------+-----------+------------+
| issue | title        | author    | created    |
+-------+--------------+-----------+------------+
| 82_   | App settings | tschubotz | 2019-01-18 |
+-------+--------------+-----------+------------+

.. _82: https://github.com/gnosis/safe/issues/82


App settings
============

1. `Main`_
2. `User Interface`_

.. _Main:

.. contents:: Table of Contents
    :depth: 3


1. Problem Definition
---------------------

- There are some app features that we need to provide the user access to.
    - Access Terms of Use
    - Access Proviacy Policy
    - Change password
    - Enable/disable fingerprint
    - Option to contact us (Send us an email)
    - Option to rate the app in the store.
    - View app version (For bug reporting)


2. Inputs
-----------

 - User manages app settings.


3. Outputs
----------

Outputs depend on the selected option.
- Open webpage (Terms & privacy policy)
- Start change password flow
- Fingerprint has been enabled / disabled
- Open up email program (Contact us)
- Open store for rating / writing review (Rate app)
- App version is displayed


4. Use Case Scenarios
-----------------------

4.1. App version
~~~~~~~~~~~~~~~~

Preconditions
+++++++++++++

- App is set up with a password

Steps
+++++

1. Open app settings

Postconditions
++++++++++++++

- User can see app version in way so we know which version they are using.


4.2. View Terms of Use
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Inherits from `4.1. App version`_

Steps
+++++

2. Open Terms of Use
3. User goes back

Postconditions
++++++++++++++

- User is back on the settings page.


4.3. View Privacy policy
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Inherits from `4.2. View Terms of Use`_

Steps
+++++

2. Open Privacy Policy
3. User goes back


4.4. Start change password flow
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Inherits from `4.1. App version`_

Steps
+++++

2. Open "Change password"

Postconditions
++++++++++++++

- "Change password" flow is started


4.5. Enable finterprint
~~~~~~~~~~~~~~~~~~~~~~~

Preconditions
+++++++++++++

- App is set up with a password
- Finterprint is disabled

Steps
+++++

1. Open app settings
2. Disable finterprint

Postconditions
++++++++++++++

- Fingerprint is disabled.
- User is still on settings page.


4.6. Disable finterprint
~~~~~~~~~~~~~~~~~~~~~~~~

Preconditions
+++++++++++++

- App is set up with a password
- Finterprint is enabled

Steps
+++++

1. Open app settings
2. Enable finterprint
3. User has to confirm with fingerprint

Postconditions
++++++++++++++

- Fingerprint is enabled.
- User is still on settings page.


4.7. Rate app
~~~~~~~~~~~~~

Inherits from `4.1. App version`_

Steps
+++++

2. Open "Rate app"

Postconditions
++++++++++++++

- Store is opened on a screen where user can rate and review the Gnosis Safe.


4.8. Contact us
~~~~~~~~~~~~~~~

Inherits from `4.2. View Terms of Use`_

Steps
+++++

2. Open "Contact us"
3. Email program opens with a prefilled email with the following text:

 App version: <iOS/Android> - <app_version>

 Safe addresses:
     0xFirstSafeAddress
     0xSecondSafeAddress

4. Send email

.. _`User Interface`: 02_user_interface.rst
.. _`External Communication`: 03_external_communication.rst
.. _Other: 04_other.rst
