# Synthetic Evidence Packet

**Purpose:** Extra technical depth for Product Support Engineer / developer-support interview discussions.  
**Important:** All payloads, logs, and identifiers below are **fictional**. They do not come from a real customer, employer, or production system.

For the completed business outcome of this sample, see [../CASE-OUTCOME.md](../CASE-OUTCOME.md).

---

## Contents

| File | What it shows |
| --- | --- |
| [webhook-event-expected.json](./webhook-event-expected.json) | Example GitHub webhook-style event when sync should succeed |
| [webhook-event-actual.json](./webhook-event-actual.json) | Example event / delivery gap when authorization scope is wrong |
| [expected-vs-actual.md](./expected-vs-actual.md) | Side-by-side comparison recruiters can scan quickly |
| [test-timeline.md](./test-timeline.md) | Timestamped support verification sequence |
| [sync-log-excerpt.txt](./sync-log-excerpt.txt) | Mock sync-job log lines (synthetic) |
| [config-mock.md](./config-mock.md) | Text mock of integration settings (no real UI screenshot required) |

---

## How I would use this in a real product

1. Confirm company policy for approved impersonation / test workspace access
2. Pull real webhook delivery logs and sync-job IDs from internal tools
3. Redact secrets, tokens, and unrelated customer data before attaching to a ticket
4. Attach only the minimum evidence needed for the next owner
