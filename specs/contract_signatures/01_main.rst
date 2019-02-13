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
        "hash": <hex-string> // Signature of the hash of the payload according to EIP712
    }


3. App: signs the payload and waits for the other signatures from other possible signers (until threshold is reached).
4. App sends push to the chrome extension with all the signatures. The ``message`` of the push notification is the following:

.. code:: javascript
    
    {
        "type": "signTypedDataResult"
        "signature": <hex-string> // Signature of the hash of the payload according to EIP712
    }

5. Optional: The browser extension validates the signature with an rpc-call against the safe contract.
6. Show signed payload on the dApp side.

.. _Diagram: https://sketchboard.me/FBr2iwh2wYbm#/
.. _EIP-712: https://github.com/ethereum/EIPs/blob/master/EIPS/eip-712.md
.. _RootMessage: https://gnosis-safe.readthedocs.io/en/latest/services/notifications.html#request
