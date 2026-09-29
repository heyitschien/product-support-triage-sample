# Documentation Improvement Note — GitHub Integration Sync

**Author:** Chien Escalera Duong  
**Trigger:** Potential repeat pattern to validate from the synthetic case — "connected but not syncing" during onboarding / migration  
**Audience:** Documentation team · Product · Support leadership  
**Type:** Public-safe sample — fictional case, no employer data, no measured ticket volume

The green "Connected" behavior below belongs to this sample scenario. It is not a verified universal product behavior.

---

## Observed confusion

Representative report / pattern a support team may encounter:

> "We connected GitHub successfully, but nothing is syncing / PR status is not updating."

Candidate configuration causes to check before treating the issue as a product defect:

- Authorization/install scope does not include the required organization or repository
- Repository not included in the integration allowlist
- Pull requests missing the work item ID in the expected reference format
- User checking the wrong team view, or expecting an instant update the product does not promise

**The confusion in this sample:** Integration settings show a green "Connected" state, so the user assumes setup is complete. When sync fails without an in-product error, they cannot tell whether the problem is configuration or a product bug. That is the kind of uncertainty that can turn into an urgent ticket during a migration.

---

## Where users can get stuck

These are friction points to design for. They are not measured drop-off data.

| Step | Friction |
|------|----------|
| **Authorization** | The install scope may not include the organization or repository the team expects to sync |
| **Repo selection** | "All repos" vs "selected repos" — the needed repo can be left out |
| **Linking PRs to work items** | Unclear where to put the work item ID (title vs body vs branch) |
| **Verification** | No in-product "test your integration" step after setup |
| **Status location** | After a migration, users may look for PR status in an unfamiliar place |
| **Timing expectations** | Users may expect instant sync when the product's own timing docs say otherwise |

---

## Suggested help-center update

**New article title:** Troubleshooting GitHub integration — connected but not syncing

**Suggested structure:**

### 1. Quick checklist (60-second version)

- Confirm the authorization/install scope includes the **required organization and repository**
- Confirm affected repositories are in the integration allowlist
- Confirm the PR includes the work item ID in the supported format
- Run a test PR and wait one sync cycle — using the product's documented interval — before concluding it failed

### 2. How to verify the GitHub connection

- Step-by-step: Settings → Integrations → GitHub
- What "Connected" means in this sample, and what it does **not** guarantee
- Example of settings that show the required organization and repository in scope

### 3. How to link pull requests to work items

- Supported reference formats (title, description, branch — confirm against the real product)
- Worked example: `ENG-142 Short description of change`
- Common mistakes in this sample (wrong ID format, wrong team prefix)

### 4. When to contact support

- List the exact information to include: workspace, team name, repo, example work item, example PR, settings screenshot
- Reduces back-and-forth when a ticket is actually needed

### 5. Related articles

- Initial GitHub setup guide
- Team mapping for integrations
- Migration guide from legacy issue trackers

---

## Suggested checklist (in-product or printable)

**GitHub integration setup verification**

```text
[ ] Authorization/install scope includes the required organization and repository
[ ] Target repository visible in the allowlist
[ ] Team mapping set for the affected repo
[ ] Test work item created
[ ] Test PR opened with the work item ID in the title or description
[ ] Waited the sync interval from the verified product timing/SLA documentation
[ ] Checked the correct team view for activity
[ ] If still failing — contact support with the checklist complete
```

In a real implementation, link that timing step to the verified product timing or SLA documentation. This sample does not invent that link.

---

## Suggested screenshots / examples

| Asset | Purpose |
|-------|---------|
| Settings page — required org and repo in scope | Shows what "in scope" looks like in this sample |
| Settings page — required repo missing from scope | Side-by-side comparison for this scenario |
| Repo allowlist with one repo selected | Clarifies selected-repo mode |
| PR title with work item ID highlighted | Linking convention example |
| Work item view with PR status visible | Sets expectation for where to look |
| Timeline note | "Use the sync window from the product's own docs" |

**Accessibility:** Alt text on all screenshots; do not rely on red-only error indicators.

---

## Why this could reduce future support load

| Benefit | Mechanism |
|---------|-----------|
| **Fewer misconfigured setups** | Missing org/repo scope is called out before the user treats setup as finished |
| **Self-serve before a ticket** | A checklist gives the user the same checks support would ask for |
| **Clearer escalations when a defect remains** | Users can arrive with minimum evidence already collected |
| **Less onboarding uncertainty** | New teams get a concrete check during the first week, if the article is validated |
| **Clearer product signal** | Docs absorb configuration questions; remaining tickets are more useful as defect signal |

**Estimated impact (hypothesis):** If a real ticket review later shows this pattern, a troubleshooting article plus a post-authorization validation prompt could reduce onboarding uncertainty and reduce avoidable repeat contacts. That impact is not measured here.

---

## What I would do next with real product access

1. Pull ticket tags for a recent window and check whether "connected not syncing" actually recurs
2. Compare that with successful setup flows and see where people drop off
3. Draft a doc outline and share it with support and docs for review
4. Propose a lightweight in-product validation after authorization (optional test PR prompt)
5. Measure ticket volume for a set window after publish, using the team's real definitions

---

## Related files in this sample

- Case outcome: [CASE-OUTCOME.md](./CASE-OUTCOME.md)
- Full case: [support-case-github-sync.md](./support-case-github-sync.md)
- Customer replies: [customer-reply.md](./customer-reply.md)
- Escalation template: [internal-escalation-note.md](./internal-escalation-note.md)
- Synthetic evidence packet: [evidence/](./evidence/)
