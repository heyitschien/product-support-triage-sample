# Customer Reply Drafts — GitHub Integration Sync Issue

**Tone guide:** Calm, clear, practical. No blame. No overpromising. One next step at a time.

These are sample drafts for a fictional case. In live support, I would personalize with the customer's name, workspace details, and findings from investigation. GitHub authorization steps below describe this sample's scope problem. They are not a claim about every product's settings screen.

---

## 1. Initial reply

**When to send:** First response after ticket intake, before investigation is complete.

---

Hi there,

Thanks for reaching out — I can help you narrow this down.

It sounds like your GitHub connection is partially working (some commit linking), but pull request status is not updating consistently on the related work items. I would check authorization scope, repository access, and linking format before treating this as a product bug.

To troubleshoot efficiently, could you confirm:

1. Which workspace and team you expect PR activity to appear on?
2. Whether the GitHub authorization/install scope includes the organization and repository you expect to sync?
3. The name of one affected repository?
4. One example work item ID and one example PR URL?
5. Whether this is first-time setup or something that worked before?

If you can include a screenshot of your integration settings page (Integration → GitHub), that helps me see how the connection is configured without you needing to guess. Please redact access tokens, secrets, private repository information, or unrelated customer data before sending the screenshot.

Once I have that, I will tell you whether this looks like a setup fix we can do together or something I should reproduce and escalate to our engineering team.

Thanks for your patience — I know migrations are time-sensitive and I want to get you unblocked.

Best,  
Chien

---

## 2. Follow-up after investigation (configuration likely)

**When to send:** After reviewing settings or a customer-provided screenshot, when the authorization/install scope does not include the required organization or repository.

---

Hi again,

Thank you for the details — I think I see what is happening.

Your integration shows as connected, but the **authorization/install scope does not include the organization and repository** your team needs. The platform can only sync repositories that scope can access. The connection can look healthy while those repositories are out of scope.

**Suggested fix:**

1. Go to Settings → Integrations → GitHub
2. Disconnect the current connection
3. Reconnect and grant access that includes the required organization and repository
4. Confirm the affected repository is included in the allowlist
5. Merge a small test PR that references a work item ID in the title or description

Wait one documented sync interval, then check whether the PR status appears on the linked work item. In a real product, that interval comes from the product's own timing docs.

If that does not work, reply with a fresh screenshot of the integration page and the test PR link — I will escalate with full reproduction notes so you do not have to repeat yourself.

Best,  
Chien

---

## 3. Follow-up after investigation (reference format / user education)

**When to send:** Integration scope includes the required repository; PRs are not referencing work item IDs in the expected format.

---

Hi,

Good news — your GitHub connection includes the repository you need.

From the example PR you shared, it looks like the pull request may not be referencing the work item ID in the format the integration expects. In this sample, the platform needs the work item ID in the PR title, description, or branch name. A real product's supported formats should be confirmed in its own docs.

**Try this:**

1. Create a small test PR
2. Include the work item ID in the title, for example: `ENG-142 Fix login redirect`
3. Wait one documented sync interval and check the work item for PR status

In a real support environment I would link the verified product help article for that linking format here.

If the test PR still does not update, send me the PR URL and work item ID and I will reproduce on our side.

Best,  
Chien

---

## 4. If confirmed product bug

**When to send:** Configuration verified, reproduction confirmed, engineering engaged. This is the Path C draft. The completed Path A outcome in this sample did not use it.

---

Hi,

Thank you for working through the setup steps with me — that helped a lot.

I was able to reproduce the issue on our side after confirming the required organization, repository, and linking format are in scope. I have escalated this to our engineering team with full details, including your example work item and PR.

**What this means for you:**

- This does not appear to be a mistake on your end
- I do not have a fix timeline yet, but I will update you as soon as engineering confirms next steps
- If you have a release blocked on this, let me know your target date — I will flag urgency internally using our severity policy

I am sorry for the friction during your migration. I will stay on this ticket until we have a resolution or a reliable workaround.

Best,  
Chien

---

## 5. If configuration-related (resolved)

**When to send:** In this sample, after the customer can repeat the workflow once the required organization and repository are in scope.

---

Hi,

The test PR updated correctly after the authorization included your required organization and repository — glad that unblocked you.

**Quick tip for your team:** When several people manage integrations, it helps to have one admin confirm the install scope includes the repositories the team actually uses.

If anything else feels off during your first few cycles on the platform, reach out. Migration weeks generate a lot of small questions, and that is normal.

Welcome aboard, and good luck with the release.

Best,  
Chien

---

## Reply principles (what I optimize for)

- **Acknowledge before diagnosing** — urgency is real during a migration, even when the cause is still unknown
- **One clear next step** — avoid sending five fixes at once
- **Plain language** — assume a smart user who may not know authorization-scope jargon
- **No blame** — "the install scope did not include the required repository" is factual, not accusatory
- **Honest timelines** — never promise a fix time without engineering confirmation and the team's real severity policy
- **Reduce repeat work** — offer to escalate with notes so the customer does not re-explain
