.. Getting Started

.. Installation and IDE
    To make your editing easier, we recommend to use VSCode editor with the extensions:
    - reStructuredText (https://marketplace.visualstudio.com/items?itemName=lextudio.restructuredtext)
    - Table Formatter (https://marketplace.visualstudio.com/items?itemName=shuworks.vscode-table-formatter)
.. 
    The prerequisites for those extensions are python3 and doc8 packcages. Install instructions are here:
    - https://docs.python-guide.org/starting/install3/osx/ (install python and pip, nothing else)
    - After this, use pip3 to install other prerequisites below:
    - https://docs.restructuredtext.net/articles/prerequisites.html

.. rst syntax quick reference
    If you are used to markdown, then rst is going to be a bit strange at first.
    rst is more powerful than markdown, and it is standardised.

.. Where to get more info
    - http://docutils.sourceforge.net/docs/user/rst/quickref.html
    - http://docutils.sourceforge.net/docs/user/rst/quickstart.html
    - http://docutils.sourceforge.net/docs/ref/rst/restructuredtext.html
    - http://docutils.sourceforge.net/docs/ref/rst/directives.html

.. <------- comments start with 2 dots

.. Document Name
    Note that the lines must be at least as long as the text
    ====================== 
    This is document name
    ======================

.. Headers
    Just underline with any symbol like = or - or + or ~ or `
    Be consistent - different symbols are taken as different header levels.
    Examples:
..
    1st level header
    ==================
..
    2nd level header
    ------------------
..
    3rd level header
    ~~~~~~~~~~~~~~~~~~~
..
    4th level header
    ++++++++++++++++++

.. Lists
    1. first item
    2. second item
    #. auto-generated item number

.. Unordered lists
    * first level
    <blank line>
        - second level
    <blank line>
        + third level

.. Code
    .. code:: <language (optional)>
    <blank line>
        this is going to be code

.. Links
    `This is link text`_ <-------- undersocre at the end
    .. _`This is  link text`: https://example.org <------------- this is link definition
    .. anchor: <---------- this is anchor to the text below it
    `anchor`_ <----------- this is link to the anchor
    `Some text <anchor_>`_ <----- text is different from the anchor name
    We put all link definitions (except from the page info header table) to the end of the document.

.. This is a document header
    It links to the epic ticket number, and provides document metadata

.. Template information:
    SPECIFICATION_NAME = name of the specification (title)
    EPIC = epic issue number
    AUTHOR = your name
    CREATED_AT = YYYY-MM-dd

.. Please replace the strings below with the values that you want to put in in all of the rst files of the specification.

=====  =============  =================  ==========
epic       title           author         created
=====  =============  =================  ==========
`67`_  Create Safe    Dmitry Bespalov     2019-01-18
=====  =============  =================  ==========

.. _67: gnosis/safe#67

.. _Main:

=============
Create Safe
=============

1. `Main`_
2. User Interface

   1. `Android`_
   2. `Chrome`_
   3. `iOS`_

3. `External Communication`_
4. Other_


.. contents:: Table of Contents

1. Problem Definition
---------------------

* List your problem definition here

2. Inputs
-----------

What inputs are needed to solve the problem? 

* User input
* Network-fetched information
* Existing information in the database

3. Outputs
------------

What is output from the functionality that is specified?

* New database data
* Error messages
* Some side-effect to other systems

4. Use Case Scenarios
-----------------------

You can put general information or context for all use case scenarios here.
Feel free to remove the use case explanation below.

Every use case scenario consists of preconditions – prerequisites
and assumptions, steps - numbered sequence of steps of the scenario,
from the user's perspective, and postconditions - results and
assumptions that must hold after the steps finished.

A use case can *inherit* another use case. That means that
inheriting use case takes all of the preconditions, steps, and postconditions
from the inhertied use case.

The inheriting (child) use case
can override (replace) any step or precondition in the parent
use case. The overriden steps in child should match the step number
in parent. The child use case may introduce sub-steps, in that case
numbering is starts with dot, for example "3.1", "3.2" gives more
details about step "3" of a parent use case.

4.1. Basic Setup
~~~~~~~~~~~~~~~~~

.. _happy_case_preconditions:

Preconditions
+++++++++++++

* Password setup complete.
* App is unlocked.
* User can transfer enough funds to the to-be-created safe to cover for network fees.
* Internet connection.
* Gnosis backend services are up and running.

.. _happy_case_steps:

Steps
+++++

1. Select "Create Safe" action. Guidelines are shown. 

2. Select "Next" action.

3. Select "Skip and setup later" to skip browser extension setup.
   The recovery phrase guidelines are shown.

4. Select "Next"

5. Note the recovery phrase. Proceed to the next step.

6. Confirm the recovery phrase. Submit your confirmation.
   Confirmation is done by providing missing words from the phrase.

7. Copy safe address.

8. Send required minimum transfer to the safe address from an external account.
   Wait for the transfer to complete.
   The app will indicate when it detects new transfer on the safe account.
   After app detected incoming transfer and it was enough, the cancellation is not possible.

9. Wait for the safe to be created.

10. Main screen opens.

.. _happy_case_postconditions:

Postconditions
++++++++++++++

* New safe have been created in the blockchain.
* Safe balance is what remains of the transferred funds after deducting fee for safe creation.
* Browser extension is not connected.

4.2. Connecting Browser Extension
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Inherits from the `4.1. Basic Setup`_

.. Inherits from
    means that this scenario takes all the preconditions,
    steps and postconditions from another use case and possibly extends
    or overrides them with new values.

Steps
+++++

.. step number overrides the step with the same number in the parent (inherited from) scenario.

3. 1. Select "Scan" action. The camera screen opens.

   2. Point the camera to the extension's QR code.
      The message displayed that the extension connected successfully.

   3. Wait until the camera closed and the app proceeds to the next step.

Postconditions
++++++++++++++

* New safe have been created in the blockchain.
* Safe balance is what remains of the transferred funds after deducting fee for safe creation.
* Browser extension is connected.


4.3. Cancellation.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Inherits from the `4.1. Basic Setup`_


Preconditions
++++++++++++++++

* Same as in the parent case.
* User has not transferred the fees to the safe address yet, OR
* User has transferred the funds but the app has not detected the incoming transfer.

Steps
+++++

7. Select "Cancel". Confirmation dialog appears.

8. Select "Cancel" to confirm the cancellation.

Postconditions
++++++++++++++++

* Safe is not created in the blockchain.
* App goes back to where it started before entering the "create safe" flow.


4.5. Failed to Connect Extension
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Inherits from the `4.1. Basic Setup`_


.. TODO

4.6. Wrong Recovery Phrase Confirmation
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. TODO

4.7. Network Unavailable
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. TODO

4.8. Insufficient funds
~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. TODO

4.9. Failed to create safe
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. TODO

4.10. Monitoring Creation Progress In Browser
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. TODO

.. _`iOS`: 02_user_interface_ios.rst
.. _`Android`: 02_user_interface_android.rst
.. _`Chrome`: 02_user_interface_chrome.rst
.. _`External Communication`: 03_external_communication.rst
.. _Other: 04_other.rst
