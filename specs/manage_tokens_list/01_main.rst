==========================================================
Manage Tokens - Selection List
==========================================================

=======  ====================  =======  ==========
 epic          title           author   created
=======  ====================  =======  ==========
58_      Token Selection List  Richard  23.01.2019
=======  ====================  =======  ==========

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

Complete token list
~~~~~~~~~~~~~~~~~~~~

As an user I want to be able to see all tokens that I have enabled and that are available.


* The content (token list) should start loading automatically
* All selected tokens should be displayed alphabetically in a separate section before all available tokens
* All available tokens should be displayed after the selected tokens.
  * It should be possible to display an unlimited number of tokens in the list (paginated list)
  * The next page of tokens should be loaded automatically when scrolling close to the end of the list
  * It should be indicated that data is loading
* For each token we display the details
  * Icon
  * Name
  * Symbol
  * Enabled or not
* It should be possible to select or deselect a token
  * Selecting a token should add it to the section of selected tokens
  * Deselecting a token should remove  it from the section of selected tokens

* Loaded list: https://zpl.io/aRqlmBe

Could not load initial token list
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

As a user I want to be able to see all tokens that I have enabled even if the available tokens could not be loaded.
  
* An non-blocking error should be displayed to the user that the data could not be loaded
* It should be possible to retrigger the loading of the available tokens
* All enabled tokens should still be displayed
  * It should still be possible to deselect a token
* Based on `Complete token list`_

Could not load next page of token list
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

As a user I want to be able to continue loading pages after a loading error occured.
  
* An non-blocking error should be displayed to the user that the data could not be loaded
* It should be possible to retrigger the loading of the next token page
  * We should continue loading where we left off
  * Loaded tokens should not be reloaded
* Based on `Complete token list`_


.. _`User Interface`: 02_user_interface.rst
.. _`Technical Details`: 03_technical_details.rst
