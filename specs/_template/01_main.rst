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

.. Template information:
    SPECIFICATION_NAME = name of the specification (title)
    EPIC = epic issue number
    AUTHOR = your name
    CREATED_AT = YYYY-MM-dd

.. Please replace the strings below with the values that you want to put in in all of the rst files of the specification.

==========================================================
SPECIFICATION_NAME
==========================================================

=======  ==================  ======  ==========
 epic          title         author   created
=======  ==================  ======  ==========
`EPIC`_  SPECIFICATION_NAME  AUTHOR  CREATED_AT
=======  ==================  ======  ==========

.. _EPIC: gnosis/safe#EPIC

.. _Main:


#. `Main`_
#. `User Interface`_
#. `Technical Details`_

.. sectnum::
.. contents:: Table of Contents
    :local:

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

Happy Case
~~~~~~~~~~~~~~~~~

.. _happy_case_preconditions:

Preconditions
+++++++++++++

* Things that are expected to be true and required for the steps below
* This are the things that needed for the functionality to work properly

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

<Remember to specirfy error situations>
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Inherits from the `Happy Case`_

Steps
+++++

3. Error happens. Display error to the user


.. _`User Interface`: 02_user_interface.rst
.. _`External Communication`: 03_external_communication.rst
.. _`Technical Details`: 04_technical_details.rst
