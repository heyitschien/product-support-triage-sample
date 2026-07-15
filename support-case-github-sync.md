# Support Case — GitHub Integration Sync Issue

**Case ID:** SAMPLE-001 (fictional)  
**Channel:** Email  
**Product context:** Generic project-management platform for software teams  
**User type:** Engineering team lead, small startup, first month on the platform  
**Coverage zone:** Pacific Time

---

## User report

**Subject:** GitHub connected but PR status not updating

> Hi support team,
>
> We connected GitHub to our workspace yesterday. Some commits seem to link to work items, but pull request status is not updating on the related items. We are not sure if this is a GitHub permissions issue, a setup issue on our side, or a bug.
>
> Our team just migrated from a legacy issue tracker and we need this working before our next release cycle. Can you help?

**Initial read:** User is blocked on workflow adoption, not just asking a how-to question. Tone suggests frustration but not hostility. Partial sync implies the integration is not completely broken.

---

## First response goals

1. Acknowledge quickly — user feels urgency after a migration
2. Restate the problem in plain language to confirm understanding
3. Ask focused clarifying questions (not a long questionnaire)
4. Set expectation: we will narrow to config vs product issue before escalating
5. Avoid blaming the user or overpromising a fix timeline

---

## Clarifying questions

Send with first reply:

1. Which workspace and team should PR activity appear on?
2. Which GitHub organization did you authorize — company org or a personal account?
3. Which repository(s) are affected? Is this all repos or only some?
4. Can you share one example work item ID and one example PR URL?
5. Did OAuth complete without error? (A redacted screenshot of integration settings is helpful — please remove tokens, secrets, and unrelated customer data.)
6. Is this a first-time setup, or did sync work before and stop?
7. Have there been recent changes to GitHub org permissions, repo access, or team membership?

---

## Investigation checklist

| Step | Question | Notes |
|------|----------|-------|
| 1 | Is GitHub showing as connected in settings? | Green/connected state does not guarantee correct scope |
| 2 | Which GitHub identity was authorized? | Personal vs org account is a common root cause |
| 3 | Is the affected repo in the integration allowlist? | Selected-repo mode vs all-repo mode |
| 4 | Does the PR reference the work item ID correctly? | Title, body, or branch naming conventions |
| 5 | Is team mapping configured for the target repo? | Wrong team = activity appears elsewhere or not at all |
| 6 | Does a new test PR with correct reference sync? | Isolates stale webhook vs ongoing failure |
| 7 | Any UI-only issue? | Try second browser or session if status appears cached |
| 8 | Silent failure pattern? | Connected with no error but no sync — document carefully |

**Layer map (troubleshooting order):**

```text
User expectation → workspace/team → integration settings → OAuth scope → org/repo permissions → reference format → sync/webhook → UI display
```

---

## Reproduction steps

Use when configuration appears correct or before engineering escalation:

1. Use an internal test workspace or approved support impersonation tooling according to company policy. Never request or use the customer’s password or private credentials.
2. Open Settings → Integrations → GitHub
3. Record: connected account name, org vs personal, repo allowlist, team mapping
4. Open example work item from customer report
5. Open example PR from customer report
6. Verify PR references work item ID in expected format
7. Create or identify a small test PR in the affected repo with correct reference
8. Wait one documented sync interval, then check whether the PR status appears on the linked work item (note actual wait time from product docs / policy)
9. Compare expected vs actual on work item view
10. If reconnect fixes issue, document exact steps for customer and internal note

**Screenshot hygiene (customer asks):** Please redact access tokens, secrets, private repository information, or unrelated customer data before sending the screenshot.

**Expected behavior:** When GitHub is connected with correct org/repo scope and PRs reference work items properly, PR status updates appear on the linked work item within the product's normal sync window.

**Actual behavior (customer report):** Partial sync — some commit linking works; PR status does not consistently update.

---

## Likely causes

| Category | Description | Support action |
|----------|-------------|----------------|
| **OAuth scope** | Personal GitHub authorized instead of company org | Guide reconnect with correct org |
| **Repo permissions** | Repo not in allowlist or integration lacks access | Update allowlist or GitHub app permissions |
| **Reference format** | PR does not include work item ID in expected place | Share linking convention + test PR |
| **Team mapping** | Activity routes to wrong team or nowhere visible | Fix mapping in integration settings |
| **User expectation** | User looking in wrong view or expecting instant update | Clarify where status appears + timing |
| **Product bug** | Setup verified correct, reproduces reliably | Escalate with full internal note |

---

## Severity / priority assessment

| Factor | Assessment |
|--------|------------|
| **User impact** | Medium-high — team blocked on migration workflow |
| **Workaround available?** | Possibly manual linking; not sustainable for eng team |
| **Scope** | Unknown until repo/org scope confirmed — could be one repo or workspace-wide |
| **Illustrative priority** | Medium-high under a hypothetical support rubric — respond same business day; escalate within about one business day if repro confirmed and config ruled out |
| **SLA note** | In production, use the company’s severity definitions and SLA policy. Treat migration-week customers as higher urgency even if technical severity is medium. |

---

## Resolution paths

### Path A — Configuration (most common)

Customer authorized wrong GitHub identity or repo not in scope. Support guides reconnect or allowlist update. Verify with test PR. Close when customer confirms.

### Path B — Reference format / user education

Integration works; customer PRs do not reference work item IDs correctly. Send linking guide + one worked example. Offer quick call if async back-and-forth is slow.

### Path C — Product bug

Configuration verified, reproduction successful, multiple users or repos affected. Escalate with [internal-escalation-note.md](./internal-escalation-note.md). Keep customer updated with honest timeline — no fix promise without engineering confirmation.

---

## Escalation criteria

Escalate to engineering or senior support when:

- [ ] Customer completed recommended configuration steps and issue persists
- [ ] Reproduction confirmed in clean test case with correct org, repo, and reference format
- [ ] Silent failure pattern (connected, no error, no sync) after reconnect
- [ ] Multiple repositories affected with identical symptoms
- [ ] Customer impact is release-blocking and config path exhausted within one business day

Do **not** escalate until minimum evidence collected (see internal note template).

---

## Product feedback signal

Patterns to flag internally if seen repeatedly:

- Integration shows "connected" when sync cannot work (misleading success state)
- No in-product error when OAuth scope is wrong — user discovers only via missing sync
- Help docs assume org-level setup; many first-time users connect personal GitHub
- PR status location in UI is non-obvious after migration from legacy tools

**Voice-of-customer summary:** *"We connected successfully but nothing works — we don't know if it's us or the product."*

---

## Documentation improvement opportunity

See [documentation-improvement-note.md](./documentation-improvement-note.md) for full proposal.

Quick win: add **"Connected but not syncing"** troubleshooting checklist to help center — org vs personal OAuth, repo allowlist, reference format, test PR steps.

---

## Interview discussion guide (10–15 min)

1. How did you read the user's emotional state and urgency?
2. Walk through your layer map — where do you check first and why?
3. What is the minimum evidence before you escalate?
4. How would you write differently for a frustrated vs curious user?
5. What product change would prevent this class of ticket?
