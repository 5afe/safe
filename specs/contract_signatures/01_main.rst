==========================================================
Contract Signatures
==========================================================

=====  ===================
epic      title       
=====  ===================
`78`_  Contract Signatures
=====  ===================

.. _78: https://github.com/gnosis/safe/issues/78

.. _Main:


#. `Main`_

.. sectnum::
.. contents:: Table of Contents
    :local:
    :depth: 2

Problem Definition
---------------------


Technical Details
-----------------

Diagram_

1. Dapp sends a JSON payload request to the browser extension.

2. The chome extension signs the hash of the payload according to EIP-712_ and sends the following ``message`` to the app (via push notification) (See RootMessage_ for the root object used with the Notification Service).

.. code:: javascript
    
    {
        "type": "signTypedData"
        "payload": <string> // Payload to sign
        "signed-hash": <hex-string> // Signature of the hash of the payload according to EIP712
        "address": <checksummed_address> // Address of the signer (Browser Extension)
    }


3. App: recover the address from the payload and verifies that it matches the address from the browser extension.
4. App: signs the payload and waits for the other signatures from other possible signers (until threshold is reached).
5. App sends push to the chrome extension with all the signatures. The ``message`` of the push notification is the following:

.. code:: javascript
    
    {
        "type": "signTypedDataResult"
        "payload": <string> // Payload to sign
        "signed-hashes": [<hex-string>, ...] // Signature of the hash of the payload according to EIP712
    }

6. The browser extension recovers each address and verifies that it has enough signatures (threshold reached) for that safe.
7. Show signed payload on the dApp side

.. _Diagram: https://sketchboard.me/FBr2iwh2wYbm#/
.. _EIP-712: https://github.com/ethereum/EIPs/blob/master/EIPS/eip-712.md
.. _RootMessage: https://gnosis-safe.readthedocs.io/en/latest/services/notifications.html#request
