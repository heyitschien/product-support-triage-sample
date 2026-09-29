# Support Case — GitHub Integration Sync Issue

**Case ID:** SAMPLE-001 (fictional)  
**Channel:** Email  
**Product context:** Generic project-management platform for software teams  
**User type:** Engineering team lead, small startup, first month on the platform  
**Coverage zone:** Pacific Time

**Scope:** Recruiter-facing synthetic work sample. Product paths, timestamps, logs, customer details, and policies below are illustrative. This is not a real ticket, a real customer, or verified product behavior.

---

## User report

**Subject:** GitHub connected but PR status not updating

> Hi support team,
>
> We connected GitHub to our workspace yesterday. Some commits seem to link to work items, but pull request status is not updating on the related items. We are not sure if this is a GitHub permissions issue, a setup issue on our side, or a bug.
>
> Our team just migrated from a legacy issue tracker and we need this working before our next release cycle. Can you help?

**Initial read:** The user is blocked on workflow adoption, not just asking a how-to question. The message shows urgency after a migration. Partial sync implies the integration is not completely broken.

---

## First response goals

1. Acknowledge quickly — the user needs this working after a migration
2. Restate the problem in plain language to confirm understanding
3. Ask focused clarifying questions (not a long questionnaire)
4. Set expectation: narrow to configuration vs product issue before a routine escalation
5. Avoid blaming the user or overpromising a fix timeline

---

## Clarifying questions

Send with first reply:

1. Which workspace and team should PR activity appear on?
2. Does the GitHub authorization/install scope include the organization and repository you expect to sync?
3. Which repository(s) are affected? Is this all repos or only some?
4. Can you share one example work item ID and one example PR URL?
5. Did authorization complete without error? (A redacted screenshot of integration settings is helpful — please remove tokens, secrets, and unrelated customer data.)
6. Is this a first-time setup, or did sync work before and stop?
7. Have there been recent changes to GitHub organization permissions, repository access, or team membership?

---

## Investigation checklist

| Step | Question | Notes |
|------|----------|-------|
| 1 | Is GitHub showing as connected in settings? | A connected state does not guarantee the required scope |
| 2 | Does the authorization/install scope include the required organization and repository? | Missing org/repo access can leave the UI looking healthy |
| 3 | Is the affected repo in the integration allowlist? | Selected-repo mode vs all-repo mode |
| 4 | Does the PR reference the work item ID correctly? | Title, body, or branch naming conventions |
| 5 | Is team mapping configured for the target repo? | Wrong team = activity appears elsewhere or not at all |
| 6 | Does a new test PR with correct reference sync? | Isolates a stale delivery from an ongoing failure |
| 7 | Any UI-only issue? | Try a second browser or session if status appears cached |
| 8 | Silent failure pattern? | Connected with no error but no sync — document carefully |

**Layer map (troubleshooting order):**

```text
User expectation → workspace/team → integration settings → authorization/install scope → org/repo permissions → reference format → sync/webhook → UI display
```

---

## Reproduction steps

Use when configuration appears correct, or before a routine engineering escalation:

1. Use an internal test workspace or approved support impersonation tooling according to company policy. Never request or use the customer’s password or private credentials.
2. Open Settings → Integrations → GitHub
3. Record: authorized installation, whether the required organization and repository are in scope, repo allowlist, and team mapping
4. Open the example work item from the customer report
5. Open the example PR from the customer report
6. Verify the PR references the work item ID in the expected format
7. Create or identify a small test PR in the affected repo with the correct reference
8. Wait one documented sync interval, then check whether the PR status appears on the linked work item (use the interval from product docs or policy — do not invent one)
9. Compare expected vs actual on the work item view
10. If correcting the scope fixes the issue, document the exact steps for the customer and the internal note

**Screenshot / evidence hygiene:** Please redact access tokens, secrets, private repository information, or unrelated customer data before sending a screenshot.

