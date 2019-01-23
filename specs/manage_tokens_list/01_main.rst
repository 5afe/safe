==========================================================
Manage Tokens - Selection List
==========================================================

=======  ====================  =======    ==========
 epic          title           author     created
=======  ====================  =======    ==========
58_      Token Selection List  rmeissner  23.01.2019
=======  ====================  =======    ==========

.. _58: https://github.com/gnosis/safe/issues/58

.. _Main:

#. `Main`_
#. `User Interface`_
#. `Technical Details`_

.. sectnum::
.. contents:: Table of Contents
    :local:
    :depth: 2

Problem Definition
-------------------------------

- User MUST be able to see all token supported by the Safe app
- User MUST be able to select and deselect tokens that should be displayed in the asset overview 


Outputs
------------

- Selected tokens for asset overview

Use Case Scenarios
-----------------------

Load token list
~~~~~~~~~~~~~~~~~~~~

Steps
+++++
1. The content (token list) should start loading automatically
2. Once loading is done the tokens should be displayed

Postconditions
++++++++++++++
- All available tokens should be displayed after the selected tokens.

  * It should be possible to display an unlimited number of tokens in the list (paginated list)
  * The next page of tokens should be loaded automatically when scrolling close to the end of the list
  * It should be indicated that data is loading
  
- For each token we display the details

  * Icon
  * Name
  * Symbol
  * Enabled or not

- Loaded list: https://zpl.io/aRqlmBe


Enable token from list
~~~~~~~~~~~~~~~~~~~~~~~~~~~

inherits from `Load token list`_

Steps
+++++++
3. Select token after list has been loaded

Postconditions
++++++++++++++
* Token should be displayed in asset overview


Disable token from list
~~~~~~~~~~~~~~~~~~~~~~~~~~~

inherits from `Load token list`_

Preconditions
+++++++++++++

- A token is already enabled (and displayed in the asset overview)

Steps
+++++++
3. Select token after list that is enable and disable it

Postconditions
++++++++++++++
- Token should NOT be displayed in asset overview



Could not load initial token list
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

inherits from `Load token list`_

Steps
+++++++
2. An non-blocking  error should be displayed if the list could not be loaded

Postconditions
++++++++++++++

- It should be possible to retrigger the loading of the available tokens
- All enabled tokens should still be displayed

  - It should still be possible to disable any enabled token

Could not load next page of token list
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

inherits from `Load token list`_

Steps
+++++++
3. Keep scrolling to load more results
4. An non-blocking error should be displayed if an error occurs while loading more tokens

Postconditions
++++++++++++++

- An non-blocking error should be displayed to the user that the data could not be loaded
- It should be possible to retrigger the loading of the next token page

  - We should continue loading where we left off
  - Loaded tokens should not be reloaded


.. _`User Interface`: 02_user_interface.rst
.. _`Technical Details`: 03_technical_details.rst
