=======  ==================  ======  ==========
 epic          title         author   created
=======  ==================  ======  ==========
`EPIC`_  SPECIFICATION_NAME  AUTHOR  CREATED_AT
=======  ==================  ======  ==========

.. _EPIC: SPEC_REPO#EPIC

===================
Other requirements
===================

.. contents:: Table of Contents

1. Timing
-----------

* Screen transition timings
* Backend services expected response time requirements
* Expected processing time of operations

2. Security
-------------

* User Inputs

  - Security considerations and limitations that affect handling user input
  - Limit input text size to X characters.
  - Specify what are the expected encoding, character ranges.

* Network Communication

  - Specify how wrong formats handled.
  - Specify how upload / download size of the requests and responses should be limited
  - Specify handling of exceptional and error situations

* Other Considerations here as well

3. Reliability
----------------

* Consequences of the software failures

  - What happens when software will crash at any point? 

    + How that affects user data?
    + How should the critical data be protected from failure?

  - Other cases or important ways in which software may err or fail and their handling.
  
* Error detection

  - How software detects errors and how it tries to recover, if it ever tries?

4. Memory and Storage
-----------------------

* Maximum memory limit
* Maximum storage space limit

5. Maintainability
---------------------

* Requirements for maintainability

* The software should be easy to adopt changes in the external communications
* The software should be easy to adopt changes in the User Interface.
  The software should be easy to adopt changes in the sequence of the screens.


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

* User Interface designs are likely to change in X months

  - What can change. Why?

* Network Service APIs may change
 
  - What can change, with which likelihood and why?

* Other things that are likely to change.
