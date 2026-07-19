# Reference: Audience Calibration Guide

Identity risk narratives go to different audiences, and the same sentence can be appropriate for one and a failure for another. Use this to judge whether a term or level of detail fits the stated audience. If the writer hasn't named an audience, ask (Rule 10) before applying this guide.

## Audience Tiers

**Board of Directors**
- Near-zero tolerance for IAM jargon. Every technical term needs either plain-language translation or removal.
- Cares about: financial exposure, regulatory/legal consequence, reputational risk, comparison to peers/industry, trend direction.
- Does not care about: tool names, specific protocols, implementation detail.

**Executive / C-Suite (non-security)**
- Some tolerance for security vocabulary if it's common in the industry (e.g., "MFA," "phishing") but not IAM-specific jargon (e.g., "federation trust," "JIT," "entitlement").
- Cares about: business impact, resourcing/budget asks, how this compares to what leadership already believes about the org's risk posture.

**Audit / Risk Committee**
- Mixed literacy — treat like a board audience by default unless told otherwise. These readers care most about evidence and control effectiveness, not process descriptions.
- Cares about: whether a control actually works, what was found, what's still open, whether findings map to known compliance obligations (without needing framework-clause-level detail).

**Steering Committee / Cross-Functional Security Leadership**
- Higher tolerance for identity-specific vocabulary since this audience often includes security peers from other domains (network, cloud, appsec).
- Still translate hyper-specific IAM jargon (e.g., "SCIM provisioning drift") unless the writer confirms this group is IAM-fluent.

**Skip-Level / Program Sponsor (e.g., CISO briefing before a board meeting)**
- Highest tolerance for technical detail, but still needs the narrative framed around what THEY will need to defend or explain upward. Look for whether the document anticipates the next-level audience's likely questions.

## Common Jargon That Needs a Translation or Removal Check

| Term | What it actually means (for your own calibration — don't hand this to the writer verbatim, ask them to translate) |
|---|---|
| JIT (Just-In-Time) access | Access granted only for the time it's needed, then automatically removed |
| Break-glass account | An emergency access account meant for rare crisis use, normally locked down |
| Entitlement sprawl | Accumulation of access rights beyond what's actually needed for the job |
| Federation trust | An agreement that lets one system accept another system's login as valid |
| Standing access | Access that's always active, as opposed to granted only when needed |
| Non-human identity (NHI) | Accounts used by software/systems rather than people (service accounts, API keys, bots) |
| Recertification / access certification | The periodic review of who has access to what, to confirm it's still needed |
| De-provisioning | Removing a person's access, typically when they leave or change roles |

When you spot one of these terms (or similar) unexplained in a document going to a board, exec, or audit-committee audience, flag it under Rule 5. Name the term, state the audience mismatch, and ask the writer to translate or justify keeping it.
