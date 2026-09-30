---
name: sendcutsend-handoff
description: Read official public SendCutSend guidance and prepare an evidence-labeled manufacturing handoff from provided design information. Use for documentation research or handoff preparation; this plugin has no SendCutSend API or connected service account.
---

# SendCutSend documentation handoff

Use the official source index in `references/official-sources.json`. It lists public web pages, not API endpoints. Fetch the appropriate current page before asserting a current supplier rule. Cite the specific official source and review date. Follow relevant service-specific links exposed by that source. If fetching fails, report the access limit and keep unverified requirements unknown.

## Workflow

1. Identify the intended service from the user's request: sheet cutting, associated sheet postprocessing, or billet CNC machining. If missing, continue a generic documentation report and ask for the service before making service-specific conclusions. Do not determine the service solely from a filename extension.
2. Read only explicitly provided design information and available relevant files. Record units, material/thickness or stock, dimensions, tolerances, datums, and requested features. Preserve unknown fields. Do not manufacture measurements or claim to have read a binary model that was not actually parsed.
3. Read the applicable official public documentation. Separate documented requirements, observations about the supplied design, reasoned inferences, and unresolved questions. Do not hard-code universal capability values from an old source snapshot.
4. Prepare a local handoff report: design/file version, intended service, units, material/stock, acceptance requirements, source-backed requirements, known mismatches, unknowns, and the scope of any supplied manufacturing/export/inspection evidence.
5. Explain the evidence ceiling: a document review is not supplier acceptance; an upload/quote is not a machine-level witness; a plan is not inspection. Claim each state only when its corresponding evidence exists.

## Integration limits

This skill provides no authentication, service reads, uploads, price calculations, cart operations, account creation, ordering, manufacturing commands, or background monitoring. Do not derive an API from web-application traffic or guess routes. Do not transmit supplied design files while carrying out this documentation workflow.

If asked for an authenticated connector, first locate an official supported interface contract. Record its source and scope. Report that authentication and service operations are unconfigured until supported interfaces and approved access exist. Do not ask for credentials in chat. Account or commercial actions require their own supported tool and authorization boundary.

## Output

Return the report or its local file link, the official citations, and remaining unknowns. Say exactly what was read and checked. Do not label a candidate “verified,” “manufacturable,” “accepted by SendCutSend,” or “ordered” merely because the documentation review completed.
