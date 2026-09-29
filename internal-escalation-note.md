# Internal Escalation Note — GitHub Integration Sync Issue

**Template for:** Engineering · Senior Support · Product triage  
**Case ID:** SAMPLE-001 (fictional)  
**Author:** Chien Escalera Duong (support craft sample — not a live employer ticket)

**Status:** This file is the **conditional handoff template for Path C**.

The completed Path A outcome in [CASE-OUTCOME.md](./CASE-OUTCOME.md) did **not** require engineering escalation. The configuration fix resolved the issue, and the controlled test passed.

Use this note only if scope and configuration are verified and a controlled test still fails, or if security, an outage, or severity policy requires an immediate handoff.

Fields below are a template. Unchecked items are not already-verified facts.

---

## Summary

Sample customer reports the GitHub integration is connected, but PR status does not consistently update on linked work items. Partial commit linking may work. The sample customer is migrating from a legacy issue tracker and is release-adjacent. Fill this note when configuration troubleshooting is exhausted, or when policy says to escalate before that.

---

## Customer impact

| Field | Detail |
|-------|--------|
| **Account type** | Small startup, ~12 engineers (sample) |
| **Workflow blocked?** | Yes, in the sample — the team relies on PR ↔ work item visibility for release tracking |
| **Migration context** | First month on the platform; high sensitivity to a connection that looks healthy and does not sync |
| **Channels used** | Email (initial) |
| **Business urgency** | Sample customer cited an upcoming release cycle. Score the real case with the company's severity policy |

---

## Steps to reproduce

1. Workspace: `[customer workspace — redacted in public sample]`
2. Team: Engineering (default team mapping)
3. Integration: GitHub — shows **Connected**
4. Authorization/install scope: `[confirm whether the required organization and repository are included]`
5. Affected repo: `[repo name — e.g., acme-corp/api]`
6. Example work item: `[e.g., ENG-142]`
7. Example PR: `[PR URL]`
8. Confirm the PR references the work item ID in the title, body, or branch per the product's convention
9. Observe the work item view after one documented sync interval (confirm timing from product docs or company policy — do not invent a fixed minute count)
10. **Result to record:** PR status does not update; some commit activity may appear inconsistently

**Access policy:** Use an internal test workspace or approved support impersonation tooling. Never request or use the customer’s password or private credentials.

**Alternative check (support test):** Correct the install scope so the required organization and repository are included, then merge a test PR. If it still fails, a product defect is more likely.

---

## Expected behavior

When the GitHub integration is configured with:

- Authorization/install scope that includes the required organization and repository
- Target repository in the allowlist
- Valid team mapping
- A PR that references the work item ID in a supported format

→ PR status and activity should appear on the linked work item within the product's documented sync window.

---

## Actual behavior to capture

Record what was observed. Do not treat this list as already proven:

- Integration UI shows a successful connection
- Customer reports inconsistent or missing PR status updates
- Possible partial commit linking
- No clear in-product error message surfaced to the customer
- Customer cannot tell a setup issue from a product defect without support guidance

---

## Environment / context

Fill from the real ticket. Sample placeholders only:

| Field | Value |
|-------|-------|
| Customer browser | `[reported browser]` |
| Customer OS | `[reported OS]` |
| Support verification | `[settings review via customer screenshot, if provided]` |
| First-time setup? | `[yes / no]` |
| Regression? | `[yes / no / unknown]` |
| Other integrations | `[unknown until asked]` |

---

## Evidence checklist

Check only what was actually collected:

- [ ] Customer email with the symptom description
- [ ] Screenshot of Integration → GitHub settings
- [ ] Example work item ID
- [ ] Example PR URL
- [ ] Confirmation that the authorization/install scope does or does not include the required organization and repository
- [ ] Repo allowlist configuration
- [ ] Result of a test PR after the scope was corrected (if attempted)
- [ ] Timestamp of the last sync attempt / wait duration observed

**Minimum evidence before a routine escalation:** settings screenshot, example work item, example PR, and the configuration steps already attempted.

**Exception:** escalate immediately when a real security issue, an outage, or the company's severity policy requires it. Do not wait for this checklist in those cases.

---

## Current hypothesis

**Primary (configuration):** The authorization/install scope lacks access to the required organization or repository. The UI can show connected while that scope is missing. Support can resolve without engineering if correcting the scope fixes the test.

**Secondary (product):** Silent failure when the authorized scope is empty or the repo is not in the allowlist — the UI shows success without an actionable error. Product improvement candidate, not a measured finding.

**Tertiary (bug):** Delivery or sync-job failure despite correct configuration. This needs engineering logs if the failure still reproduces after the scope is corrected.

---

## Suggested next owner

| If… | Route to… |
|-----|-----------|
| Config fix resolves | Support closes — no escalation. This is the Path A ending in [CASE-OUTCOME.md](./CASE-OUTCOME.md) |
| Config verified, repro persists | **Integrations engineering** or on-call for the sync path |
| Security, outage, or severity policy requires it | Escalate immediately on the team's on-call path |
| Same pattern needs a docs fix | **Documentation** — see [documentation-improvement-note.md](./documentation-improvement-note.md) |

---

## Related documentation / product feedback

**Docs gap in this sample:** No prominent "connected but not syncing" article for someone setting this up during a migration.

**Product feedback signals to validate, not claimed as measured:**

1. A success state can appear when the install scope cannot reach the required repository
2. There may be no guided validation step after authorization ("test your first PR")
3. People migrating from another tool may look for PR status in a familiar place and miss it

**Suggested ticket labels:** `integration` · `github` · `support-escalation` · `voice-of-customer`

---

## Support commitment to customer

- Will not close the ticket until it is resolved or a workaround is confirmed
- Will update the customer on the cadence required by the company's SLA and severity policy
- Will not ask the customer to repeat information already captured in this note

---

## Author note

This is a **public-safe sample** demonstrating escalation discipline. In live support I would attach real (non-public) workspace identifiers and follow the team's actual escalation template. Nothing in this file is a real production log, webhook, or SLA.
