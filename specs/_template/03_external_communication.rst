=======  ==================  ======  ==========
 epic          title         author   created
=======  ==================  ======  ==========
`EPIC`_  SPECIFICATION_NAME  AUTHOR  CREATED_AT
=======  ==================  ======  ==========

.. _EPIC: gnosis/safe#EPIC

=========================
External Communication
=========================

.. contents:: Table of Contents

1. Service A
--------------------

**Protocol:** JSON-RPC via REST

- `Put your link to documentation here`_
- `More links`_

1.1. Operation Name
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

* **Method:** method name
* **Parameters:**

  - ``parameter_name`` parameter description
  - ``parameter_name`` parameter description

* **Returns:** ``return_value`` description

2. REST Service B
---------------------------

**Protocol:** REST with JSON payloads

- `Source code link`_
- `API documentation or swagger link`_
- `Other helpful links`_

2.1. Operation name
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

* **Endpoint:** ``POST /api/v1/your/endpoint``
* **JSON Payload:**

.. code::

    {
        "key": {
            "name": "<value>", // description or format explanation
        }
    }

* - **ATTENTION:** Something important to mention here
  - Point A
  - Point B

* **Responses:**

  - 200 - OK, payload:

.. code::

    {
        "key": [
            "<string>", “<string>" // value descriptions
        ]
    }

* - 400 - invalid request

    + When does it happen?
    + What could be invalid?

  - 500 - Internal server error

    + When would it happen?
    + What could it be?

.. _`Put your link to documentation here`: https://example.org/
.. _`More links`: https://example.org/
.. _`Source code link`: https://example.org/
.. _`API documentation or swagger link`: https://example.org/
.. _`Other helpful links`: https://example.org/
