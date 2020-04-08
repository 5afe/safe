=====================
How to format amounts
=====================

This doc specifies the different types of formatting amounts inside the Safe apps.


Full amount
-----------

Used when the entire amount matters. 

- No truncation, always show all numbers.
- Thousands and decimal separators are used according to user's locale.


Short amount
-------------------

Used in cases where horizontal screen real estate is limited and the complete amount is not super important. 

- Cut off after the 5th decimal, no matter how many decimals there are: 0.12345
- Remove trailing zeroes, i.e. display 0.10000 as 0.1.
- Use the 5 decimals up until 999.99999
- Use 1 decimal less from 1,000.0001 until 9,999.9999 (Use comma as thousands-separator)
- Use 1 decimal less from 10,000.001 until 99,999.999
- Use 1 decimal less from 100,000.01 until 999,999.99
- Use 1 decimal less from 1,000,000.1 until 9,999,999.9
- From 10,000,000 No Decimals until 99,999,999
- Then Use 10.001M until 999.999M
- Then 1.001B until 999.999B
- Then 1.001T until 999.999T
- Then just > 1000T
- Thousands and decimal separators are used according to user's locale.
- k, M, B, T should be localized.

This format has been dicussed on Github_.

.. _Github: https://github.com/gnosis/safe/issues/62#issuecomment-455240793
