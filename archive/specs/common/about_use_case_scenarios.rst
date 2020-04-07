============================
About Use Case Scenarios
============================

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

