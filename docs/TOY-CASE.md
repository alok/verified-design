# Toy case: a capsule pocket in a retained blank

This is an invented, idealized environment used to test the proposed contract. The equations and bounds below are a mathematical walkthrough, not a Lean-checked proof, a validated machining recipe, or a SendCutSend service claim. Coordinates are in millimeters.

## 1. Initial state and intended result

The accepted blank is the box

**S₀ = [0, 40] × [0, 30] × [−6, 0].**

The top face is the datum plane z = 0. Define the center segment **L = [12, 28] × {15}** and the closed planar disk **B₂** of radius 2 centered at the origin. The ideal removal region is

**R = (L ⊕ B₂) × [−2, 0],**

where ⊕ is a Minkowski sum. Its planar footprint is a capsule: a rectangle between two semicircular ends. The ideal finished stock is the regular closed solid associated with **S₀ ∖ R**. Boundary conventions must be fixed in a future formalization; here removal of boundary surfaces is interpreted through that regularization.

The pocket has nominal overall length 20, width 4, depth 2, and end radius 2. It stays strictly inside the blank. The blank remains one retained part; this example intentionally avoids contouring a loose finished part out of sheet stock.

The acceptance contract asks for a pocket with this feature identity and topology; its specified boundary must remain within a 0.10 normal-distance envelope of the ideal boundary under the correspondence used by the model. Overall length, width, and depth each have a ±0.20 dimensional allowance. Remaining floor thickness must be at least 3.70. Burrs, finish, and strength would require additional predicates if they were needed; none are asserted here.

## 2. Tool, fixture, and machine assumptions

The ideal cutting region is a cylinder of radius 2 extending from the tool tip to 3 above it. The noncutting shank has radius 2 and spans tip+3 to tip+8; the holder has radius 5 and spans tip+8 to tip+18. These envelopes define the entire moving assembly in this toy model. A real spindle or other omitted component cannot inherit its collision conclusion.

Two fixture obstacles occupy **[0, 4] × [0, 30] × [0, 4]** and **[36, 40] × [0, 30] × [0, 4]**. Their contacts with stock at the top plane are intentional. An external workholding hypothesis states that this fixture keeps the blank fixed under the model's allowed loads. Obstacle geometry alone does not establish that hypothesis.

The machine has identity kinematics q = (x, y, z) and joint limits **x ∈ [0,40]**, **y ∈ [0,30]**, **z ∈ [−3,12]**. Other fixed machine obstacles are assumed absent from the swept assembly region. These are toy assumptions, not specifications of an actual machine.

The process grammar permits a modeled vertical entry and a modeled linear pocket sweep for this tool/material pair. A capability attestation is assumed to cover engagement, timing, restraint, and cutting error. No feed, spindle setting, controller instruction, or physical execution is provided. A future checker must verify a time-parameterized trajectory within the actual motion and process constraints.

## 3. Abstract construction witness

The finite geometric trace has three pieces: descend at planar center (12,15) from tip z = 10 to z = −2; move the tip along L at z = −2; return vertically at planar center (28,15) to z = 10. Entry and withdrawal have no planar displacement. Cutting is interpreted only by intersection of the cutting region with current stock.

For the entry, the union of cutter/stock intersections is **({(12,15)} ⊕ B₂) × [−2,0]**. For the horizontal piece it is **(L ⊕ B₂) × [−2,0]**. Withdrawal removes no region outside that capsule. The entry disk is already contained in the horizontal sweep. Hence the union of ideal removed regions is exactly R, and sequential subtraction has the intended regularized final denotation.

This calculation proves neither cutting forces nor the claimed physical error bounds. It only supplies the geometric denotation that a future proof of the constructor would establish under the ideal cutting semantics.

## 4. Clearance and reachability obligations

The holder's planar x extent along the trace lies in **[7,33]**. It has 3 of horizontal clearance from each fixture strip. At the deepest position its bottom is z = 6, so it also clears the nominal stock top by 6 and fixture tops by 2. The shank bottom is z = 1 at that position and its x extent stays in [10,30]. The cutting cylinder's stock contact is intentional; fixture contact is prohibited.

The trace stays within the joint box. Each segment remains in it by convexity. This is possible because kinematics are explicitly identity here; this argument does not carry over to an arbitrary robot or multi-axis mill.

In this ideal model, the pocket removal is enclosed by **[10,30] × [13,17] × [−2,0]**. It leaves a floor of thickness 4 and retains peripheral stock. Workholding strength still depends on the separate fixture/capability hypothesis. A general library must check preserved support after every operation, rather than infer it from a positive remaining volume.

## 5. A deliberately conservative error budget

Assume the following independently bounded contributions to each relevant boundary position in the registered feature model. “Independently bounded” means each bound holds; statistical independence is not assumed.

| Contribution | Assumed worst-case bound |
| --- | ---: |
| Exact geometric specification | 0.00 |
| Tool geometry, including tip uncertainty | 0.01 |
| Controller interpolation and tracking | 0.02 |
| Datum registration | 0.02 |
| Material, elastic, and thermal effects | 0.02 |
| Export and numerical approximation | 0.01 |
| **Worst-case sum** | **0.08** |

All terms must be justified in the same norm and datum, and cover the entire trace. The assumed capability relation must also preserve the required capsule feature and topology. A 0.08 positional bound by itself cannot establish the absence of arbitrary extra defects.

The sum leaves 0.02 against the 0.10 boundary allowance. A dimension formed from two independently perturbed boundaries can deviate by **2 × 0.08 = 0.16**; the ±0.20 dimensional allowances leave 0.04. It would be incorrect to reuse the single-boundary 0.08 as the general width error.

Separately assume stock thickness is within 0.05 of 6. A conservative floor lower bound is **(6 − 0.05) − (2 + 0.16) = 3.79**, which exceeds 3.70. Stock acceptance and the depth uncertainty model must justify this calculation.

For collision checks, assume a total *relative* obstacle/assembly enclosure expansion of at most 0.16, covering fixture geometry as well as tool pose. The 3 horizontal fixture gap is then at least 2.84. The shank/stock vertical gap is at least 0.84, and holder/stock vertical clearance at least 5.84. These are positive margins. Clearance from fixture tops can likewise be bounded, but the horizontal separation already excludes fixture intersection along this trace.

Every number in this table is an assumption or arithmetic consequence. No measurement or experiment in this repository validates the assumptions. If even one bound lacks evidence, the design can remain admitted in the toy model while its physical conformance remains conditional.

## 6. Inspection examples

For the width acceptance interval [3.80,4.20], an observation **4.04 ± 0.03** implies a possible true width in [4.01,4.07], wholly within acceptance. An observation **4.18 ± 0.03** implies [4.15,4.21], crossing the upper limit. The latter supplies unresolved conformance evidence under the bounded-interval rule, despite its central reading being inside tolerance.

Checking width alone does not establish the complete pocket specification. Depth, location, correspondence of boundaries, floor thickness, and topology need their own appropriate evidence. Planned conformance and inspected conformance should therefore appear as separate statuses.

## 7. What the example establishes

The geometry is simple enough to state a finite witness and calculate its denotation, access, and margin obligations explicitly. Changing the tool radius, fixture placement, datum uncertainty, or acceptance limits changes the obligations. This is precisely why an admitted design should be indexed by a versioned environment and acceptance contract.

The next formalization target is a sound constructor for this capsule-pocket fragment and a compositional stock invariant. It is not a general pocket planner and has no asserted coverage of arbitrary imported CAD.
