==========================================================
Replace browser extension - Token payment
==========================================================

=====  =============================================  =========  ==========
epic                       title                       author     created
=====  =============================================  =========  ==========
`89`_  Replace browser extension funds Token payment  tschubotz  2019-05-21
=====  =============================================  =========  ==========

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
- Replace browser extension 👈 this spec
- Replace recovery phrase
- Recover Safe 
- Menu 

The payment method is set per Safe but can be changed before making a transaction and also via the menu. 

The smart contracts and the backend are already ready for this change. We "just" have to incorporate this into the frontends now.


Screens
---------------------

[TOKEN PAYMENT] Replace2FA
~~~~~~~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/[TOKEN PAYMENT] Replace2FA.png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/(Token Payment) Replace2FA.png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/V1OXekB
      </td>
      <td>
        https://zpl.io/25JDK4W
      </td>
    </tr>
  </table>
  
  
[TOKEN PAYMENT] Replace2FA (insufficient funds)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/[TOKEN PAYMENT] Replace2FA (insufficient funds).png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/(Token Payment) Replace2FA (insufficient funds).png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/V0LOlXO
      </td>
      <td>
        https://zpl.io/bJp6nMr
      </td>
    </tr>
  </table>
  
  
Replace2FA_Scan
~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/Replace2FA_Scan.png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/Replace2FA_Scan.png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/aRqRQJN
      </td>
      <td>
        https://zpl.io/bzNDgl4
      </td>
    </tr>
  </table>
  
  
Replace2FA_EnterSeed
~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/Replace2FA_EnterSeed.png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/Replace2FA_EnterSeed.png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/aBEvYxm
      </td>
      <td>
        https://zpl.io/b61gZmP
      </td>
    </tr>
  </table>
  
  
Replace2FA_EnterSeed (error)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/Replace2FA_EnterSeed (error).png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/Replace2FA_EnterSeed (error).png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/V1Nq4GJ
      </td>
      <td>
        https://zpl.io/br8LYXO
      </td>
    </tr>
  </table>
  
  
Replace2FA_EnterSeed (filled)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/Replace2FA_EnterSeed (filled).png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/Replace2FA_EnterSeed (correct).png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/b61MwdN
      </td>
      <td>
        https://zpl.io/bljL8xe
      </td>
    </tr>
  </table>
  
  
Replace2FA_Review
~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/Replace2FA_Review.png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/(Token Payment) Replace2FA_Review.png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/VKPq9ZR
      </td>
      <td>
        https://zpl.io/V4eLd4Q
      </td>
    </tr>
  </table>
  
  
Replace2FA_Success
~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/Replace2FA_Success.png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/Replace2FA_Success.png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/VkG599v
      </td>
      <td>
        https://zpl.io/a3epozA
      </td>
    </tr>
  </table>
  
  
