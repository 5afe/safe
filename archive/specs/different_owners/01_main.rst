==========================================================
Different owners
==========================================================

=======  ==================  ======  ==========
 epic          title         author   created
=======  ==================  ======  ==========
`143`_  Different_owners  tschubotz  2019-03-27
=======  ==================  ======  ==========

.. _143: https://github.com/gnosis/safe/issues/143

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

Currently, on a single device, the same address is used for all Safes it is connected to. So it is easy to conclude that they all belong to the same account. This is not desired for privacy reasons.

Inputs
-----------

- Creating or restoring several new Safes on the same device.

Outputs
------------

- Safes that can be managed from the same device but do not share an owner address.

Use Case Scenarios
-----------------------

Happy Case - Creating a Safe
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Preconditions
+++++++++++++

- App has been set up with a password.
- There is a Safe existing on the device

Steps
+++++

1. Go through the Safe creation flow

2. Wait for the Safe to be created on the blockchain.

Postconditions
++++++++++++++

- New Safe is created on the blockchain.
- New Safe can be managed from the device.
- Previously created Safe and new Safe do not share an owner.


Happy Case - Restoring a Safe
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Preconditions
+++++++++++++

- App has been set up with a password.
- There is a Safe existing on the device

Steps
+++++

1. Go through the Safe restore flow

2. Wait for the restore transaction to finish.

Postconditions
++++++++++++++

- Restored Safe can be managed from the device.
- Previously created Safe and restored Safe do not share an owner.