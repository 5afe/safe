=====================
User interface
=====================

=====  ================  =========  ==========
epic          title       author     created
=====  ================  =========  ==========
`71`_  Transaction List  tschubotz  2019-01-22
=====  ================  =========  ==========

.. _71: https://github.com/gnosis/safe/issues/71

.. sectnum::
.. contents:: Table of Contents
    :local:
    :depth: 2

Transaction list
------------------

**Sections:**

- "Pending" for pending txs
- "Today" for all txs that happened today, i.e. on the same calendar day like the current day.
- "Yesterday" for all txs that happened yesterday, i.e. the previous calendar day.
- "<month day>" For all previous txs that happened this year. We use the format depending on the user's locale settings, i.e. e.g. "Feb 12"
- "<month day, year>" for all previous txs of the previous year. We use the format depending on the user's locale settings, i.e. e.g. "Dec 31, 2018"

**Time indicator on the tx row**

- If tx happened on current calendar day (today):

  - "Just now" if < 1min ago
  - "x minutes ago" if >= 1min & < 1h ago
  - "x hours ago" if >= 1h & < 24h ago

- If tx happened before today: Please put the time (hours + minutes only, not seconds), depending on the selected locale.

**Types:**

- Incoming ETH
- Incoming ERC20 token
- Outgoing ETH
- Outgoing ERC20 token
- Data
- Settings change

**States:**

- Pending
- Successful
- Failed


.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/transaction_list.png" width="320px"/>
      </td>
      <td>
        <img src="screens/ios/transaction_list.png" width="320px"/>
      </td>
    </tr>
  </table>


* Zeplin link Android: https://zpl.io/bAB7q36
* Zeplin link iOS: https://zpl.io/aR1x7Je


Transaction list - Empty
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/transaction_list_empty.png" width="320px"/>
      </td>
      <td>
        <img src="screens/ios/transaction_list_empty.png" width="320px"/>
      </td>
    </tr>
  </table>


* Zeplin link Android: https://zpl.io/bAB7q6p
* Zeplin link iOS: https://zpl.io/VqKRpd4

Transaction details - Outgoing funds
-------------------------------------

.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/transaction_details_funds_outgoing.png" width="320px"/>
      </td>
      <td>
        <img src="screens/ios/transaction_details_funds_outgoing.png" width="320px"/>
      </td>
    </tr>
  </table>


* Zeplin link Android: https://zpl.io/agnwKgQ
* Zeplin link iOS: https://zpl.io/aByYr4k

Transaction details - Incoming funds
-------------------------------------

.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/transaction_details_funds_incoming.png" width="320px"/>
      </td>
      <td>
        <img src="screens/ios/transaction_details_funds_incoming.png" width="320px"/>
      </td>
    </tr>
  </table>


* Zeplin link Android: https://zpl.io/awrvZy1
* Zeplin link iOS: https://zpl.io/2jQMnOq

Transaction details - Failed
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/transaction_details_failed.png" width="320px"/>
      </td>
      <td>
        <img src="screens/ios/transaction_details_failed.png" width="320px"/>
      </td>
    </tr>
  </table>


* Zeplin link Android: https://zpl.io/boKNxEg
* Zeplin link iOS: https://zpl.io/2v769Dv


Transaction details - Pending
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/transaction_details_pending.png" width="320px"/>
      </td>
      <td>
        <img src="screens/ios/transaction_details_pending.png" width="320px"/>
      </td>
    </tr>
  </table>


* Zeplin link Android: https://zpl.io/2v7Oo7P
* Zeplin link iOS: https://zpl.io/aNPDJYN


Transaction details - Data
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/transaction_details_data.png" width="320px"/>
      </td>
      <td>
        <img src="screens/ios/transaction_details_data.png" width="320px"/>
      </td>
    </tr>
  </table>


* Zeplin link Android: https://zpl.io/bABQqWn
* Zeplin link iOS: https://zpl.io/VkGXRLq


Transaction details - Settings change
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. raw:: html

  <table>
    <tr>
      <td>
        <img src="screens/android/transaction_details_settings_change.png" width="320px"/>
      </td>
      <td>
        <img src="screens/ios/transaction_details_settings_change.png" width="320px"/>
      </td>
    </tr>
  </table>


* Zeplin link Android: https://zpl.io/boBjO1X
* Zeplin link iOS: https://zpl.io/aXwd06E
