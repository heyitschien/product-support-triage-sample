# Documentation Improvement Note — GitHub Integration Sync

**Author:** Chien Escalera Duong  
**Trigger:** Repeated support pattern — "connected but not syncing" during onboarding / migration  
**Audience:** Documentation team · Product · Support leadership  
**Type:** Public-safe sample — fictional case, no employer data

---

## Observed confusion

Customers frequently report:

> "We connected GitHub successfully, but nothing is syncing / PR status is not updating."

Common underlying causes are **configuration**, not product defects:

- Personal GitHub account authorized instead of company organization
- Repository not included in integration allowlist
- Pull requests missing work item ID in expected reference format
- User checking wrong team view or expecting instant updates

**The confusion:** Integration settings show a green "Connected" state, so users assume the setup is complete. When sync fails silently, they cannot tell whether the problem is on their side or a product bug. That drives urgent support tickets during migration weeks.

---

## Where users get stuck

| Step | Friction |
|------|----------|
| **OAuth authorization** | GitHub prompts for org vs personal — users pick personal by default |
| **Repo selection** | "All repos" vs "selected repos" — wrong repo omitted |
| **Linking PRs to work items** | Unclear where to put work item ID (title vs body vs branch) |
| **Verification** | No in-product "test your integration" step after setup |
| **Status location** | After migration from legacy tools, users look for PR status in unfamiliar UI location |
| **Timing expectations** | Users expect instant sync; actual window not visible |

---

## Suggested help-center update

**New article title:** Troubleshooting GitHub integration — connected but not syncing

**Suggested structure:**

### 1. Quick checklist (60-second version)

- Confirm you authorized your **company GitHub organization**, not a personal account
- Confirm affected repositories are in the integration allowlist
- Confirm your PR includes the work item ID in the supported format
- Run a test PR and wait one sync cycle before concluding it failed

### 2. How to verify your GitHub connection

- Step-by-step: Settings → Integrations → GitHub
- What "Connected" means vs what it does **not** guarantee
- Screenshot: correct org name visible in settings

### 3. How to link pull requests to work items

- Supported reference formats (title, description, branch — product-specific)
- Worked example: `ENG-142 Short description of change`
- Common mistakes (wrong ID format, wrong team prefix)

### 4. When to contact support

- List exact information to include: workspace URL, team name, repo, example work item, example PR, settings screenshot
- Reduces back-and-forth and speeds resolution

### 5. Related articles

- Initial GitHub setup guide
- Team mapping for integrations
- Migration guide from legacy issue trackers

---

## Suggested checklist (in-product or printable)

**GitHub integration setup verification**

```text
[ ] Authorized company GitHub organization (not personal account)
[ ] Target repository visible in allowlist
[ ] Team mapping set for affected repo
[ ] Test work item created
[ ] Test PR merged with work item ID in title or description
[ ] Waited full sync interval (see: [link to timing doc])
[ ] Checked correct team view for activity
[ ] If still failing — contact support with checklist complete
```

---

## Suggested screenshots / examples

| Asset | Purpose |
|-------|---------|
| Settings page — correct org authorization | Shows what "good" looks like |
| Settings page — personal account (common mistake) | Side-by-side comparison |
| Repo allowlist with one repo selected | Clarifies selected-repo mode |
| PR title with work item ID highlighted | Linking convention example |
| Work item view with PR status visible | Sets expectation for where to look |
| Timeline note | "Sync may take up to X minutes" |

**Accessibility:** Alt text on all screenshots; avoid red-only error indicators.

---

## Why this reduces future support load

| Benefit | Mechanism |
|---------|-----------|
| **Fewer misconfigured setups** | Org vs personal called out before user completes OAuth |
| **Self-serve before ticket** | Checklist matches 80% of inbound "not syncing" cases |
| **Faster escalations when real bugs exist** | Users arrive with minimum evidence pre-collected |
| **Lower migration churn** | New teams feel supported during high-anxiety first week |
| **Product signal clarity** | Docs deflect config issues; remaining tickets better indicate real defects |

**Estimated impact (hypothesis):** If this pattern represents even a modest share of integration tickets, a single well-placed troubleshooting article plus post-OAuth validation prompt could reduce repeat contacts and improve time-to-first-success for new workspaces.

---

## What I would do next with real product access

1. Pull ticket tags for last 90 days — confirm frequency of "connected not syncing"
2. Compare against successful setup flows — where do drop-offs happen?
3. Draft doc outline and share with support + docs for review
4. Propose lightweight in-product validation after OAuth (optional test PR prompt)
5. Measure ticket volume 30 days after publish

---

## Related files in this sample

- Full case: [support-case-github-sync.md](./support-case-github-sync.md)
- Customer replies: [customer-reply.md](./customer-reply.md)
- Escalation template: [internal-escalation-note.md](./internal-escalation-note.md)
