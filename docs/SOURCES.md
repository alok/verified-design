# Primary source register

Sources reviewed on 30 September 2026. Links point to the source supporting the associated claim. The proposed architecture, definitions, and toy environment are original modeling choices; no third-party text or source code is reproduced in this repository.

| Source | Supports | Does not establish |
| --- | --- | --- |
| [Michael Reed / Crucial Flow Research](https://crucialflow.com/) | Author identity and relationship to Grassmann.jl and related projects | A verified CNC system or the reported CNC interest |
| [Grassmann.jl repository, pinned revision](https://github.com/chakravala/Grassmann.jl/tree/8f38550e9dd2f0d759060d44a8d115bc8b0b7b04) | Original public project identity and revision consulted | Correctness of a Lean port or proposed manufacturing adapter |
| [Grassmann.jl documentation](https://grassmann.crucialflow.com/dev/) | Geometric-algebra vocabulary and parameterized-space design | Machinability, clearance, process capability, or physical accuracy |
| [Grassmann.jl license](https://github.com/chakravala/Grassmann.jl/blob/8f38550e9dd2f0d759060d44a8d115bc8b0b7b04/LICENSE) | AGPL-3.0 licensing of the original source | Permission to relicense copied code under this paper's license |
| [CGAL geometry kernel manual](https://doc.cgal.org/latest/Kernel_23/index.html) | Distinction between predicates and constructions; numerical robustness considerations | Formal verification of a call to an external geometric library |
| [LinuxCNC kinematics](https://linuxcnc.org/docs/stable/html/motion/kinematics.html) | Cartesian/joint distinction and forward/inverse kinematics | A certified trajectory or limits of a particular machine |
| [NIST RS274/NGC interpreter report](https://www.nist.gov/publications/nist-rs274ngc-interpreter-version-3) | Interpreter and canonical-machining-function semantic boundary | Verification of a contemporary controller/postprocessor |
| [SendCutSend sheet-cutting guide](https://sendcutsend.com/guidelines/sheet-cutting/) | File guidance, service restrictions, material/process relationship | A universally applicable machining grammar or supported developer API |
| [SendCutSend CNC machining](https://sendcutsend.com/services/cnc-machining/) | Public billet-machining service and file-upload workflow | Supplier validation of this paper's toy case |
| [SendCutSend FAQ](https://sendcutsend.com/faq/) | Public saved-cart, quote, and account workflow descriptions | API schemas or formal/physical conformance evidence |
| [SendCutSend commercial page](https://sendcutsend.com/commercial/) | Business-facing workflow description | A developer integration contract |
| [SendCutSend Marketplace](https://sendcutsend.com/marketplace/) | Marketplace and fulfillment workflow description | Connector access or an authorization grant |

## Unresolved evidence

- Michael Reed's reported CNC interest was not confirmed in the primary sources and public-post searches examined. The paper does not assert it.
- A supported public SendCutSend API contract was not found in the official sources and site search examined. This does not rule out a private or partner API.
- No Lean build, manufacturing checker, external-oracle certificate check, machine execution, supplier upload, quote, or metrology validation is reported by this design sketch.

## Publication provenance

This repository contains original research prose, a hypothetical toy environment, small uncompiled illustrative signatures, and an independently authored documentation plugin scaffold. It includes no imported Grassmann source, private assessments, personal account records, credentials, or manufacturing instructions. References are attribution and context, not an assertion of endorsement by their authors or providers.
