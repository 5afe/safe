===================
Other requirements
===================

.. contents:: Table of Contents

1. Timing
-----------

* All of the screen transitions must be executed within 200ms,
  starting from the user action (button tap, for example).

  - If some action is long running, then for the duration
    of the action there should be an activity indicator
    shown or a progress bar.
  - If the progress bar or other animation needs to
    indicate its finished state, it should animate so with 400-500ms duration.

* Backend services expected response time: up to 30 seconds.

  - Relay Service

    + estimate transaction
    + submit transaction

  - Notification Service

    + create new device pair
    + delete old device pair
    + send notification

  - Ethereum Node API

    + eth_getBalance
    + eth_call
    + eth_getTransactionReceipt

* Expected processing time of submitted transaction:

  - Rinkeby network: 30 seconds
  - Mainnet network: 2 minutes
  - Note, that this time, potentially, can go up to hours.

* What to do in case the transaction processing
  time is taking more than 2 minutes?

* At any time, there might be only 1 pending
  replace browser transaction in the app.

2. Security
-------------

* User Inputs

  - The recovery phrase input must limit the text entry to 500 characters.
    The 500 number is a heuristic to limit size of potentially insecure input.
  - The phrase is split into words by whitespaces or newlines.
  - The phrase is a set of words from a language-specific word lists.
    All characters except whitespace, newline
    (characters in Unicode General Category Z*, U+000A ~ U+000D, and U+0085)
    and letter characters
    (characters in Unicode General Category L* & M*.) should be ignored)

* Network Communication

  - Application must expect wrong format or errors
    when receiving network responses.
  - The size of the response should be limited to
    appropriate length (in KB, MB or character length).
  - These situations must be handled gracefully, i.e. app should
    not crash if the JSON payload is malformed or unexpected.
  - These situations must be reported to the user and
    logged for further investigation.

* QR-code reading

  - Application must expect malformed input encoded
    in QR code and treat it appropriately.
  - Size of the QR-code encoded information must be limited to a fixed length.
  - Unexpected inputs should be reported to the user and logged.

* Recovery Phrase

  - Application must not persist the Recovery Phrase or derived keys, but
    only use it for the transaction signing.
  - Application must remove the phrase from memory as soon as possible.
  - Before removing, the program must override the memory with trash data.
  - Check that the recovery phrase in the pasteboard cannot be read
    by another app without explicit user action.
  - Recovery phrase is shown as plain text, so that user can
    visually check it.

3. Reliability
----------------

* Consequences of the software failures

  - Crashing before submitting transaction to the network

    + This should not affect the app in any way as nothing should be changed.

.. review: is it possible now?

  - Crashing after submitting transaction to the network but before
    persisting this information. The transaction executes successfully.

    + This will leave the app knowing it's connected to the old extension
      while in fact the new extension became an owner. This will
      prevent the user from making any transactions except replacing
      the extension one more time. In that case, the "replace
      browser extension" option should repair the state by
      reconnecting with new extension but not submitting
      the transaction to the blockchain.
      This conflicts with the use case `4.5. Existing Extension Scanned`_

  - Crashing during the transaction pending status.

    + Transaction status will be queried after app restart,
      in the transaction list.
      No user data should be affected.

  - Transaction execution fails in the blockchain.

    + This should not change the browser connection. The newly created
      notification pair must be removed.

* Error detection

  - The app should check the contract's state before executing the transaction.
    Particularly, the threshold and owners should be checked to verify
    that the replacement transaction should be successful.

4. Memory and Storage
-----------------------

* For iOS, the maximum memory size depends on the device and iOS version.
  In general, it is best to use as low memory as possible.
  Some empirical testing data about memory limits is on stackoverflow_
* For iOS, the maximum storage space is limited by the device capacity.
  That being said, the app should try to use as low storage as possible
  to reduce the chance of being deleted from the phone by users for using
  too much space.

5. Maintainability
---------------------

* The software should be easy to adopt changes in the external communications
* The software should be easy to adopt changes in the User Interface.
  The software should be easy to adopt changes in the sequence of the screens.
* For iOS, the software should be easy to move major parts to
  other operating systems such as watchOS, macOS, iPad and tvOS.

6. Definition of Success
---------------------------

* For the team, success is

  - when the feature is deployed in Production
    and achieved 99,9% of crash-free users with regard to the functionality
    specified in this specification.
  - when team members did not quit or burned out.
  - when the software is maintainable and extensible.
  - when the appropriate automated test suites are in place and running,
    including unit tests, integration tests, and user interface tests.

* For the Product Owner, the success is:

  - The feature is deployed in production on all platforms.
  - The feature is developed on time.
  - Users are able to go through all use case scenarios without crashes.
  - Users understand how to change their browser extension ←
    This aims at the usability of the feature.
  - The feature works similarly on Android and iOS
    (i.e. it should be the same except for platform-specific
    differences and deliberate design decisions.)

* For the end user, the success is:

  - when after update to new app version, the app is still working.
  - when the 'replace browser extension' works as expected.
  - when the software is easy to use.

Failure to achieve the success points above will qualify as failure.

7. Possible Changes to the Specification
------------------------------------------

* User Interface designs are very likely to change in the next 6 months.

  - New language translations are going to be added, and that might affect
    layout of text labels.

  - For iOS, the "Dynamic Text" feature might be implemented in the following
    year. That will affect the layout of text labels.

* In case the recovery option will change, then the recovery phrase steps
  will change. Likely to change in the next year.

* Backend service API can change

  - Infura service might be replaced by our backend service. Very likely
    in the following 2 months

  - Notification service might change, very likely in the following year.

  - Transaction list might be changed from local storage to new service.

* New authenticators support might be added, and that might change
  the QR-code based communication. Likely in the following 2 years.

Revision History
----------------

==========  =======================================================
Date        Description
==========  =======================================================
2019-01-07  New document with other requirements for the "Replace
            Browser Extension" feature.
==========  =======================================================

.. _`4.5. Existing Extension Scanned`: 01_main.rst
.. _stackoverflow: https://stackoverflow.com/questions/5887248/ios-app-maximum-memory-budget
