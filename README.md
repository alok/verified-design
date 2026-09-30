# Verified Design: shapes with manufacturing witnesses

**A research sketch / pseudo white paper.** Every admitted design should carry a checked construction plan for a stated manufacturing environment. “Constructible” means that such a plan exists under explicit assumptions about process, tools, stock, material, fixtures, machine motion, and tolerance. The proposal has no implemented CNC library and no machine-ready output.

Start with [the paper](PAPER.md), then read the [worked pocket example](docs/TOY-CASE.md). The main claim is a proposed contract, not a proved theorem: an accepted design has an executable witness in the model, and physical conformance follows only when the model's stated assumptions hold.

| Document | Purpose |
| --- | --- |
| [Paper](PAPER.md) | Architecture, definitions, soundness targets, and research agenda |
| [Toy case](docs/TOY-CASE.md) | Stock, tool sweep, fixture clearance, and tolerance arithmetic |
| [Counterexamples](docs/COUNTEREXAMPLES.md) | Where valid geometry fails a manufacturing contract |
| [Grassmann context](docs/GRASSMANN.md) | Public source attribution and proposed algebra adapter responsibilities |
| [SendCutSend boundary](docs/SENDCUTSEND.md) | Supported file workflows and the precise integration limit |
| [Source register](docs/SOURCES.md) | Primary references, supported claims, and unresolved evidence |
| [Read-only plugin](plugins/sendcutsend-readonly/README.md) | Installable-format documentation workflow; no service connection |
| [Research scope](SPEC.md) | Limits of this repository |

The paper proposes constructions that produce geometry and plans together, rather than treating arbitrary CAD shapes as manufactured parts after a boolean validation. Imported geometry remains a candidate until a witness is supplied and checked. A useful initial scope is a finite grammar of simple subtractive operations with rational dimensions, finite tool sets, and conservative clearance certificates.

Grassmann.jl is Michael Reed's geometric-algebra project, published under AGPL-3.0. It offers relevant algebraic language; it supplies no manufacturing guarantee merely by representing a shape. This repository copies none of its code. See [attribution and limits](docs/GRASSMANN.md).

Original paper prose is [CC BY 4.0](LICENSE). The independently authored plugin scaffold is [MIT](plugins/sendcutsend-readonly/LICENSE). Citation metadata is in [CITATION.cff](CITATION.cff).
