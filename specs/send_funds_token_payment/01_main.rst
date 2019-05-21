==========================================================
Send funds - Token payment
==========================================================

=====  ========================  =========  ==========
epic            title             author     created
=====  ========================  =========  ==========
`89`_  Send funds Token payment  tschubotz  2019-05-21
=====  ========================  =========  ==========

.. _89: https://github.com/gnosis/safe/issues/89

.. sectnum::
.. contents:: Table of Contents
    :local:


What is this feature about? (1 sentence)
----------------------------------------

This feature will enable users to pay transaction fees with tokens like DAI, OWL or others.


Why is it needed? What is the value? For whom do we build it?
----------------------------------------------------------------

Currently, all transaction fees have to be paid in ETH ("gas"). That means, for all transactions, a user needs ETH. They are unable to make transactions without ETH, even if they own a significant amount of funds in tokens. 
Users were asking for this features. One of the reasons is, that they would like to pay fees with a stable token like DAI or OWL in order to be more independent from the volatile ETH price.
Additionally, this creates a use case for GNO holders to use their OWL, which is important for Gnosis as a company.


High-level overview of the feature
----------------------------------

We use meta-transactions anyway already, i.e. our relay service pays for transaction fees in ETH and then gets refunded in ETH from the user's Safe as part of the transaction. We would change this, so that the refund happens in a token.
There will a list of tokens that the relay service accepts as payment. We will also have to incorporate a price oracle to determine the fee amount. DutchX will be one price oracle.

This feature affects the following flows & screens:

- Safe creation 
- Send funds 👈 this spec
- Connect browser extension
- Replace browser extension
- Replace recovery phrase
- Recover Safe 
- Menu 

The payment method is set per Safe but can be changed before making a transaction and also via the menu. 

The smart contracts and the backend are already ready for this change. We "just" have to incorporate this into the frontends now.


Screens
---------------------

[TOKEN PAYMENT] Send_Input
~~~~~~~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/[TOKEN PAYMENT] Send_Input.png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/(Token Payment) Send_Input.png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/bWN3DN1
      </td>
      <td>
        https://zpl.io/adz5qB5
      </td>
    </tr>
  </table>
  
  
[TOKEN PAYMENT] Send_Input (payment token tooltip)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/[TOKEN PAYMENT] Send_Input (payment token tooltip).png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/(Token Payment) Send_Input (payment token tooltip).png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/aBR3YWK
      </td>
      <td>
        https://zpl.io/2pv903j
      </td>
    </tr>
  </table>
  
  
Send_Input (enter address)
~~~~~~~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/Send_Input (enter address).png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/Send_Input (enter address).png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/VQKNee4
      </td>
      <td>
        https://zpl.io/2p4MGzy
      </td>
    </tr>
  </table>
  
  
[TOKEN PAYMENT] Send_Input (network fee dialog)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/[TOKEN PAYMENT] Send_Input (network fee dialog).png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/(Token Payment) Send_Input (network fee dialog).png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/aNmrP1N
      </td>
      <td>
        https://zpl.io/bWNE0gn
      </td>
    </tr>
  </table>
  
  
[TOKEN PAYMENT] Send_Input (amount filled)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/[TOKEN PAYMENT] Send_Input (amount filled).png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/(Token Payment) Send_Input (filled).png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/bPx3ADD
      </td>
      <td>
        https://zpl.io/2pveYDj
      </td>
    </tr>
  </table>
  
  
[TOKEN PAYMENT] Send_Input (error)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/[TOKEN PAYMENT] Send_Input (error).png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/(Token Payment) Send_Input (error).png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/blDnXYP
      </td>
      <td>
        https://zpl.io/25JvKno
      </td>
    </tr>
  </table>
  
  
[TOKEN PAYMENT] Send_Input (token)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/[TOKEN PAYMENT] Send_Input (token).png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/(Token Payment) Send_Input (token).png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/a31JYdY
      </td>
      <td>
        https://zpl.io/b647mjq
      </td>
    </tr>
  </table>
  
  
[TOKEN PAYMENT] Send_Input (no internet)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/[TOKEN PAYMENT] Send_Input (no internet).png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/(Token Payment) Send_Input (no internet).png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/a87LmzE
      </td>
      <td>
        https://zpl.io/V0L4eOK
      </td>
    </tr>
  </table>
  
  
[TOKEN PAYMENT] Send_Input (token amount filled)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/[TOKEN PAYMENT] Send_Input (token amount filled).png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/(Token Payment) Send_Input (OWL selected).png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/aX30Pd8
      </td>
      <td>
        https://zpl.io/brvQXWX
      </td>
    </tr>
  </table>
  
  
(Token Payment) Send_Input (OWL selected error)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/MISSING.png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/(Token Payment) Send_Input (OWL selected error).png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        
      </td>
      <td>
        https://zpl.io/2yq90z9
      </td>
    </tr>
  </table>
  
  
[TOKEN PAYMENT] Send_Review2FARequired (token)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/[TOKEN PAYMENT] Send_Review2FARequired (token).png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/(Token Payment) Send_Review2FARequired.png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/VKDO7EX
      </td>
      <td>
        https://zpl.io/V0L1mRQ
      </td>
    </tr>
  </table>
  
  
[TOKEN PAYMENT] Send_Input (filled tooltip)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/[TOKEN PAYMENT] Send_Input (filled tooltip).png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/Send_Input (filled tooltip).png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/2j5z7ZQ
      </td>
      <td>
        https://zpl.io/a31m9Ex
      </td>
    </tr>
  </table>
  
  
[TOKEN PAYMENT] Send_Input (balance tooltip)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/[TOKEN PAYMENT] Send_Input (balance tooltip).png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/Send_Input (balance tooltip).png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/2pvqZA8
      </td>
      <td>
        https://zpl.io/2ZLXKzJ
      </td>
    </tr>
  </table>
  
  
[TOKEN PAYMENT] Send_Review2FAConfirmed (token)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/[TOKEN PAYMENT] Send_Review2FAConfirmed (token).png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/Send_Review2FAConfirmed.png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/aRxkQpK
      </td>
      <td>
        https://zpl.io/aR1A8Wv
      </td>
    </tr>
  </table>
  
  
[TOKEN PAYMENT] Send_Review2FARejected (token)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/[TOKEN PAYMENT] Send_Review2FARejected (token).png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/Send_Review2FARejected.png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/29w3YQB
      </td>
      <td>
        https://zpl.io/V1NgdNk
      </td>
    </tr>
  </table>
  
  
[TOKEN PAYMENT] Send_Review (token)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/[TOKEN PAYMENT] Send_Review (token).png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/MISSING.png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/VDA3Yeq
      </td>
      <td>
        
      </td>
    </tr>
  </table>
  
  
(Token Payment) TransactionDetail (outgoing)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/MISSING.png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/(Token Payment) TransactionDetail (outgoing).png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        
      </td>
      <td>
        https://zpl.io/beA0joq
      </td>
    </tr>
  </table>
  
  
Send_Review2FARequired (enable push)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/MISSING.png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/Send_Review2FARequired (enable push).png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        
      </td>
      <td>
        https://zpl.io/agQ0qz9
      </td>
    </tr>
  </table>
  
  
Send_Success
~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/Send_Success.png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/Send_Success.png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/bzNpeO3
      </td>
      <td>
        https://zpl.io/2v7QeO7
      </td>
    </tr>
  </table>
  
  


  
.. _`short amount`: ../common/format_amounts.rst#short-amount