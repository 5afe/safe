=========================
Technical Details
=========================

========  ===========================  ================  ==========
epic      title                        author            created
========  ===========================  ================  ==========
`60`_     Replace Browser Extension    DmitryBespalov    2019-01-04
========  ===========================  ================  ==========

.. _60: https://github.com/gnosis/safe/issues/60

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

Ethereum Node
~~~~~~~~~~~~~~~~~

- `Ethereum JSON RPC Documentation`_
- `Infura Getting Started Documentation`_
- `Solidity Contract ABI Specification`_

Requests:

- eth_getBalance_
- eth_call_

  + selector: ``getOwners()``
  + selector: ``getThreshold()``

- eth_getTransactionReceipt_

Notification Service
~~~~~~~~~~~~~~~~~~~~~~~

- `Source code <notification_service_source>`_
- `Development API Documentation <notification_service_dev_>`_
- `Staging API Documentation <notification_service_staging_>`_
- `Production API Documentation <notification_service_prod_>`_


Requests:

- ``POST /api/v1/pairing/``
- ``DELETE /api/v1/pairing/``
- ``POST /api/v1/notifications/`` with ``safeCreation`` message type

Relay Service
~~~~~~~~~~~~~~~~

- `Source code <relay_service_source>`__
- `Development API Documentation <relay_service_dev_>`__
- `Staging API Documentation <relay_service_staging_>`__
- `Production API Documentation <relay_service_prod_>`__

Requests:

- ``POST /api/v1/safes/{address}/transactions/estimate``
- ``POST /api/v1/safes/{address}/transactions/``


Browser Extension
~~~~~~~~~~~~~~~~~~~

- `Source code <extension_source_>`__

QR-code encoding a JSON payload.

* Contains expiry date that limits signature’s validity.
  App should check for it before using the signature.
* The signature implicitly encodes the browser extension’s address.
  To extract the address of the signer, use the “ecrecover” algorithm.

.. code::

    {
        "expirationDate": “<date>", // format: yyyy-MM-dd’T’HH:mm:ss+00:00 ; UTC timezone; example: 2018-04-18T14:46:09+00:00
        "signature": { // signs sha3("GNO" + <expirationDate>)
            "v": <integer>,
            "r": "<string>", // stringified int (decimal)
            "s": "<string>" // stringified int (decimal)
        }
    }


Timing
-----------

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


Security
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

* Recovery Phrase

  - Application must not persist the Recovery Phrase or derived keys, but
    only use it for the transaction signing.
  - Application must remove the phrase from memory as soon as possible.
  - Before removing, the program must override the memory with trash data.
  - Check that the recovery phrase in the pasteboard cannot be read
    by another app without explicit user action.
  - Recovery phrase is shown as plain text, so that user can
    visually check it.


Reliability
----------------

* Consequences of the software failures

  - Crashing before submitting transaction to the network

    + This should not affect the app in any way as nothing should be changed.

  - Crashing after submitting transaction to the network but before
    persisting this information. The transaction executes successfully.

    + This will leave the app knowing it's connected to the old extension
      while in fact the new extension became an owner. This will
      prevent the user from making any transactions except replacing
      the extension one more time. In that case, the "replace
      browser extension" option should repair the state by
      reconnecting with new extension but not submitting
      the transaction to the blockchain.
      This conflicts with the use case `Existing Extension Scanned`_

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

Possible Changes to the Specification
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

.. _`Existing Extension Scanned`: 01_main.rst
.. _`Common Technical Requiremets`: ../common/technical_requirements.rst
.. _Ethereum JSON RPC Documentation: https://github.com/ethereum/wiki/wiki/JSON-RPC
.. _Infura Getting Started Documentation: https://infura.io/docs/gettingStarted/chooseaNetwork
.. _Solidity Contract ABI Specification: https://solidity.readthedocs.io/en/v0.5.2/abi-spec.html
.. _eth_getBalance: https://github.com/ethereum/wiki/wiki/JSON-RPC#eth_getbalance
.. _eth_call: https://github.com/ethereum/wiki/wiki/JSON-RPC#eth_call
.. _eth_getTransactionReceipt: https://github.com/ethereum/wiki/wiki/JSON-RPC#eth_gettransactionreceipt
.. _notification_service_source: https://github.com/gnosis/safe-notification-service/tree/develop
.. _notification_service_dev: https://safe-notification.dev.gnosisdev.com
.. _notification_service_staging: https://safe-notification.staging.gnosisdev.com
.. _notification_service_prod: https://safe-notification.gnosis.pm
.. _relay_service_source: https://github.com/gnosis/safe-relay-service/tree/develop
.. _relay_service_dev: https://safe-relay.dev.gnosisdev.com
.. _relay_service_staging: https://safe-relay.staging.gnosisdev.com
.. _relay_service_prod: https://safe-relay.gnosis.pm
.. _extension_source: https://github.com/gnosis/safe-browser-extension/tree/develop
