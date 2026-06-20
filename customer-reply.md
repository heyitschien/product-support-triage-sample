# Customer Reply Drafts — GitHub Integration Sync Issue

**Tone guide:** Calm, clear, practical. No blame. No overpromising. One next step at a time.

These are sample drafts for a fictional case. In live support, I would personalize with the customer's name, workspace details, and findings from investigation.

---

## 1. Initial reply

**When to send:** First response after ticket intake, before investigation is complete.

---

Hi there,

Thanks for reaching out — I can help you narrow this down.

It sounds like your GitHub connection is partially working (some commit linking), but pull request status is not updating consistently on the related work items. That usually points to a permissions scope, repository access, or linking format issue — and sometimes a product bug once setup is ruled out.

To troubleshoot efficiently, could you confirm:

1. Which workspace and team you expect PR activity to appear on?
2. Which GitHub organization you authorized — your company org or a personal account?
3. The name of one affected repository?
4. One example work item ID and one example PR URL?
5. Whether this is first-time setup or something that worked before?

If you can include a screenshot of your integration settings page (Integration → GitHub), that helps me see how the connection is configured without you needing to guess.

Once I have that, I will tell you whether this looks like a setup fix we can do together or something I should reproduce and escalate to our engineering team.

Thanks for your patience — I know migrations are stressful and I want to get you unblocked.

Best,  
Chien

---

## 2. Follow-up after investigation (configuration likely)

**When to send:** After reviewing settings or customer-provided screenshot — OAuth connected to personal account instead of org.

---

Hi again,

Thank you for the details — I think I see what is happening.

Your integration shows as connected, but GitHub was authorized with a **personal account** rather than your **company organization**. The platform can only sync repositories the authorized identity can access. If your team's code lives under the company org, the integration may appear healthy while having nothing useful to sync.

**Suggested fix:**

1. Go to Settings → Integrations → GitHub
2. Disconnect the current connection
3. Reconnect and, when GitHub prompts you, select your **company organization**
4. Confirm the affected repository is included in the allowlist
5. Merge a small test PR that references a work item ID in the title or description

Give it about 15 minutes, then check whether status updates on the linked work item.

If that does not work, reply with a fresh screenshot of the integration page and the test PR link — I will escalate with full reproduction notes so you do not have to repeat yourself.

Best,  
Chien

---

## 3. Follow-up after investigation (reference format / user education)

**When to send:** Integration scope is correct; PRs are not referencing work item IDs in the expected format.

---

Hi,

Good news — your GitHub connection and repository access look correct.

From the example PR you shared, it looks like the pull request may not be referencing the work item ID in the format the integration expects. The platform typically needs the work item ID in the PR title, description, or branch name (depending on your team's setup).

**Try this:**

1. Create a small test PR
2. Include the work item ID in the title, for example: `ENG-142 Fix login redirect`
3. Wait one sync cycle and check the work item for PR status

Here is a short guide on linking conventions: [link to help article if available]

If the test PR still does not update, send me the PR URL and work item ID and I will reproduce on our side.

Best,  
Chien

---

## 4. If confirmed product bug

**When to send:** Configuration verified, reproduction confirmed, engineering engaged.

---

Hi,

Thank you for working through the setup steps with me — that helped a lot.

I was able to reproduce the issue on our side after confirming your org, repository, and linking format are correct. I have escalated this to our engineering team with full details, including your example work item and PR.

**What this means for you:**

- This does not appear to be a mistake on your end
- I do not have a fix timeline yet, but I will update you as soon as engineering confirms next steps
- If you have a release blocked on this, let me know your target date — I will flag urgency internally

I am sorry for the friction during your migration. I will stay on this ticket until we have a resolution or a reliable workaround.

Best,  
Chien

---

## 5. If configuration-related (resolved)

**When to send:** Customer confirmed fix after reconnect or allowlist update.

---

Hi,

Great to hear the test PR updated correctly after reconnecting with your company org — glad we got you unblocked.

**Quick tip for your team:** When multiple people manage integrations, it helps to have one admin complete the org-level GitHub authorization so permissions stay consistent.

If anything else feels off during your first few cycles on the platform, reach out. Migration weeks generate a lot of small questions, and that is normal.

Welcome aboard, and good luck with the release.

Best,  
Chien

---

## Reply principles (what I optimize for)

- **Acknowledge before diagnosing** — user frustration is valid, especially during migration
- **One clear next step** — avoid sending five fixes at once
- **Plain language** — assume smart user, not necessarily familiar with OAuth scope jargon
- **No blame** — "authorized with personal account" is factual, not accusatory
- **Honest timelines** — never promise "fixed in an hour" without engineering confirmation
- **Reduce repeat work** — offer to escalate with notes so customer does not re-explain
