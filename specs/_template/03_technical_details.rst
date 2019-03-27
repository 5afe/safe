=========================
Technical Details
=========================

=======  ==================  ======  ==========
 epic          title         author   created
=======  ==================  ======  ==========
`EPIC`_  SPECIFICATION_NAME  AUTHOR  CREATED_AT
=======  ==================  ======  ==========

.. _EPIC: https://github.com/gnosis/safe/issues/EPIC

.. sectnum::
.. contents:: Table of Contents
    :local:
    :depth: 2

Please describe the relevant technical requirements in this document.
Please remove all unrelated sections to keep the document easy to read and maintain.

Common Technical Requirements
-------------------------------

The feature implementation must fulfill the technical requirements specified in
the `Common Technical Requiremets`_ unless
specifically noted in this document below.

Communication
---------------

Describe APIs and provide links to the documentation here (swagger, readthedocs, and so on).

Timing
-----------

Define timing requirements here if they're different from common requirements.

* Screen transition timings
* Backend services expected response time requirements
* Expected processing time of operations

Security
-------------

Define security requirements here if they're different from common requirements.

* User Inputs

  - Security considerations and limitations that affect handling user input
  - Limit input text size to X characters.
  - Specify what are the expected encoding, character ranges.


* Network Communication

  - Specify how wrong formats handled.
  - Specify how upload / download size of the requests and responses should be limited
  - Specify handling of exceptional and error situations

* Other Considerations here as well

Reliability
----------------

* Consequences of the software failures

  - What happens when software will crash at any point? 

    + How that affects user data?
    + How should the critical data be protected from failure?

  - Other cases or important ways in which software may err or fail and their handling.
  
* Error detection

  - How software detects errors and how it tries to recover, if it ever tries?

Memory and Storage
-----------------------

* Maximum memory limit
* Maximum storage space limit
* Define them here if they're different from common requirements.

Maintainability
---------------------

* Requirements for maintainability
* Define them here if they're different from common requirements.


Definition of Success
---------------------------

Define it here if it's different from the common definition.

Possible Changes to the Specification
------------------------------------------

* User Interface designs are likely to change in X months

  - What can change. Why?

* Network Service APIs may change
 
  - What can change, with which likelihood and why?

* Other things that are likely to change.

.. _`Common Technical Requiremets`: ../common/technical_requirements.rst
