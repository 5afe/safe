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
    SPEC_REPO = gnosis/safe

=======  ==================  ======  ==========
 epic          title         author   created
=======  ==================  ======  ==========
`EPIC`_  SPECIFICATION_NAME  AUTHOR  CREATED_AT
=======  ==================  ======  ==========

.. _EPIC: SPEC_REPO#EPIC

.. _Main:

==================
SPECIFICATION_NAME
==================

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

4.1. Happy Case
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


4.2. Edge Case Scenario
~~~~~~~~~~~~~~~~~~~~~~~~~

Inherits from the `4.1. Happy Case`_

.. Inherits from
    means that this scenario takes all the preconditions,
    steps and postconditions from another use case and possibly extends
    or overrides them with new values.

Preconditions
+++++++++++++

.. if preconditions are all the same - remove this section completely.
.. if preconditions are the same AND there's something additional, or something is missing
.. then explicitly mention all preconditions as wel.

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


4.3. Remember loading state scenario
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Inherits from the `4.1. Happy Case`_

Steps
+++++

2. Something is loading

4.5. Remember error situations
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Inherits from the `4.1. Happy Case`_

Steps
+++++

3. Error happens. Display error to the user


.. _`iOS`: 02_user_interface_ios.rst
.. _`Android`: 02_user_interface_android.rst
.. _`Chrome`: 02_user_interface_chrome.rst
.. _`External Communication`: 03_external_communication.rst
.. _Other: 04_other.rst
