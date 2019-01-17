========  ===========================  ================  ==========
epic      title                        author            created
========  ===========================  ================  ==========
`60`_     Replace Browser Extension    DmitryBespalov    2019-01-04
========  ===========================  ================  ==========

.. _60: gnosis/safe#60

===============
User interface
===============

.. contents:: Table of Contents

1. Intro
------------

Intro screen, loaded with all information and ready to start.

.. raw:: html

   <img src="screens/ios/RBE-Intro.png" width="320px"/>


1.1. Intro - Insufficient Funds
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Intro screen, when there are insufficient funds
and screen waits for balance updates.

.. raw:: html

   <img src="screens/ios/RBE-Intro-FundsError.png" width="320px"/>


1.2. Intro - Loading
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Intro screen when information is still loading

.. raw:: html

   <img src="screens/ios/RBE-1_2_RBE_Intro_Loading.png" width="320px"/>


1.3. Intro - Error Alert
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Intro screen when "Start" action resulted in alert

.. raw:: html

   <img src="screens/ios/RBE-1_3_RBE_Error_Alert.png" width="320px"/>


1.4. Intro - Start Action Loading
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Intro screen when "Start" action taking long time.

.. raw:: html

   <img src="screens/ios/RBE-1_4_RBE_Intro_Start_Action_Loading.png" width="320px"/>



1.5. Intro - Inline Error
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Intro screen showing error when initial loading action failed.

.. raw:: html

   <img src="screens/ios/RBE-1_5_Intro_Inline_Error.png" width="320px"/>


2. Scan QR Code
---------------

Scan QR Code screen ready to start scanning

.. raw:: html

   <img src="screens/ios/RBE-Scan.png" width="320px"/>


2.1. Scan QR Code - Loading
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Loading under slow operating conditions - after scanning a valid QR code

.. raw:: html

   <img src="screens/ios/RBE-3_1_Scan_QR_Code_Loading.png" width="320px"/>


3. Camera screen
---------------------------

Camera screen for scanning a QR code.

.. raw:: html

   <img src="screens/ios/RBE-4_Camera_Screen.png" width="320px"/>


3.1. Camera Screen - Error Alert
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Error shown after scanning invalid QR-code

.. raw:: html

   <img src="screens/ios/RBE-4_1_Camera_Screen_Error_Alert.png" width="320px"/>


4. Recovery Phrase
------------------

Recovery Phrase input screen with inline error related to the recovery phrase

.. raw:: html

   <img src="screens/ios/RBE-Phrase.png" width="320px"/>


4.1. Recovery Phrase - Loading
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Recovery Phrase screen when "Next" action takes long time.

.. raw:: html

   <img src="screens/ios/RBE-2_1_Recovery_Phrase_Loading.png" width="320px"/>


5. Review
-----------------------

Review transaction screen.

.. raw:: html

   <img src="screens/ios/RBE-Review.png" width="320px"/>


5.1 Review - Loading
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Review screen after selecting "Submit" action, showing the loading
indicator for the long-running operation.

.. raw:: html

   <img src="screens/ios/RBE-8_1_Review_Loading.png" width="320px"/>


5.2. Review - Error Alert
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Review screen showing error after selecting "Submit" action.

.. raw:: html

   <img src="screens/ios/RBE-8_2_Review_Error_Alert.png" width="320px"/>


6. Transaction List
---------------------------------

Transaction list showing the "Replace Browser Extension" item in 3 statuses:

* Pending
* Success
* Failed

.. raw:: html

   <img src="screens/ios/RBE-List.png" width="320px"/>


6.1. Pending Transaction
~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. raw:: html

   <img src="screens/ios/RBE-6_Transaction_List_Pending.jpg" width="320px"/>


6.2. Successful Transaction
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. raw:: html

   <img src="screens/ios/RBE-6_Transaction_List_Success.jpg" width="320px"/>


6.3. Failed Transaction
~~~~~~~~~~~~~~~~~~~~~~~~~~

.. raw:: html

   <img src="screens/ios/RBE-6_Transaction_List_Failed.jpg" width="320px"/>


.. _details:

7. Transaction Details
------------------------------------

Transaction Details screen showing "Replace Browser Extension",
possibly in 3 statuses.

.. raw:: html

   <img src="screens/ios/RBE-Details.png" width="320px"/>


7.1. Pending Transaction
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. raw:: html

   <img src="screens/ios/RBE-7_Transaction_Details_Pending.png" width="320px"/>


7.2. Successful Transaction
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. raw:: html

   <img src="screens/ios/RBE-7_Transaction_Details_Success.png" width="320px"/>


7.3. Failed Transaction
~~~~~~~~~~~~~~~~~~~~~~~~

.. raw:: html

   <img src="screens/ios/RBE-7_Transaction_Details_Failed.png" width="320px"/>