**Expected behavior:** When the authorization/install scope includes the required organization and repository, and PRs reference work items properly, PR status updates appear on the linked work item within the product's normal sync window.

**Actual behavior (customer report in this sample):** Partial sync — some commit linking works; PR status does not consistently update.

---

## Candidate causes to check

These are checks for this synthetic case, not a claim about how often each cause appears in production.

| Category | Description | Support action |
|----------|-------------|----------------|
| **Authorization scope** | Install scope lacks access to the required organization or repository | Guide a reconnect that includes the required org and repo |
| **Repo permissions** | Repo not in allowlist, or the installation lacks access | Update the allowlist or the installation's repository access |
| **Reference format** | PR does not include the work item ID in the expected place | Share the linking convention and a test PR |
| **Team mapping** | Activity routes to the wrong team or is not visible | Fix mapping in integration settings |
| **User expectation** | User is looking in the wrong view, or expects an instant update | Clarify where status appears, and what the product's timing docs say |
| **Product bug** | Setup verified, and the failure still reproduces | Escalate with the full internal note |

---

## Severity / priority assessment

| Factor | Assessment |
|--------|------------|
| **User impact** | The sample customer says the team is blocked on a migration workflow |
| **Workaround available?** | Manual linking might be possible; it is not a sustainable path for an engineering team |
| **Scope** | Unknown until org/repo access is confirmed — could be one repo or workspace-wide |
| **Release / service impact** | The customer cites an upcoming release cycle. In a real queue, score this with the company's severity definitions, release impact, and security or service-impact rules |
| **SLA note** | Do not invent a response window. Use the company's real severity definitions and SLA. Migration context can raise urgency; it does not create a policy by itself |

---

## Resolution paths

### Path A — Configuration

In this sample, the authorization/install scope does not include the required organization or repository. Support guides a reconnect or allowlist update, then verifies with a test PR. Close when the customer can repeat the workflow. This is the ending recorded in [GITHUB-INTEGRATION-CASE-OUTCOME.md](./GITHUB-INTEGRATION-CASE-OUTCOME.md).

### Path B — Reference format / user education

The integration scope is sufficient, but the customer's PRs do not reference work item IDs in the expected format. Send the linking guide and one worked example. Offer a short call if async back-and-forth is slow.

### Path C — Product bug

Configuration is verified, reproduction succeeds, and the failure continues. Escalate with [internal-escalation-note.md](./internal-escalation-note.md). Keep the customer updated with an honest status — no fix promise without engineering confirmation.

---

## Escalation criteria

Normally collect the minimum evidence in the internal note before escalating.

Escalate immediately when a real security issue, an outage, or the company's severity policy requires it. Do not hold those cases for a full configuration checklist.

Otherwise escalate to engineering or senior support when:

- [ ] The customer completed the recommended configuration steps and the issue persists
- [ ] Reproduction is confirmed in a clean test with the required org/repo scope and reference format
- [ ] A silent failure remains (connected, no error, no sync) after the scope is corrected
- [ ] Multiple repositories show the same symptoms
- [ ] Release impact remains after the configuration path is exhausted

---

## Product feedback signal

If this sample's confusion showed up in real tickets, these are the patterns worth flagging. They are hypotheses, not measured production findings:

- The integration shows "connected" when sync cannot reach the required repository
- No in-product error appears when the install scope is incomplete, so the user notices only because sync is missing
- Help docs may assume the required organization is already in scope
- The place to see PR status may be non-obvious after a migration from another tool

**Voice-of-customer summary (sample wording):** *"We connected successfully but nothing useful is syncing — we don't know if it's us or the product."*

---

## Documentation improvement opportunity

See [documentation-improvement-note.md](./documentation-improvement-note.md) for the full proposal.

Quick win to validate: a **"Connected but not syncing"** checklist covering authorization/install scope, repo allowlist, reference format, and a test PR.
