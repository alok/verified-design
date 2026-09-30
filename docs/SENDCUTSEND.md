# SendCutSend: documented handoff and integration boundary

Review date: **30 September 2026**. This note records official public workflows and the limit of the integration prepared here. It is not an account connection or an order.

## What official sources support

The [sheet-cutting guide](https://sendcutsend.com/guidelines/sheet-cutting/) documents CAD/vector file preparation, including consistent units, scale, and contours, and distinguishes sheet cutting from billet machining. The selected material/thickness affects the supplier's process selection. Exact current feature limits belong to the service and material guidance; this sketch does not hard-code a universal rule table.

The separate [CNC machining service](https://sendcutsend.com/services/cnc-machining/) concerns billet parts and advertises a file-upload workflow. Its requirements must be checked for that service, rather than inferred from sheet-routing rules. The service page should be followed to its current guidance before preparing a real billet handoff.

The official [FAQ index](https://sendcutsend.com/faq/) describes saved carts, shared purchase links, and formal quotes. These are website workflows, not a documented programmable API. A formal quote, accepted upload, or saved-cart link must retain its own evidentiary status. The [Marketplace page](https://sendcutsend.com/marketplace/) describes supplier-hosted sale and fulfillment of designs; it does not by itself grant connector access.

## API discovery result

No supported public developer API specification, authentication scheme, OpenAPI document, SDK, or published integration contract was located in the official sources examined. The review covered the official homepage, FAQ, commercial page, guidelines, service page, Marketplace, and public site search for API. This is a bounded discovery result. Partner access might exist, and the result is not proof that SendCutSend has no API.

An installed-plugin directory search separately found no exact SendCutSend match. That result is likewise about discovery in that directory, not the supplier's interface availability.

The address of a web application, network calls made by its frontend, and undocumented routes are not evidence of a supported API. The scaffold includes no guessed endpoints and does not inspect private web-application calls.

## Prepared capability

The [sendcutsend-readonly plugin](../plugins/sendcutsend-readonly/README.md) is a valid-format, skill-only local bundle. It can direct an agent to read official documentation, identify the relevant service, and produce a handoff report from explicitly provided design information. Its source register distinguishes a documented rule from an inference and from an unknown.

It has no MCP server, app connector, authentication configuration, credential storage, automatic uploader, quotation client, cart client, or order client. This repository publishes the bundle; it does not claim that Codex has installed it. It creates no account or persistent service grant.

## Suggested handoff record

| Field | Meaning |
| --- | --- |
| Design intent and file identity | Named version and content digest of the file to be reviewed |
| Service | Sheet cutting, sheet postprocessing, or billet CNC; never inferred solely from file extension |
| Units, material, thickness/stock | Explicit choices, with unknown fields retained |
| Acceptance | Required dimensions, tolerances, datums, feature and finish requirements |
| Rule evidence | Official source URLs, review date, and requirement-specific observations |
| Model witness | Plan/certificate identity and exact environment assumptions, if available |
| Export evidence | Semantic and error relationship between the design and emitted file |
| Supplier evidence | Any actual supplier response, preserving its scope and date |
| Inspection evidence | Actual measurements and metrology assumptions, if supplied |

This is a proposed report structure, not SendCutSend's request schema. Its contents remain local until the user authorizes a specific external handoff. A future implementation may generate a file-based export with a checked relationship to the design; no actual export or uploaded design is asserted here.

## Boundary for a future authenticated connector

First obtain an official interface contract from published documentation or supplier-provided partner documentation. Establish supported operations, authentication/scopes, rate limits, file semantics, data handling, and any permitted test environment. Then implement the smallest documented read-only action and test it against approved access. Separately authorize uploads and commercial mutations at their actual boundaries.

Without that contract, a programmable connector remains unspecified. The useful deliverable now is the documentation workflow and a preparation record. No endpoint, key, new account, grant, quotation, or purchase has been fabricated to fill the gap.
