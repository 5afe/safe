.. Getting Started
.. Installation and IDE
    To make your editing easier, we recommend to use VSCode editor with the extensions:
    - reStructuredText (https://marketplace.visualstudio.com/items?itemName=lextudio.restructuredtext)
    - Table Formatter (https://marketplace.visualstudio.com/items?itemName=shuworks.vscode-table-formatter)
.. The prerequisites for those extensions are python3 and doc8 packcages. Install instructions are here:
    - https://docs.python-guide.org/starting/install3/osx/ (install python and pip, nothing else)
    - After this, use pip3 to install other prerequisites below:
    - https://docs.restructuredtext.net/articles/prerequisites.html
.. Where to get more info
    - http://docutils.sourceforge.net/docs/user/rst/quickref.html
    - http://docutils.sourceforge.net/docs/user/rst/quickstart.html
    - http://docutils.sourceforge.net/docs/ref/rst/restructuredtext.html
    - http://docutils.sourceforge.net/docs/ref/rst/directives.html

==========================================================
SPECIFICATION_NAME
==========================================================

.. ==================== NOTE ===============================
.. You can search and replace the EPIC, SPECIFICATION_NAME, 
.. AUTHOR and CREATED_AT
.. So that the header information is updated in this doc. 
.. Do the same in other specification doc headers.
.. =========================================================

=======  ==================  ======  ==========
 epic          title         author   created
=======  ==================  ======  ==========
`EPIC`_  SPECIFICATION_NAME  AUTHOR  CREATED_AT
=======  ==================  ======  ==========

.. _EPIC: https://github.com/gnosis/safe/issues/EPIC

.. _Main:


#. `Main`_
#. `User Interface`_
#. `Technical Details`_

.. sectnum::
.. contents:: Table of Contents
    :local:
    :depth: 2

Please specify problem definition, inputs, outputs and use cases in this document.

Please remove all unrelated sections to keep the document easy to read and maintain.

Problem Definition
-------------------------------

* List your problem definition here

Inputs
-----------

What inputs are needed to solve the problem? Specify the requirements for them here

* User input
* Network-fetched information
* Existing information in the database

Outputs
------------

What is output from the functionality that is specified? Specify the requirements here.

* New database data
* Error messages
* Some side-effect to other systems

Use Case Scenarios
-----------------------

You can put general information or context for all use case scenarios here.
Feel free to remove the use case explanation below.

See more in `About Use Case Scenarios`_.

Happy Case
~~~~~~~~~~~~~~~~~

.. _happy_case_preconditions:

Preconditions
+++++++++++++

* Things that are expected to be true and required for the steps below
* This are the things that needed for the functionality to work properly
* You may include the place where scenario starts here or mention it in the Steps section.

.. _happy_case_steps:

Steps
+++++

1. <Open something>

2. Select "X" action. Something opens.

.. you can reference some steps in other scenarios, when needed:

.. _happy_case_step_3:

3. Type in "abcd". and so on


.. _happy_case_postconditions:

Postconditions
++++++++++++++

* Changes to the database, to user interface
* Changes to the backend systems' databases
* Changes in the smart contracts and so on.


<Extension Of Happy Case Scenario>
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Inherits from the `Happy Case`_

.. Inherits from
    means that this scenario takes all the preconditions,
    steps and postconditions from another use case and possibly extends
    or overrides them with new values.

Preconditions
+++++++++++++

.. if preconditions are all the same - remove this section completely.
.. if preconditions are the same AND there's something additional, or something is missing
.. then explicitly mention all preconditions as well.

* Precondition text

Steps
+++++

.. step number overrides the step with the same number in the parent (inherited from) scenario.

3. 1. Do something else instead. Something else happening.

Postconditions
++++++++++++++

.. delete the postconditions section if they are the same as in parent scenario
.. otherwise, list all postconditions here.

* Some other postcondition


<Remember to specify loading state scenario>
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Inherits from the `Happy Case`_

Steps
+++++

2. Something is loading

<Remember to specify error situations>
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Inherits from the `Happy Case`_

Steps
+++++

3. Error happens. Display error to the user


.. _`User Interface`: 02_user_interface.rst
.. _`Technical Details`: 03_technical_details.rst
.. _`About Use Case Scenarios`: ../common/about_use_case_scenarios.rst
