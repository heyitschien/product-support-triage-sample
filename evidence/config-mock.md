# Mock Configuration Screenshot (Text)

Synthetic stand-in for an annotated settings screenshot. In production, attach a redacted UI capture instead.

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
