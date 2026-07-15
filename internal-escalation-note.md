# Internal Escalation Note — GitHub Integration Sync Issue

**Template for:** Engineering · Senior Support · Product triage  
**Case ID:** SAMPLE-001 (fictional)  
**Author:** Chien Escalera Duong (support craft sample — not live employer ticket)

---

## Summary

Customer reports GitHub integration is connected but PR status does not consistently update on linked work items. Partial commit linking may work. Customer is migrating from a legacy issue tracker and is release-adjacent. Configuration troubleshooting in progress or exhausted — requesting engineering review if reproduction confirms.

---

## Customer impact

| Field | Detail |
|-------|--------|
| **Account type** | Small startup, ~12 engineers |
| **Workflow blocked?** | Yes — team relies on PR ↔ work item visibility for release tracking |
| **Migration context** | First month on platform; high sensitivity to "silent failure" |
| **Channels used** | Email (initial) |
| **Business urgency** | Medium-high — customer cited upcoming release cycle |

---

## Steps to reproduce

1. Workspace: `[customer workspace — redacted in public sample]`
2. Team: Engineering (default team mapping)
3. Integration: GitHub — shows **Connected**
4. Authorized identity: `[org or personal handle — confirm with customer]`
5. Affected repo: `[repo name — e.g., acme-corp/api]`
6. Example work item: `[e.g., ENG-142]`
7. Example PR: `[PR URL]`
8. Confirm PR references work item ID in title/body/branch per product convention
9. Observe work item view after one documented sync interval (confirm timing from product docs / company SLA policy — do not invent a fixed minute count)
10. **Result:** PR status does not update; some commit activity may appear inconsistently

**Access policy:** Use an internal test workspace or approved support impersonation tooling. Never request or use the customer’s password or private credentials.

**Alternative repro (support test):** Reconnect with correct org → merge test PR → if still fails, bug likely.

---

## Expected behavior

When GitHub integration is configured with:

- Correct organization authorized
- Target repository in allowlist
- Valid team mapping
- PR referencing work item ID in supported format

→ PR status and activity should appear on the linked work item within the product's documented sync window.

---

## Actual behavior

- Integration UI shows successful connection
- Customer reports inconsistent or missing PR status updates
- Possible partial commit linking
- No clear in-product error message surfaced to customer
- Customer unable to distinguish setup issue vs product defect without support guidance

---

## Environment / context

| Field | Value |
|-------|-------|
| Customer browser | Chrome (reported) |
| Customer OS | macOS (reported) |
| Support verification | Settings review via customer screenshot |
| First-time setup? | Yes — migration week |
| Regression? | N/A — new customer |
| Other integrations | Unknown |

---

## Evidence collected

- [ ] Customer email with symptom description
- [ ] Screenshot of Integration → GitHub settings
- [ ] Example work item ID
- [ ] Example PR URL
- [ ] Confirmation of GitHub org vs personal authorization
- [ ] Repo allowlist configuration
- [ ] Result of test PR after guided reconnect (if attempted)
- [ ] Timestamp of last sync attempt / wait duration observed

**Minimum evidence before escalation:** At least settings screenshot + example issue + example PR + config steps attempted.

---

## Current hypothesis

**Primary (configuration):** GitHub authorized with personal account lacking org repo access — sync appears connected but has no valid scope. Support can resolve without engineering if reconnect fixes.

**Secondary (product):** Silent failure when authorized scope is empty or repo not in allowlist — UI shows success without surfacing actionable error. Product improvement candidate.

**Tertiary (bug):** Webhook delivery or sync job failure despite correct configuration — requires engineering logs if repro confirmed after config fix.

---

## Suggested next owner

| If… | Route to… |
|-----|-----------|
| Config fix resolves | Support closes — no escalation |
| Config verified, repro persists | **Integrations engineering** or on-call for GitHub sync |
| Multiple customers, same pattern | **Product** + docs — misleading connected state |
| Docs gap only | **Documentation** — see [documentation-improvement-note.md](./documentation-improvement-note.md) |

---

## Related documentation / product feedback

**Docs gap:** No prominent "connected but not syncing" article for migration users.

**Product feedback signals:**

1. Success state shown when sync cannot function (wrong OAuth scope)
2. No guided validation step after OAuth ("test your first PR")
3. Users migrating from legacy tools expect PR status in familiar location — possible UX discoverability issue

**Suggested ticket labels:** `integration` · `github` · `support-escalation` · `voice-of-customer`

---

## Support commitment to customer

- Will not close ticket until resolved or workaround confirmed
- Will provide updates on the cadence required by the company’s SLA / severity policy (illustrative sample: within one business day while engineering investigates)
- Will not ask customer to repeat information already captured in this note

---

## Author note

This is a **public-safe sample** demonstrating escalation discipline. In live support I would attach real (non-public) workspace identifiers and follow the team's actual escalation template.
