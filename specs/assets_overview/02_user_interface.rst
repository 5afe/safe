=====================
User interface
=====================

=====  ===============  =========  ==========
epic        title        author     created
=====  ===============  =========  ==========
`64`_  Assets overview  tschubotz  2019-01-22
=====  ===============  =========  ==========

.. _64: https://github.com/gnosis/safe/issues/64

.. _`User interface`:


#. `Main`_
#. `User interface`_
#. `Technical Details`_

.. sectnum::
.. contents:: Table of Contents
    :local:
    :depth: 2

Assets overview screen
-------------------------

- Tapping the identicon or the address brings up the receive screen.
- Tapping "Add token" brings up the manage tokens screen.
- Amounts should be abbreviated / truncated as follows:
    - Cut off after the 5th decimal, no matter how many decimals there
      are: 0.12345ETH
    - Remove trailing zeroes, i.e. display 0.10000ETH as 0.1ETH.
    - Use the 5 decimals up until 999.99999ETH
    - Use 1 decimal less from 1,000.0001 until 9,999.9999ETH (Use
      comma as thousands-separator)
    - Use 1 decimal less from 10,000.001 until 99,999.999ETH
    - Use 1 decimal less from 100,000.01 until 999,999.99ETH
    - Use 1 decimal less from 1,000,000.1 until 9,999,999.9ETH
    - From 10,000,000ETH No Decimals until 99,999,999ETH
    - Then Use 10.001M until 999.999M
    - Then 1.001B until 999.999B
    - Then 1.001T until 999.999T
    - Then just > 1000T

This format has been dicussed on Github_.

.. _Github: https://github.com/gnosis/safe/issues/62#issuecomment-455240793

.. raw:: html

   <img src="screens/android/assets_overview.png" width="320px"/>

.. raw:: html

   <img src="screens/ios/assets_overview.png" width="320px"/>

* Zeplin link Android https://zpl.io/V0EKY5l
* Zeplin link iOS https://zpl.io/a75pdpK
