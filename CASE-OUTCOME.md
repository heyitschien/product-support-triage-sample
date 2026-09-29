# Junior IT Support Proof — Outlook Send Failure

**Author:** Chien Escalera Duong

**Type:** One-page synthetic support example — not a real customer ticket, employer case, or production support record

This example shows how I would communicate, isolate a failure safely, restore useful work when possible, and leave a clean senior-engineer handoff. It demonstrates support judgment—not prior MSP, law-firm IT, Microsoft 365 administration, or production helpdesk employment.

---

## Scenario

A busy professional reports:

> “Outlook stopped sending email. I have a client call in 15 minutes. Please fix this.”

Goal: reduce stress, isolate the failure without adding risk, and keep ownership through resolution or acknowledged handoff.

## 1. Start with the person

> “I understand you are on a deadline. I’ll first determine whether this affects your account or only the Outlook application, then I’ll give you the fastest safe next step. Please do not send me your password.”

- Confirm a callback method and the next update time.
- Reuse information already in the ticket so the user does not repeat the story.

## 2. Bound the problem before changing anything

Capture only what is needed: exact error and start time · send versus receive · one user versus several · webmail versus desktop · network state · recent account/device/software changes · whether the issue follows the account to another approved device.

This turns “email is broken” into a testable problem.

## 3. Use the fastest low-risk isolation path

1. Confirm basic network connectivity.
2. Check approved Microsoft 365 service-health sources for a known incident.
3. Test Outlook on the web to separate account/service behavior from the local desktop application.
4. If webmail works, capture the local Outlook error and inspect only the approved client-side checks.
5. If webmail also fails, preserve the evidence and route the account/service investigation through the correct authorized owner.
6. Apply only low-risk, documented steps within permission; escalate instead of experimenting when administrator access, deeper endpoint work, security review, or a broader incident is involved.

**Security boundary:** Never ask for a password, bypass identity controls, disable protection to make the symptom disappear, or place confidential client information in an unapproved tool.

## 4. Leave a ticket the next person can use

- **Impact:** User cannot send Outlook email; client call in 15 minutes.
- **Scope:** Single user / multiple users / unknown.
- **Started:** [time reported].
- **Checks completed:** Network · service health · webmail · local client · account/session checks within permission.
- **Evidence:** Exact error text · approved screenshot location · timestamps.
- **Actions taken:** [bounded steps and results].
- **Current state:** Resolved / safe workaround active / still blocked.
- **Next owner and action:** [specific person or team and the next required check].
- **User expectation:** [next update time and callback method].

A clean escalation lets the senior engineer continue from this point instead of repeating discovery.

## 5. Make the escalation judgment explicit

Escalate immediately for security, privacy, a widespread outage, or the company’s severity policy. Otherwise, collect the minimum useful evidence and state exactly what access or expertise is needed. The technician owns communication until the handoff is acknowledged.

## 6. Close the loop

If resolved, confirm a test send, explain the result plainly, and record the working state. If unresolved, give a specific next step and update time—not a vague “engineering is looking at it.” Propose a runbook or knowledge-base update only after the real cause is verified.

## Where approved AI can help

An approved AI assistant can summarize notes or draft a runbook step. It must not receive confidential client data outside approved systems, invent a diagnosis, or make consequential changes without permission and human review.

---

## What this page demonstrates

**Listen → bound the problem → isolate safely → solve or escalate → document → follow through.**
