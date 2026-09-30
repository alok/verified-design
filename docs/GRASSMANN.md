# Grassmann context and attribution

The relevant original project is [chakravala/Grassmann.jl](https://github.com/chakravala/Grassmann.jl), authored by Michael Reed. His own [Crucial Flow Research page](https://crucialflow.com/) identifies him and the project. This refers to the contemporary library author, not Hermann Grassmann, the historical mathematician.

Public source revision consulted for attribution: [8f38550e9dd2f0d759060d44a8d115bc8b0b7b04](https://github.com/chakravala/Grassmann.jl/tree/8f38550e9dd2f0d759060d44a8d115bc8b0b7b04). The source has an [AGPL-3.0 license](https://github.com/chakravala/Grassmann.jl/blob/8f38550e9dd2f0d759060d44a8d115bc8b0b7b04/LICENSE). This paper imports no source and does not relicense the original project.

The [public documentation](https://grassmann.crucialflow.com/dev/) describes parameterized spaces and geometric-algebra operations. This suggests an algebraic vocabulary for a Lean-oriented design: spaces and grades as indices, geometry-specific operations behind a small interface, and explicit semantic interpretation of representations. These are architectural proposals here, rather than a correctness assessment of an existing Lean implementation.

## Proposed adapter obligations

| Proposed use of algebra | Additional statement needed |
| --- | --- |
| Encode a point, line, or plane | Establish its Euclidean denotation and handle exceptional representations |
| Compose frame transformations | Establish transform semantics, orientation, metric assumptions, and conversion bounds |
| Compute incidence or orientation | Prove the predicate agrees with the geometric specification |
| Use a projective or conformal representation | Identify null/degenerate cases and valid extraction rules |
| Use a fast Float kernel | Prove or conservatively bound its relation to the exact specification |
| Express a tool pose | Connect it to joint kinematics and the complete assembly geometry |

The manufacturing layer then checks stock removal, tool access, fixture restraint, motion, and acceptance. None follows merely from a correct multivector product. A future dependency decision needs evidence for the precise operations and coefficients used, as well as license review for any actual code reuse.

## CNC provenance limit

The library author's reported interest in CNC prompted this research. It was not independently confirmed in the public primary sources examined on 30 September 2026: his project page, repository description, and searches of his public GitHub and Julia forum posts. Absence from those searches does not establish absence of such an interest. The paper therefore makes no attributed CNC claim and does not present Grassmann.jl as a CAM system.

The proposed relationship is technical: geometric algebra might support a geometry layer whose interpretation can be checked. Whether it improves performance or proof ergonomics for this manufacturing fragment remains an open research question.
