# Expected vs Actual (Synthetic)

All data fictional. Used to show how I compare an investigation hypothesis to evidence.

The rows below are **one illustrative configuration** for this sample. They do not describe how every GitHub integration authenticates, and they are not a measured production pattern. The sample identity `alex-dev-personal-sample` is only a stand-in for an install whose scope misses the required organization and repository.

| Field | Expected (healthy config) | Actual (before fix) |
| --- | --- | --- |
| Authorization / install scope | Includes org `acme-corp-sample` and repo `acme-corp-sample/api` | Does not include that org/repo. Sample identity shown: `alex-dev-personal-sample` |
| Target repo in scope | `acme-corp-sample/api` included | Only `alex-dev-personal-sample/sandbox` is visible |
| Integration UI | Connected, and the required repo is in scope | Connected with no error (misleading in this sample) |
| Example PR | Title includes `ENG-142` | Sample PRs reference work items correctly |
| Work item view | PR status appears after one documented sync interval | PR status missing / inconsistent |
| Customer experience | Clear pass/fail after setup validation | “Connected but nothing useful syncs” |

**Decision:** Treat this sample as configuration first. Escalate only if the mismatch remains after the required organization and repository are in scope and a controlled test PR still fails. Escalate sooner if security, an outage, or severity policy requires it.
