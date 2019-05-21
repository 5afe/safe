==========================================================
Recover Safe - Token payment
==========================================================

=====  ==========================  =========  ==========
epic             title              author     created
=====  ==========================  =========  ==========
`89`_  Recover Safe Token payment  tschubotz  2019-05-20
=====  ==========================  =========  ==========

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
- Send funds 
- Connect browser extension
- Replace browser extension
- Replace recovery phrase
- Recover Safe 👈 this spec
- Menu 

The payment method is set per Safe but can be changed before making a transaction and also via the menu. 

The smart contracts and the backend are already ready for this change. We "just" have to incorporate this into the frontends now.


Screens
---------------------

Recover_Intro
~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/Recover_Intro.png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/Recover_Intro.png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/a8wGjNK
      </td>
      <td>
        https://zpl.io/aR1GrYn
      </td>
    </tr>
  </table>
  
  
Recover_InputAddress
~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/Recover_InputAddress.png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/Recover_InputAddress.png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/aw4OL1N
      </td>
      <td>
        https://zpl.io/2yOW8y9
      </td>
    </tr>
  </table>
  
  
Recover_InputAddress (enter address)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/Recover_InputAddress (enter address).png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/Recover_InputAddress (edit address).png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/aR1GrPv
      </td>
      <td>
        https://zpl.io/adpN4P7
      </td>
    </tr>
  </table>
  
  
Recover_InputAddress (error)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/Recover_InputAddress (error).png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/Recover_InputAddress (error).png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/bABWjE8
      </td>
      <td>
        https://zpl.io/VxLw81R
      </td>
    </tr>
  </table>
  
  
Recover_InputAddress (address filled)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/Recover_InputAddress (address filled).png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/Recover_InputAddress (correct).png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/am5eOyv
      </td>
      <td>
        https://zpl.io/VKPypo6
      </td>
    </tr>
  </table>
  
  
Recover_EnterSeed
~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/Recover_EnterSeed.png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/Recover_EnterSeed.png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/bJ7W5Zr
      </td>
      <td>
        https://zpl.io/2yOW8lo
      </td>
    </tr>
  </table>
  
  
Recover_EnterSeed (error)
~~~~~~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/Recover_EnterSeed (error).png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/Recover_EnterSeed (error).png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/b61gZ3R
      </td>
      <td>
        https://zpl.io/aw4OLmM
      </td>
    </tr>
  </table>
  
  
Recover_EnterSeed (filled)
~~~~~~~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/Recover_EnterSeed (filled).png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/Recover_EnterSeed (correct).png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/2GyAvWd
      </td>
      <td>
        https://zpl.io/2GyW79E
      </td>
    </tr>
  </table>
  
  
Recover_2FA
~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/Recover_2FA.png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/Recover_2FA.png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/VDBK9Wq
      </td>
      <td>
        https://zpl.io/2v701K7
      </td>
    </tr>
  </table>
  
  
Recover_2FA (share)
~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/Recover_2FA (share).png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/Recover_2FA (share).png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/a8wkvRE
      </td>
      <td>
        https://zpl.io/VYKowGM
      </td>
    </tr>
  </table>
  
  
Recover_2FAScan
~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/Recover_2FAScan.png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/Replace2FA_Scan (camera).png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/V1Nk53Z
      </td>
      <td>
        https://zpl.io/bzNDOLz
      </td>
    </tr>
  </table>
  
  
Recover_2FA (error)
~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/Recover_2FA (error).png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/Recover_2FAScan (error).png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/2GykwYj
      </td>
      <td>
        https://zpl.io/V1NkXnJ
      </td>
    </tr>
  </table>
  
  
[Token Payment] Recover_RecoveryFeeIntro
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/[Token Payment] Recover_RecoveryFeeIntro.png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/(Token payment) Recover_RecoveryFeeIntro.png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/25JDK1r
      </td>
      <td>
        https://zpl.io/aBRJ11Q
      </td>
    </tr>
  </table>
  
  
(Token payment) Recover_RecoveryFeeIntro (modal)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/MISSING.png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/(Token payment) Recover_RecoveryFeeIntro (modal).png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        
      </td>
      <td>
        https://zpl.io/amdAD8A
      </td>
    </tr>
  </table>
  
  
[Token Payment] Recover_PaymentMethod
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/[Token Payment] Recover_PaymentMethod.png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/(Token Payment) Recover_PaymentMethod.png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/aX3Ao8g
      </td>
      <td>
        https://zpl.io/a7W9wGM
      </td>
    </tr>
  </table>
  
  
Recover_Fee
~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/Recover_Fee.png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/(Token Payment) Recover_RecoveryFee (insufficient funds).png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/29OKRjw
      </td>
      <td>
        https://zpl.io/a7W9wZY
      </td>
    </tr>
  </table>
  
  
Recover_Fee (no browser extension)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/Recover_Fee (no browser extension).png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/Recover_Review (no browser extension).png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/2EBzKJn
      </td>
      <td>
        https://zpl.io/aR1GrzE
      </td>
    </tr>
  </table>
  
  
Recover_Review
~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/Recover_Review.png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/Recover_Review.png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/aXP9LPE
      </td>
      <td>
        https://zpl.io/aMPRBP3
      </td>
    </tr>
  </table>
  
  
Recover_FeePaid
~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/Recover_FeePaid.png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/Recover_FeePaid.png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/agzM5m0
      </td>
      <td>
        https://zpl.io/2p4kyMj
      </td>
    </tr>
  </table>
  
  
