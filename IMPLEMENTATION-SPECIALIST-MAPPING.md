# Implementation Specialist Mapping

**Repo:** [product-support-triage-sample](https://github.com/heyitschien/product-support-triage-sample)  
**Type:** Synthetic support sample — no real customer or employer data

This table maps common posting responsibilities for Implementation Specialist, Onboarding Specialist, Product Support, and Technical Support roles to concrete proof files in this repo.

| Posting responsibility | Proof file | What it demonstrates |
| --- | --- | --- |
| **Ticket ownership** | [support-case-github-sync.md](./support-case-github-sync.md) | Owns the case from first report through resolution path selection; tracks evidence, severity, and next owner |
| **Ticket triage** | [support-case-github-sync.md](./support-case-github-sync.md) | Layer map, investigation checklist, likely-cause table, and reproduction steps before guessing |
| **Status updates** | [customer-reply.md](./customer-reply.md) | Calm customer-facing updates that restate the problem, set expectations, and avoid overpromising |
| **Configuration validation** | [support-case-github-sync.md](./support-case-github-sync.md) | OAuth scope, repo allowlist, team mapping, and reference-format checks before calling it a bug |
| **QA mindset** | [support-case-github-sync.md](./support-case-github-sync.md) | Test PR workflow, expected vs actual behavior, and isolation of config vs product failure |
| **Escalation** | [internal-escalation-note.md](./internal-escalation-note.md) | Escalation only after minimum evidence; clear repro, impact, and what support already ruled out |
| **Handoff documentation** | [internal-escalation-note.md](./internal-escalation-note.md) | Engineer-ready note so the next owner does not restart the investigation |
| **Knowledge-base improvement** | [documentation-improvement-note.md](./documentation-improvement-note.md) | Turns one ticket pattern into help-center and onboarding improvements |
| **SLA mindset** | [support-case-github-sync.md](./support-case-github-sync.md) | Priority assessment (P2), same-business-day response, migration-week urgency without false promises |

---

## Employer relevance by role

| Target role | Strongest proof in this repo |
| --- | --- |
| Implementation Specialist | Configuration validation, reproduction steps, resolution paths A/B/C |
| Client / Onboarding Specialist | Clarifying questions, user education path, documentation improvement |
| Product Support Specialist | Full triage loop, customer replies, escalation criteria |
| Technical Support Specialist | Layer map, integration troubleshooting, internal escalation note |
| Customer Operations Specialist | Ticket ownership, status communication, knowledge-base signal |
| AI / workflow operations | Structured operating loop reusable as SOP or automation spec |

---

## 10-minute reading path

1. [docs/triage-flow-diagram.md](./docs/triage-flow-diagram.md) — visual flow (2 min)
2. [support-case-github-sync.md](./support-case-github-sync.md) — full case (5 min)
3. [customer-reply.md](./customer-reply.md) — customer voice (2 min)
4. [internal-escalation-note.md](./internal-escalation-note.md) — handoff quality (1 min)

No install required. No private data.
