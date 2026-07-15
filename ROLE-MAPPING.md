# Role Mapping

**Repo:** [product-support-triage-sample](https://github.com/heyitschien/product-support-triage-sample)  
**Type:** Synthetic support sample — no real customer or employer data

This table maps common posting responsibilities for Product Support, Technical Support, Onboarding, Implementation, and related bridge roles to concrete proof files in this repo.

| Posting responsibility | Proof file | What it demonstrates |
| --- | --- | --- |
| **Ticket ownership** | [support-case-github-sync.md](./support-case-github-sync.md) · [CASE-OUTCOME.md](./CASE-OUTCOME.md) | Owns the case from first report through verified resolution; tracks evidence, severity, and next owner |
| **Ticket triage** | [support-case-github-sync.md](./support-case-github-sync.md) | Layer map, investigation checklist, likely-cause table, and reproduction steps before guessing |
| **Status updates** | [customer-reply.md](./customer-reply.md) | Calm customer-facing updates that restate the problem, set expectations, and avoid overpromising |
| **Configuration validation** | [support-case-github-sync.md](./support-case-github-sync.md) | OAuth scope, repo allowlist, team mapping, and reference-format checks before calling it a bug |
| **QA mindset** | [support-case-github-sync.md](./support-case-github-sync.md) · [CASE-OUTCOME.md](./CASE-OUTCOME.md) | Test PR workflow, expected vs actual behavior, and isolation of config vs product failure |
| **Escalation** | [internal-escalation-note.md](./internal-escalation-note.md) | Escalation only after minimum evidence; clear repro, impact, and what support already ruled out |
| **Handoff documentation** | [internal-escalation-note.md](./internal-escalation-note.md) | Engineer-ready note so the next owner does not restart the investigation |
| **Knowledge-base improvement** | [documentation-improvement-note.md](./documentation-improvement-note.md) | Turns one ticket pattern into help-center and onboarding improvements |
| **SLA mindset** | [support-case-github-sync.md](./support-case-github-sync.md) | Illustrative priority framing and migration-week urgency without inventing a product’s real SLA policy |

---

## Best-aligned roles

| Target role | Fit | Strongest proof in this repo |
| --- | :---: | --- |
| Product Support Specialist | Excellent | Full triage loop, customer replies, escalation criteria, case outcome |
| Technical Support Specialist | Excellent | Layer map, integration troubleshooting, internal escalation note, evidence packet |
| Customer Operations Specialist | Strong | Ticket ownership, status communication, knowledge-base signal |
| Onboarding Specialist | Strong | Clarifying questions, user education path, documentation improvement |
| Junior Implementation Specialist | Strong | Configuration validation, reproduction steps, resolution paths A/B/C |
| Customer Success Specialist | Moderate | Status communication and prevention loop |
| Support Engineer | Moderate | Evidence packet + escalation handoff (log/API depth is illustrative) |

---

## Recruiter quick path — 5 minutes

1. [CASE-OUTCOME.md](./CASE-OUTCOME.md) — the full story in one page
2. [customer-reply.md](./customer-reply.md) — customer communication
3. [internal-escalation-note.md](./internal-escalation-note.md) — engineering handoff
4. [documentation-improvement-note.md](./documentation-improvement-note.md) — prevention loop

No install required. No private data.
