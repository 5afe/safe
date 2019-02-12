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

1. Dapp sends a JSON payload request to the browser extension.

2. The chome extension signs the hash of the payload according to EIP712 and sends the following payload to the app (via push notification)

{
  "payload" : <string> // Payload that the app needs to sign
  "signed-hash" : <hex-string> // Signature of the hash of the payload according to ERC67
  "address" : <checksummed-address-string>
}

3. App: recover the address from the payload and verify that it matches the address from the browser extension.
4. App: signs the payload and waits for the other signatures from other possible signers (until threshold is reached).
5. App sends push to the chrome extension with all the signatures
6. Show signed payload on the dApp side
