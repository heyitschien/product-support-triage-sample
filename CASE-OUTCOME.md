# Sample Case Outcome

**Case ID:** SAMPLE-001 (fictional)  
**Type:** Completed resolution path for the recruiter walkthrough — synthetic, not a real customer ticket

This file takes one definitive ending through Path A (configuration). Other paths remain documented in [support-case-github-sync.md](./support-case-github-sync.md) for branching judgment.

---

## Confirmed root cause

The GitHub integration was authorized through a personal account that did
not have access to the company repository.

## Action taken

1. Confirmed the correct company organization
2. Reauthorized the integration using the approved organization
3. Verified the target repository was included
4. Created a test PR with the correct work-item reference
5. Waited one documented sync interval

## Result

The PR status appeared correctly on the linked work item.

## Customer follow-up

Sent the resolved-case reply and confirmed that the customer could repeat
the workflow successfully.

## Preventive action

Proposed a “Connected but not syncing” help-center article and a
post-authorization setup validation step.

See [documentation-improvement-note.md](./documentation-improvement-note.md) for the full prevention proposal.

---

## Closure checklist (what “done” looked like)

- [x] Root cause confirmed (config, not product bug)
- [x] Fix verified with a controlled test PR
- [x] Customer confirmed they can repeat the workflow
- [x] Ticket closed with clear resolution notes
- [x] Repeat-pattern signal forwarded to documentation / product
