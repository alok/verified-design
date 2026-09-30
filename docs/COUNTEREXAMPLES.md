# Counterexamples and required diagnoses

Each case below is a requirement for the proposed library. Outcomes are relative to the stated model. None is a reported result of implemented software.

| Candidate or change | Why a naive contract fails | Required response |
| --- | --- | --- |
| Exactly square internal pocket; only positive-radius cylindrical end-mill sweeps permitted | A swept disk rounds the interior corner in this restricted operation family | Request a fillet/tolerance change, another supported operation, or prove restricted infeasibility |
| Valid enclosed cavity in a sealed solid; tool must enter from outside and subtraction is the only process | The specified tool has no modeled access route to the material to remove | Missing accessibility witness; CAD validity is insufficient |
| Tool fits a narrow deep slot but its holder reaches the walls | Tool-tip collision tests omit the complete assembly | Check shank, holder, and every modeled moving component over the whole motion |
| Two tool poses are reachable but every proposed connecting trajectory crosses a joint limit | Pointwise inverse kinematics does not supply an admissible path | Require a continuous branch-consistent joint trajectory |
| Two collision-free sampled poses with a collision between them | Samples omit intermediate states | Supply a continuous bound or return unknown |
| Contour cut frees a part that was providing its own support | Final volume is plausible but the process loses restraint | Check intermediate stock/support state and a retention/release operation |
| A Boolean union of independently witnessed parts | Witnesses may use incompatible stocks, tools, or setups | Treat the union as a candidate until a compositional construction is checked |
| Scale a part to half size while keeping the cutter | Tool radius and feature clearance no longer scale together | Recheck or construct a new witness |
| Swap to another tool with the same catalog label | Size, holder, wear, or identity may differ | Bind the witness to the tool model and its evidence |
| Exact-predicate test performed on a previously rounded intersection point | An exact decision about the rounded object need not decide the intended object | Prove the construction approximation or use supported exact geometry |
| Mesh display looks watertight | Display geometry may lack an enclosure or semantic relation to the intended solid | Keep visualization separate from admitted geometry |
| Global geometric distance is small but an extra tiny hole appears | Geometric closeness alone need not preserve feature identity or topology | Add feature/topology obligations |
| Measured width is inside tolerance but its uncertainty interval crosses the limit | A central reading cannot establish bounded true-value conformance | Report unresolved evidence or improve inspection |
| Collision oracle returns an unchecked boolean | The result is an external assertion | Mark the oracle trusted or require a checkable certificate |
| Planner times out | Search failure does not establish nonexistence | Report unknown, including the searched fragment and bounds |
| Environment has no possible calibrated initial state | A universal claim over no executions would be vacuous | Require realizability and execution/completion obligations |
| Plan produces a larger shape than initial stock using only subtraction | A arbitrary “final shape” field ignores material conservation | Derive output from state transitions and prove stock monotonicity |
| Supplier accepts a file or returns a price | Commercial acceptance does not certify a machine trace or measurements | Record supplier acceptance separately from manufacturing and inspection evidence |

Useful repair messages should identify the failed obligation and its margin: for example, “holder enclosure intersects fixture enclosure,” rather than “shape invalid.” A library can provide a theorem of infeasibility for a sufficiently restricted fragment, but must name that fragment and avoid extending it to all processes.

An adversarial evaluation should include near-tangency, degenerate primitives, exhausted stock supports, stale environment versions, empty exports, unit mismatches, and equality-at-tolerance cases. These are future checker acceptance criteria, not tests claimed to have run.
