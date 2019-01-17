========  ===========================  ================  ==========
epic      title                        author            created
========  ===========================  ================  ==========
`60`_     Replace Browser Extension    DmitryBespalov    2019-01-04
========  ===========================  ================  ==========

.. _60: gnosis/safe#60

=========================
External Communication
=========================

.. contents:: Table of Contents

1. Ethereum Node
--------------------

**Protocol:** JSON-RPC via REST calls to an Ethereum node through Infura
service

- `Ethereum JSON RPC Documentation`_
- `Infura Getting Started Documentation`_
- `Solidity Contract ABI Specification`_

1.1. Get Balance of the Safe address in ETH
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

* **Method:** eth_getBalance_
* **Parameters:**

  - address of the Safe as a hex-encoded UInt160 (see Solidity ABI)
  - blockchain's block identifier: ``latest``

* **Returns:** ``uint256`` - Solidity ABI-encoded balance in Wei
  (ETH's smallest unit)

1.2. Get Owners of the Safe
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

* **Method:** eth_call_
* **Parameters:**

  - to: Safe's address
  - data: Solidity ABI-encoded method call

    + selector: ``getOwners()``
    + arguments: none

* **Returns:** ``[address]`` - Solidity ABI-encoded array of the ``uin160``
  addresses

1.3. Get Safe Threshold
~~~~~~~~~~~~~~~~~~~~~~~~~~~

* **Method:** eth_call_
* **Parameters:**

  - to: Safe's address
  - data: Solidity ABI-encoded method call
    + selector: ``getThreshold()``
    + arguments: none

* **Returns:** ``uint256`` - Solidity ABI-encoded UInt value

1.4. Getting status of a pending transaction
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

* **Method**: eth_getTransactionReceipt_
* **Parameters:**

  - hash of a transaction - 32 bytes serialized as a hex digit string

* **Returns:** receipt object that has a `status` field with `1` for
  success and `0` for failure. Can return null, when receipt not found.
  Receipt is not available for pending transactions.

2. Notification Service
---------------------------

**Protocol:** REST using JSON payloads sent to the Gnosis Safe's
Notification Service.

- `Source code <notification_service_source>`_
- `Development API Documentation <notification_service_dev_>`_
- `Staging API Documentation <notification_service_staging_>`_
- `Production API Documentation <notification_service_prod_>`_

2.1. Create New Device Pair
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

* **Endpoint:** ``POST /api/v1/pairing/``
* **JSON Payload:**

.. code::

    {
        "temporaryAuthorization": {
            "expirationDate": "<date>", // format: yyyy-MM-dd’T’HH:mm:ss+00:00 ; UTC timezone; example: 2018-04-18T14:46:09+00:00
            "signature": { // signs sha3("GNO" + <expirationDate>) - this is signature from browser extension
                "v": 0, // <integer>,
                "r": "<string>", // stringified int
                "s": "<string>" // stringified int
            },
        },
        "signature": { // signs sha3("GNO" + <chrome-extension-address>) - this is app’s signature
            "v": 0, // <integer>,
            "r": "<string>", // stringified int
            "s": "<string>" // stringified int
        }
    }

* **Responses:**

  - 201 - OK, payload:

.. code::

    {
        "devicePair": [
            "<string>", “<string>" // addresses of the pair, in checksummed EIP55 format
        ]
    }

* - 400 - invalid request

    + When expiration date is invalid (earlier than current time)
    + When any signature is invalid

  - 500 - Internal server error

2.2. Delete Old Device Pair
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

* **Endpoint:** ``DELETE /api/v1/pairing/``
* **JSON Payload:**

.. code::

    {
        "device": “<address>", // Address must be in a checksummed format (EIP 55)
        "signature": { // signs sha3("GNO" + <address>)
            "v": <integer>,
            "r": "<string>", // stringified int
            "s": "<string>" // stringified int
        }
    }

* - The ``device`` parameter is the address of the browser extension
  - The ``signature`` is derived by the signing with the app’s private
    key (keccak's SHA3-256)

* **Responses:**

  - 204 - OK
  - 400 - Invalid request

    + Some fields are missing
    + Signature is invalid
    + No such pair exists

  - 500 - Internal server error

2.3 Notify New Extension about the connected Safe
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

* **Endpoint:** ``POST /api/v1/notifications/``
* **JSON Payload:**

.. code::

    {
        "devices": [“<new browser extension address in checksummed EIP55 format>"],
        "message": “<notification contents>",
        "signature": { // signs sha3("GNO" + <message>)
            "v": <integer>,
            "r": "<string>", // stringified int
            "s": "<string>" // stringified int
        }
    }

* - ``<notification contents>`` is a JSON string:

.. code::

    {
      "type": "safeCreation",
      "safe": “<address>", // in checksummed EIP55 format
    }

* - **ATTENTION:** Service does not validate the contents of
    the ``message`` parameter.
  - The ``device`` parameter is address of the browser extension
  - The signature is signed by the app’s private key

* **Responses:**

  - 204 - OK
  - 400 - Invalid request

    + device pair does not exist (sender is the address extracted from the
      signature using “ecrecover” algorithm, and recipient are addresses in
      the “devices” parameter
    + signature is invalid

  - 500 - Internal server error

3.Relay Service
-------------------

**Protocol:** REST using JSON payloads sent to the Gnosis Safe's Relay Service.

- `Source code <relay_service_source>`__
- `Development API Documentation <relay_service_dev_>`__
- `Staging API Documentation <relay_service_staging_>`__
- `Production API Documentation <relay_service_prod_>`__

3.1. Estimating "Replace Owner" Transaction Parameters
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

* **Endpoint:** ``POST /api/v1/safes/{address}/transactions/estimate``
* **JSON Payload:**

.. code::

    {
      "safe": "<sender safe address>",
      "to": "<tx recipient Ethereum address>", // optional
      "value": "0", // stringified int, in wei
      "data": "string", // prefixed or unprefixed hex string, optional
      "operation": 0, // 0 = call, 1 = delegateCall, 2 = create
      "gasToken": "string" // optional
    }

* **Responses:**
  - 200 - OK, payload:

.. code::

    {
      "safeTxGas": 0,
      "dataGas": 0,
      "operationalGas": 0,
      "gasPrice": 0,
      "lastUsedNonce": 0, // nonce of last tx processed
      "gasToken": "string"  // hexadecimal address, checksumed, address(0) for now
    }

* - + **NOTE:** total transaction cost is estimated as
      `gasPrice * (safeTxGas + dataGas + operationalGas)`. The `operationalGas`
      is only used for customer-facing calculation of transaction
      estimation and is not used when transaction is submitted for execution.

  - 400 - Invalid request
  - 404 - Safe not found
  - 422 - Safe address checksum not valid or Tx not valid
  - 500 - Internal server

3.2. Submitting Transaction
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

* **Endpoint:** ``POST /api/v1/safes/{address}/transactions/``
* **JSON Payload:**

.. code::

    {
      "safe": "<sender safe address>",
      "to": "<recipient's Ethereum address>", // optional
      "value": "0", // stringified int, in wei, base 10
      "data": "string", // prefixed or unprefixed hex string, optional
      "operation": 0, // 0 = call, 1 = delegateCall, 2 = create
      "gasToken": "string", // address, optional
      "safeTxGas": 0, // stringified int, base 10
      "dataGas": 0, // stringified int, base 10
      "gasPrice": 0, // stringified int, base 10
      "refundReceiver": "string", // optional
      "nonce": 0,
      "signatures": [ // Sorted lexicographically by lowercased owner address
        {
          "v": 0,
          "r": "0",
          "s": "0"
        }
      ]
    }

* - Pass the result of estimation request as the `safeTxGas`,
    `dataGas`, `gasPrice` and `gasToken` parameters.

* **Responses:**
  - 201 - OK, payload:

.. code::

    {
      "transactionHash": "string" // 32-byte transaction hash as a hex data string
    }

* - 400 - Invalid request
  - 404 - Safe not found
  - 422 - Safe address checksum not valid or Tx not valid
  - 500 - Internal server error

4. Browser Extension
------------------------

**Protocol**: QR-code encoding a JSON payload.

- `Source code <extension_source_>`__
- `Staging-Rinkeby <extension_staging_>`_
- `Pre-Production-Rinkeby <extension_preprod_rinkeby_>`_
- `Production-Rinkeby <extension_prod_rinkeby_>`_
- `Pre-Production-Mainnet <extension_preprod_mainnet_>`_
- `Production-Mainnet <extension_prod_mainnet_>`_

4.1. New browser extension’s registration code
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

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
.. _extension_staging: https://chrome.google.com/webstore/detail/gnosis-safe-rinkeby/onhbkfhncfcgjenedjnbhdjggnnbflbe
.. _extension_preprod_rinkeby: https://chrome.google.com/webstore/detail/gnosis-safe-rinkeby/ananopmgehnpbbjpphfelfmhbpcajaii
.. _extension_prod_rinkeby: https://chrome.google.com/webstore/detail/gnosis-safe-rinkeby/gkiklnclpcbphbiaickiepnnnahefkoc
.. _extension_preprod_mainnet: https://chrome.google.com/webstore/detail/gnosis-safe/cakigglcodkncnmkjhmkpadaemhbnfkc
.. _extension_prod_mainnet: https://chrome.google.com/webstore/detail/gnosis-safe/iecodoenhaghdlpodmhooppdhjhmibde
