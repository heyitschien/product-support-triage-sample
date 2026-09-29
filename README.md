# Support Triage Samples

**Author:** Chien Escalera Duong  
**Type:** Public, synthetic support samples — safe for recruiters

This repository contains **two separate fictional examples**. They demonstrate support judgment without claiming that either scenario came from a real customer, employer, or production support role.

1. **Junior IT support:** a time-sensitive Outlook send failure
2. **Product support:** a GitHub integration that appears connected but does not sync

These are different examples. They should not be read as one customer story.

---

## Start here — Junior IT support proof

[CASE-OUTCOME.md](./CASE-OUTCOME.md) is the standalone one-page Outlook example. It shows:

- A calm response to a busy professional
- Safe first-line isolation across service, account, webmail, and local-client layers
- A usable ticket note
- Clear escalation thresholds and senior-engineer handoff
- Security, privacy, and approved-AI boundaries
- Ownership through resolution or acknowledged handoff

It is evidence of the **support approach**, not a claim of prior MSP, law-firm IT, Microsoft 365 administration, or production helpdesk employment.

---

## Separate example — Product support / GitHub integration

A fictional dev team connected GitHub to a project-management workspace, but pull request status is not updating on related work items. This case contains customer replies, investigation notes, a simulated outcome, a conditional engineering handoff, and a documentation-improvement proposal.

**Product-support quick path:**

1. **[GITHUB-INTEGRATION-CASE-OUTCOME.md](./GITHUB-INTEGRATION-CASE-OUTCOME.md)** — the GitHub story in one page
2. **[customer-reply.md](./customer-reply.md)** — customer communication for that case
3. **[internal-escalation-note.md](./internal-escalation-note.md)** — conditional engineering handoff
4. **[documentation-improvement-note.md](./documentation-improvement-note.md)** — prevention loop

Hiring managers who want depth can open [support-case-github-sync.md](./support-case-github-sync.md). Product-support responsibility map: [ROLE-MAPPING.md](./ROLE-MAPPING.md). Visual flow: [docs/triage-flow-diagram.md](./docs/triage-flow-diagram.md).

---

## Role alignment

| Sample | Best-aligned role families |
| --- | --- |
| Outlook send failure | Junior IT Support · Helpdesk · MSP Support · Desktop Support |
| GitHub integration | Product Support · Technical Support · Onboarding · Junior Implementation |

---

## Why it matters

Recruiters and hiring managers often ask: *Can this person triage technical user issues, communicate clearly, and feed useful signal back to the team?*

These artifacts answer that with concrete examples — not claims about years of MSP, helpdesk, SaaS, or Microsoft 365 administration tenure.

---

## What it demonstrates

| Skill | Where to see it |
|-------|-----------------|
| Junior IT support triage, ticket note, escalation, and follow-through | [CASE-OUTCOME.md](./CASE-OUTCOME.md) |
| Product-support ownership loop | [GITHUB-INTEGRATION-CASE-OUTCOME.md](./GITHUB-INTEGRATION-CASE-OUTCOME.md) |
| Calm first response + clarifying questions | [customer-reply.md](./customer-reply.md) |
| Structured investigation and triage | [support-case-github-sync.md](./support-case-github-sync.md) |
| Engineering handoff quality | [internal-escalation-note.md](./internal-escalation-note.md) |
| Reducing repeat tickets through docs | [documentation-improvement-note.md](./documentation-improvement-note.md) |
| Log / webhook-style investigation depth | [evidence/](./evidence/) |

Core habits shown:

- Restate the user's problem before troubleshooting
- Gather minimum evidence before a routine escalation; escalate immediately for security, an outage, or severity policy
- Separate configuration issues from potential product bugs
- Use approved support access methods — never customer passwords
- Write for both the customer and the internal team
- Turn one ticket into a documentation proposal when the same confusion is worth checking for a repeat pattern

---

## Product-support screenshots and visuals

The visuals below belong only to the **separate GitHub integration case**. They are not evidence for the Outlook scenario.

| Asset | File |
| --- | --- |
| Social / LinkedIn preview (1200×630) | [docs/screenshots/social-preview.png](./docs/screenshots/social-preview.png) |
| Triage operating loop | [docs/screenshots/triage-flow.png](./docs/screenshots/triage-flow.png) |

Mermaid source: [docs/triage-flow-diagram.md](./docs/triage-flow-diagram.md)

Set `docs/screenshots/social-preview.png` as the GitHub repository social preview (Settings → General → Social preview).

---

## How to run locally

Not applicable — this repo is markdown artifacts only. Clone and read:

```bash
git clone https://github.com/heyitschien/product-support-triage-sample.git
cd product-support-triage-sample
```

For deeper context, see [docs/recruiter-notes.md](./docs/recruiter-notes.md).

---

## Notes on privacy / scope

| In scope (public) | Out of scope (private or not claimed) |
|-------------------|---------------------------------------|
| Synthetic customer scenarios | Real customer names, tickets, or employer data |
| Sample replies and internal notes | Production support tenure claims |
| Triage methodology and templates | Private Career OS or hunt strategy |
| Synthetic evidence packet | Real webhook / production logs |
| Documentation improvement ideas | Access to a real product's admin tools |

**Safe to share** with recruiters, pin on GitHub, or link from LinkedIn Featured.

---

## Related public work

- **Developer workflow walkthrough (YouTube):** [Supabase to Neon migration](https://www.youtube.com/watch?v=osexel8sixc) — plain-English technical explanation showing documentation and adoption thinking

---

## Contact

- **GitHub:** https://github.com/heyitschien
- **LinkedIn:** https://www.linkedin.com/in/chien-escalera-duong/
