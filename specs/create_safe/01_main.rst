==========================================================
Create Safe
==========================================================

=====  ===========  ========================  ==========
epic      title              author            created
=====  ===========  ========================  ==========
`67`_  Create Safe  DmitryBespalov,tschubotz  2019-01-18
=====  ===========  ========================  ==========

.. 67: https://github.com/gnosis/safe/issues/67

.. _Main:


#. `Main`_
#. `User Interface`_
#. `Technical Details`_

.. sectnum::
.. contents:: Table of Contents
    :local:
    :depth: 2

Problem Definition
-------------------------------

A user would like to create a Safe from scratch that gets deployed on the blockchain and which is ready to use afterwards.

Inputs
-----------

- 2FA device

Outputs
------------

- Deployed Safe contract on the blockchain.
- Recovery phrase
- Safe is ready to use from inside the Safe app

Use Case Scenarios
-----------------------

Happy case - no browser extension
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. _happy_case_preconditions:

Preconditions
+++++++++++++

- Password setup complete.
- App is unlocked.
- User can transfer enough funds to the to-be-created Safe to cover for network fees.
- Internet connection.
- Gnosis backend services are up and running.

.. _happy_case_steps:

Steps
+++++

1. Select "Create Safe" action. Guidelines are shown. 

2. Select "Next" action.

3. Select "Skip and setup later" to skip browser extension setup.
   The recovery phrase guidelines are shown.

4. Select "Next". Recovery phrase is shown.

5. Note the recovery phrase. Proceed to the next step.

6. Confirm the recovery phrase. Submit your confirmation.
   Confirmation is done by providing missing words from the phrase.

7. Send required minimum transfer to the Safe address from an external account.
   
8. App detects new transfer on the Safe account.

9. Wait for the safe to be created.

10. Main screen opens.

.. _happy_case_postconditions:

Postconditions
++++++++++++++

- New Safe have been created on the blockchain.
- Safe balance is what remains of the transferred funds after deducting fee for Safe creation.
- Browser extension is not connected.

Happy case - with browser extension
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Inherits from the `Happy case - no browser extension`_

Steps
+++++

.. step number overrides the step with the same number in the parent (inherited from) scenario.

3. 1. Select "Scan" action. The camera screen opens.

   2. Point the camera to the extension's QR code.
      The message displayed that the extension connected successfully.

   3. Wait until the camera closed and the app proceeds to the next step.

Postconditions
++++++++++++++

- New Safe have been created on the blockchain.
- Safe balance is what remains of the transferred funds after deducting fee for Safe creation.
- Browser extension is connected.


Cancellation
~~~~~~~~~~~~~~

Inherits from the `Happy case - no browser extension`_

Steps
+++++

7. Select "Cancel". Confirmation dialog appears.

8. Confirm the cancellation.

Postconditions
++++++++++++++++

- Safe is not created in the blockchain.
- App goes back to where it started before entering the "Create safe" flow.

Wrong Recovery Phrase Confirmation
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Inherits from the `Happy case - no browser extension`_

Steps
+++++

6. Wrong order of words is selected

7. User selects "Try again". Screen to write down recovery phrase is shown.

8. User select "I have a copy"

9. User enter correct order of words.

Postconditions
++++++++++++++++

- User can continue the creation flow.

Insufficient funds
~~~~~~~~~~~~~~~~~~~~~~~~~~~

Inherits from the `Happy case - no browser extension`_

Steps
+++++

7. Send not enough funds to the Safe address
   
8. App detects new transfer on the Safe account.

Postconditions
++++++++++++++++

- User sees that insufficient funds have been transferred.
- User sees how much funds are missing.

Monitor creation via Etherscan
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Inherits from the `Happy case - no browser extension`_

Steps
+++++

9. User selects "Follow progress on Etherscan"

Postconditions
++++++++++++++++

- Browser is opened with details on the creation transaction.

.. _`User Interface`: 02_user_interface.rst
