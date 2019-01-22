=========================
Technical Requirements
=========================

.. sectnum::
.. contents:: Table of Contents
    :local:
    :depth: 2

Timing
-----------

* All of the screen transitions must be executed within standard platform timing limits,
  starting from the user action (button tap, for example).

  - If some action is long running, then for the duration
    of the action there should be an activity indicator
    shown or a progress bar.
  - If the progress bar or other animation needs to
    indicate its finished state, it should animate visibly to the user.

Security
-------------

* User Inputs

  - The size of any textual input must be limited to a specific number of characters.
  - The accepted character set must be defined.

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

Memory and Storage
-----------------------

* For iOS, the maximum memory size depends on the device and iOS version.
  In general, it is best to use as low memory as possible.
  Some empirical testing data about memory limits is on stackoverflow_
* For iOS, the maximum storage space is limited by the device capacity.
  That being said, the app should try to use as low storage as possible
  to reduce the chance of being deleted from the phone by users for using
  too much space.

Maintainability
---------------------

* The software should be easy to adopt changes in the external communications
* The software should be easy to adopt changes in the User Interface.
  The software should be easy to adopt changes in the sequence of the screens.
* For iOS, the software should be easy to move major parts to
  other operating systems such as watchOS, macOS, iPad and tvOS.

Definition of Success
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

.. _stackoverflow: https://stackoverflow.com/questions/5887248/ios-app-maximum-memory-budget
