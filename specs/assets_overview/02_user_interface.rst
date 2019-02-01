=====================
User interface
=====================

=====  ===============  =========  ==========
epic        title        author     created
=====  ===============  =========  ==========
`64`_  Assets overview  tschubotz  2019-01-22
=====  ===============  =========  ==========

.. _64: https://github.com/gnosis/safe/issues/64

.. sectnum::
.. contents:: Table of Contents
    :local:
    :depth: 2

Assets overview screen
-------------------------

- Tapping the identicon or the address brings up the receive screen.
- Tapping "Add token" brings up the manage tokens screen.
- Tapping an asset will start the send transaction flow.
- All amounts are formatted as `short amount`_

.. _`short amount`: ../common/format_amounts.rst#short-amount

.. raw:: html

   <img src="screens/android/assets_overview.png" width="320px"/>

.. raw:: html

   <img src="screens/ios/assets_overview.png" width="320px"/>

* Zeplin link Android https://zpl.io/V0EKY5l
* Zeplin link iOS https://zpl.io/a75pdpK


MISSING: Assets overview screen - loading
------------------------------------------

- When balances are loaded or reloaded.


MISSING: Assets overview screen - No internet
---------------------------------------------

- When there is no internet connection but the balances have been loaded before.


MISSING: Assets overview screen - No internet first time
--------------------------------------------------------

- When there is no internet for the very first time loading balances.

.. _`Technical details`: 03_user_interface.rst