# Expected vs Actual (Synthetic)

All data fictional. Used to show how I compare investigation hypotheses to evidence.

| Field | Expected (healthy config) | Actual (before fix) |
| --- | --- | --- |
| Authorized identity | Company org `acme-corp-sample` | Personal account `alex-dev-personal-sample` |
| Target repo in scope | `acme-corp-sample/api` included | Only personal `sandbox` repo visible |
| Integration UI | Connected + meaningful scope | Connected with no error (misleading) |
| Example PR | Title includes `ENG-142` | Customer PRs reference work items correctly |
| Work item view | PR status appears after one sync interval | PR status missing / inconsistent |
| Customer experience | Clear pass/fail after setup validation | “Connected but nothing useful syncs” |

**Decision:** Treat as configuration first. Escalate only if the mismatch remains after org reauthorization and a controlled test PR.
