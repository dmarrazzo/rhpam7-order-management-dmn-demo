Order Management DMN
=======================

Release
-----------------------

v7.5 aligned to Red Hat Decision Manager and Red Hat Process Automation Manager v 7.5
v7.4.1 aligned to Red Hat Decision Manager and Red Hat Process Automation Manager v 7.4.1

Description
-----------------------

This is a sample decision designed to be consumed by the Order Management Process Demo.
The goal of the decision is to approve an order based on its features.
The logic is pretty straightforward:

- `target price`: is the desired price by the requester (purchase department)
- `price`: is the best offer from the suppliers
- the order can be automatically approved when the `price` is lower than the `target price` increased by a tolerance factor.
- the tolerance factor is computed by a Business Knowledge Model (`price tolerance`) implemented as a decision table
- the decision table produce a number between 1.1 and 1.25 based on the urgency and the `category` of the `order`

Test the decision
-----------------------

Open the test scenario `order-test` and press the play icon:

- all test are passed

In the first row change the target price to `900` and run again the test:

- the first scenario fails because `1099` is not in tolerance range when the target price is `900`