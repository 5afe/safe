==========================================================
Token payment
==========================================================

=====  =============  =========  ==========
epic       title       author     created
=====  =============  =========  ==========
`89`_  Token_payment  tschubotz  2019-05-15
=====  =============  =========  ==========

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

This feature affects the following flows:
- Safe creation
- Send funds 
- Connect browser extension
- Replace browser extension
- Replace recovery phrase
- Recover Safe

The smart contracts and the backend are already ready for this change. We "just" have to incorporate this into the frontends now.


Screens - Create Safe
---------------------

Onboarding_CreationFeeIntro
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/ScreenName.png" width="240"/>
      </td>
      <td>
        <img src="screens/ios/(Token Payment) Onboarding_CreationFeeIntro.png" width="240"/>
      </td>
    </tr>
    <tr>
      <td>
        https://example.org/
      </td>
      <td>
        https://zpl.io/adz58gl
      </td>
    </tr>
  </table>

- Tapping the question mark brings up the info modal.


Onboarding_CreationFeeIntro (modal)
+++++++++++++++++++++++++++++++++++

.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/ScreenName.png" width="240"/>
      </td>
      <td>
        <img src="screens/ios/(Token Payment) Onboarding_CreationFeeIntro (modal).png" width="240"/>
      </td>
    </tr>
    <tr>
      <td>
        https://example.org/
      </td>
      <td>
        https://zpl.io/Vx0e5jW
      </td>
    </tr>
  </table>


Onboarding_CreationFeeIntro (OWL selected)
++++++++++++++++++++++++++++++++++++++++++

.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/ScreenName.png" width="240"/>
      </td>
      <td>
        <img src="screens/ios/(Token Payment) Onboarding_CreationFeeIntro (OWL selected).png" width="240"/>
      </td>
    </tr>
    <tr>
      <td>
        https://example.org/
      </td>
      <td>
        https://zpl.io/b64EYYm
      </td>
    </tr>
  </table>


Onboarding_PaymentMethod
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/ScreenName.png" width="240"/>
      </td>
      <td>
        <img src="screens/ios/(Token Payment) Onboarding_PaymentMethod.png" width="240"/>
      </td>
    </tr>
    <tr>
      <td>
        https://example.org/
      </td>
      <td>
        https://zpl.io/amdNlJr
      </td>
    </tr>
  </table>

- User has to tap "Pay with xx" to get back to the previous screen.


Onboarding_PaymentMethod (OWL selected)
+++++++++++++++++++++++++++++++++++++++

.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/ScreenName.png" width="240"/>
      </td>
      <td>
        <img src="screens/ios/(Token Payment) Onboarding_PaymentMethod (OWL selected).png" width="240"/>
      </td>
    </tr>
    <tr>
      <td>
        https://example.org/
      </td>
      <td>
        https://zpl.io/brv6zzW
      </td>
    </tr>
  </table>


Onboarding_CreationFee (token payment)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/ScreenName.png" width="240"/>
      </td>
      <td>
        <img src="screens/ios/(Token Payment) Onboarding_CreationFee (token payment).png" width="240"/>
      </td>
    </tr>
    <tr>
      <td>
        https://example.org/
      </td>
      <td>
        https://zpl.io/VQv8ggk
      </td>
    </tr>
  </table>

- Tapping the address copies it.
- Tapping the share button brings up the operating system's share sheet.
- Tapping the question mark bring up the info modal.


Onboarding_CreationFee (address copied)
+++++++++++++++++++++++++++++++++++++++

.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/ScreenName.png" width="240"/>
      </td>
      <td>
        <img src="screens/ios/(Token Payment) Onboarding_CreationFee (address copied).png" width="240"/>
      </td>
    </tr>
    <tr>
      <td>
        https://example.org/
      </td>
      <td>
        https://zpl.io/aRx8QQK
      </td>
    </tr>
  </table>


Onboarding_CreationFee (action sheet)
+++++++++++++++++++++++++++++++++++++++

.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/ScreenName.png" width="240"/>
      </td>
      <td>
        <img src="screens/ios/(Token Payment) Onboarding_CreationFee (action sheet).png" width="240"/>
      </td>
    </tr>
    <tr>
      <td>
        https://example.org/
      </td>
      <td>
        https://zpl.io/aRx8QQK
      </td>
    </tr>
  </table>


Onboarding_CreationFee (modal)
+++++++++++++++++++++++++++++++++++++++

.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/ScreenName.png" width="240"/>
      </td>
      <td>
        <img src="screens/ios/(Token Payment) Onboarding_CreationFee (modal).png" width="240"/>
      </td>
    </tr>
    <tr>
      <td>
        https://example.org/
      </td>
      <td>
        https://zpl.io/2j5xBBr
      </td>
    </tr>
  </table>


Onboarding_CreationFee (cancel warning)
+++++++++++++++++++++++++++++++++++++++

.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/ScreenName.png" width="240"/>
      </td>
      <td>
        <img src="screens/ios/(Token Payment) Onboarding_CreationFee (cancel warning).png" width="240"/>
      </td>
    </tr>
    <tr>
      <td>
        https://example.org/
      </td>
      <td>
        https://zpl.io/adz588E
      </td>
    </tr>
  </table>


Onboarding_CreationFee (insufficient funds)
+++++++++++++++++++++++++++++++++++++++++++

.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/ScreenName.png" width="240"/>
      </td>
      <td>
        <img src="screens/ios/(Token Payment) Onboarding_CreationFee (insufficient funds).png" width="240"/>
      </td>
    </tr>
    <tr>
      <td>
        https://example.org/
      </td>
      <td>
        https://zpl.io/V4ex3kJ
      </td>
    </tr>
  </table>