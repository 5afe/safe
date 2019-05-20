==========================================================
Create Safe - Token payment
==========================================================

=====  =========================  =========  ==========
epic            title             author     created
=====  =========================  =========  ==========
`89`_  Create Safe Token payment  tschubotz  2019-05-15
=====  =========================  =========  ==========

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
- Safe creation 👈 this spec
- Send funds 
- Connect browser extension
- Replace browser extension
- Replace recovery phrase
- Recover Safe
- Menu

The payment method is globally set but can be changed before making a transaction and also via the menu. 

The smart contracts and the backend are already ready for this change. We "just" have to incorporate this into the frontends now.


Screens
---------------------

Onboarding_RecoveryIntro
~~~~~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/Onboarding_RecoveryIntro.png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/Onboarding_RecoveryIntro.png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/V0EBR5l
      </td>
      <td>
        https://zpl.io/bJ76pP9
      </td>
    </tr>
  </table>
  
  
Onboarding_2FA
~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/Onboarding_2FA.png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/Onboarding_2FA.png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/V18Bzpm
      </td>
      <td>
        https://zpl.io/VqWMkWY
      </td>
    </tr>
  </table>
  
  
Onboarding_2FA (share)
~~~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/Onboarding_2FA (share).png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/Onboarding_2FA (share).png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/a3eGRB8
      </td>
      <td>
        https://zpl.io/agzEOWO
      </td>
    </tr>
  </table>
  
  
Onboarding_SeedIntro
~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/Onboarding_SeedIntro.png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/Onboarding_SeedIntro.png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/b6y0jxP
      </td>
      <td>
        https://zpl.io/VOP3pP1
      </td>
    </tr>
  </table>
  
  
Onboarding_ShowSeed
~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/Onboarding_ShowSeed.png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/Onboarding_ShowSeed.png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/awrk6jJ
      </td>
      <td>
        https://zpl.io/2yOW80p
      </td>
    </tr>
  </table>
  
  
Onboarding_EnterSeed
~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/Onboarding_EnterSeed.png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/Onboarding_EnterSeed.png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/bzAvEM8
      </td>
      <td>
        https://zpl.io/bJ7z83n
      </td>
    </tr>
  </table>
  
  
Onboarding_EnterSeed (semi filled)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/Onboarding_EnterSeed (semi filled).png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/Onboarding_EnterSeed (semi filled).png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/bldv5W1
      </td>
      <td>
        https://zpl.io/adpmNr7
      </td>
    </tr>
  </table>
  
  
Onboarding_EnterSeed (filled)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/Onboarding_EnterSeed (filled).png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/Onboarding_EnterSeed (flled).png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/bJ9wy3E
      </td>
      <td>
        https://zpl.io/bPPzgXD
      </td>
    </tr>
  </table>
  
  
Onboarding_EnterSeed (error)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/Onboarding_EnterSeed (error).png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/Onboarding_EnterSeed (filled error).png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/2v7QPJv
      </td>
      <td>
        https://zpl.io/aw4j4r1
      </td>
    </tr>
  </table>
  
  
[Token Payment] Onboarding_CreationFeeIntro
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/[Token Payment] Onboarding_CreationFeeIntro.png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/(Token Payment) Onboarding_CreationFeeIntro.png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/25JDk1j
      </td>
      <td>
        https://zpl.io/adz58gl
      </td>
    </tr>
  </table>
  
  
[Token Payment] Onboarding_PaymentMethod
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/[Token Payment] Onboarding_PaymentMethod.png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/(Token Payment) Onboarding_PaymentMethod.png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/anyglRk
      </td>
      <td>
        https://zpl.io/amdNlJr
      </td>
    </tr>
  </table>
  
  
Onboarding_CreationFee (creation fee dialog)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/Onboarding_CreationFee (creation fee dialog).png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/(Token Payment) Onboarding_CreationFeeIntro (modal).png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/aR1A0jN
      </td>
      <td>
        https://zpl.io/Vx0e5jW
      </td>
    </tr>
  </table>
  
  
[Token Payment] Onboarding_CreationFeeIntro (GNO selected)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/[Token Payment] Onboarding_CreationFeeIntro (GNO selected).png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/(Token Payment) Onboarding_CreationFeeIntro (OWL selected).png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/25JDkzo
      </td>
      <td>
        https://zpl.io/b64EYYm
      </td>
    </tr>
  </table>
  
  
[TOKEN PAYMENT] Onboarding_CreationFee
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/[TOKEN PAYMENT] Onboarding_CreationFee.png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/(Token Payment) Onboarding_CreationFee (token payment).png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/VqvN1w5
      </td>
      <td>
        https://zpl.io/VQv8ggk
      </td>
    </tr>
  </table>
  
  
[TOKEN PAYMENT] Onboarding_CreationFee (address copied)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/[TOKEN PAYMENT] Onboarding_CreationFee (address copied).png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/(Token Payment) Onboarding_CreationFee (address copied).png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/Vqv4GN7
      </td>
      <td>
        https://zpl.io/aRx8QQK
      </td>
    </tr>
  </table>
  
  
Onboarding_CreationFee (creation fee dialog)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/Onboarding_CreationFee (creation fee dialog).png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/(Token Payment) Onboarding_CreationFee (modal).png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/aR1A0jN
      </td>
      <td>
        https://zpl.io/2j5xBBr
      </td>
    </tr>
  </table>
  
  
[TOKEN PAYMENT] Onboarding_CreationFee (insufficient funds)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/[TOKEN PAYMENT] Onboarding_CreationFee (insufficient funds).png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/(Token Payment) Onboarding_CreationFee (insufficient funds).png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/aMWeLKo
      </td>
      <td>
        https://zpl.io/V4ex3kJ
      </td>
    </tr>
  </table>
  
  

