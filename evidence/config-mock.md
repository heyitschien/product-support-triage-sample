# Mock Configuration Screenshot (Text)

Synthetic stand-in for an annotated settings screenshot. In a real ticket, attach a redacted UI capture instead.

This before/after is **one illustration** of missing authorization scope in SAMPLE-001. It is not a claim that every GitHub integration chooses a personal account versus an organization, and it is not a real settings screen.

## Before fix

```text
Settings → Integrations → GitHub
─────────────────────────────────
Status:           ● Connected
Authorized as:    alex-dev-personal-sample  (User)
Organization:     — (none)
Repositories:     Selected — sandbox
Team mapping:     Engineering
Last error:       (none shown)
```

## After fix

```text
Settings → Integrations → GitHub
─────────────────────────────────
Status:           ● Connected
Authorized as:    acme-corp-sample  (Organization)
Organization:     acme-corp-sample
Repositories:     Selected — api
Team mapping:     Engineering
Last error:       (none shown)
```

**Customer screenshot hygiene:** Please redact access tokens, secrets, private repository information, or unrelated customer data before sending the screenshot.
