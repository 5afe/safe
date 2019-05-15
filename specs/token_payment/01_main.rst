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
    :depth: 2


1 sentence: What is this feature about?
---------------------------------------

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

<Screen Name>
~~~~~~~~~~~~~

.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/ScreenName.png" width="320px"/>
      </td>
      <td>
        <img src="screens/ios/(Token Payment) Onboarding_CreationFeeIntro.png" width="320px"/>
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


[MISSING] <Screen Name> - <Screen Variation>
+++++

Screen description explaining when this screen variation happening.
What are we trying to achieve with this screen?
This is the explanation for UI designer.
