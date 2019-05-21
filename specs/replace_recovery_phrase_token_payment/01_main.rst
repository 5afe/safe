==========================================================
Replace recovery phrase - Token payment
==========================================================

=====  =============================================  =========  ==========
epic                       title                       author     created
=====  =============================================  =========  ==========
`89`_  Replace recovery phrase - Token payment  tschubotz  2019-05-21
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
- Replace browser extension 
- Replace recovery phrase 👈 this spec
- Recover Safe 
- Menu 

The payment method is set per Safe but can be changed before making a transaction and also via the menu. 

The smart contracts and the backend are already ready for this change. We "just" have to incorporate this into the frontends now.


Screens
---------------------

[TOKEN PAYMENT] ReplaceSeed
~~~~~~~~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/[TOKEN PAYMENT] ReplaceSeed.png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/(Token payment) ReplaceSeed.png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/a87omN4
      </td>
      <td>
        https://zpl.io/aBRJlNL
      </td>
    </tr>
  </table>
  
  
[TOKEN PAYMENT] ReplaceSeed (insufficient funds)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/[TOKEN PAYMENT] ReplaceSeed (insufficient funds).png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/(Token payment) ReplaceSeed (insufficient funds).png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/VKDZ1o6
      </td>
      <td>
        https://zpl.io/a878x8J
      </td>
    </tr>
  </table>
  
  
ReplaceSeed_SeedIntro
~~~~~~~~~~~~~~~~~~~~~

- The entire flow off writing and confirming the phrase is left out. It should be the same like during onboarding.
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/ReplaceSeed_SeedIntro.png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/ReplaceSeed_SeedIntro.png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/a7OnPeK
      </td>
      <td>
        https://zpl.io/am5qvxe
      </td>
    </tr>
  </table>
  
  
ReplaceSeed_Review
~~~~~~~~~~~~~~~~~~

- 2FA versions of this screen are left out.
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/ReplaceSeed_Review.png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/(Token payment) ReplaceSeed_Review.png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/bzNvWvM
      </td>
      <td>
        https://zpl.io/aX3Ao9M
      </td>
    </tr>
  </table>
  
  
ReplaceSeed_Success
~~~~~~~~~~~~~~~~~~~
            
.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/ReplaceSeed_Success.png" width="240px"/>
      </td>
      <td>
        <img src="screens/ios/ReplaceSeed_Success.png" width="240px"/>
      </td>
    </tr>
    <tr>
      <td>
        https://zpl.io/2v7z3AY
      </td>
      <td>
        https://zpl.io/aR137D0
      </td>
    </tr>
  </table>
