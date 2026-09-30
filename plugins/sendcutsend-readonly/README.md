# SendCutSend read-only guidance plugin

A **skill-only Codex plugin bundle**, prepared in installable format. It helps read official public guidance and write a manufacturing handoff with known requirements, inferences, and unknowns clearly labeled. It has no connected service account or callable SendCutSend API. Publication of this bundle does not mean it is installed in Codex.

The manifest is [.codex-plugin/plugin.json](.codex-plugin/plugin.json). The workflow is [skills/sendcutsend-handoff/SKILL.md](skills/sendcutsend-handoff/SKILL.md), and its source index is [references/official-sources.json](skills/sendcutsend-handoff/references/official-sources.json).

Example request after installation: “Use SendCutSend read-only guidance to review the documented handoff requirements for this design.” The plugin produces a report from provided design information; it does not claim a formal manufacturing witness unless one is actually available and checked.

No MCP server or app connector is included because an official supported public API contract was not found. See the [research boundary](../../docs/SENDCUTSEND.md). The bundle has no endpoints, credentials, hooks, background jobs, uploads, account creation, grant flow, quotes, carts, purchasing actions, or controller output.

The bundle can be installed through a user's local Codex plugin workflow. No marketplace configuration or authentication is changed by this repository. An authenticated connector requires supplier-supported documentation and separately approved access before implementation.

This independently authored bundle is [MIT](LICENSE). SendCutSend's name identifies the subject of the guidance; this is not an official or endorsed SendCutSend integration.
