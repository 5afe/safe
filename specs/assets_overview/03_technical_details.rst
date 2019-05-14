=========================
Technical Details
=========================

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

Common Technical Requirements
-------------------------------

The feature implementation must fulfill the technical requirements specified in
the `Common Technical Requiremets`_ unless
specifically noted in this document below.

Communication
---------------

Describe APIs and provide links to the documentation here (swagger, readthedocs, and so on).

Ethereum Node
~~~~~~~~~~~~~~~~~

- `Ethereum JSON RPC Documentation`_
- `Infura Getting Started Documentation`_
- `Solidity Contract ABI Specification`_

Requests:

- eth_getBalance_
- eth_call_

  + selector: ``balanceOf(address)`` - for ERC20 contracts

Relay Service
~~~~~~~~~~~~~~~~

- `Source code <relay_service_source>`__
- `Development API Documentation <relay_service_dev_>`__
- `Staging API Documentation <relay_service_staging_>`__
- `Production API Documentation <relay_service_prod_>`__

Requests:

- ``POST /api/v1/tokens/`` - to retrieve the list of all tokens. 

App is storing the list of tokens that are shown in the asset overview, so for each ERC20 token 
we should invoke `eth_call`_ with ERC20 contract call to get balance of the address of that token.

Note, this might be optimized request-wise with batching multiple requests if using JSON-RPC protocol
for communication with the Ethereum Node API.

.. _`Common Technical Requiremets`: ../common/technical_requirements.rst
.. _Ethereum JSON RPC Documentation: https://github.com/ethereum/wiki/wiki/JSON-RPC
.. _Infura Getting Started Documentation: https://infura.io/docs/gettingStarted/chooseaNetwork
.. _Solidity Contract ABI Specification: https://solidity.readthedocs.io/en/v0.5.2/abi-spec.html
.. _eth_getBalance: https://github.com/ethereum/wiki/wiki/JSON-RPC#eth_getbalance
.. _eth_call: https://github.com/ethereum/wiki/wiki/JSON-RPC#eth_call
.. _relay_service_source: https://github.com/gnosis/safe-relay-service/tree/develop
.. _relay_service_dev: https://safe-relay.dev.gnosisdev.com
.. _relay_service_staging: https://safe-relay.staging.gnosisdev.com
.. _relay_service_prod: https://safe-relay.gnosis.pm