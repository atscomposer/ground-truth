# Reference: Identity Security Framework Benchmarks

This file exists so risk claims in a narrative can be checked against something external and recognized — not just the writer's own confidence. Use it under Rule 11. You are not auditing whether the org's actual implementation meets these frameworks (that's an architecture review, out of scope). You are checking whether the narrative's *claims* are specific enough to be located on these scales, and whether the evidence described actually supports the maturity level being claimed.

## Primary Framework 1: NIST SP 800-63-3 Digital Identity Guidelines (ref: [link](https://pages.nist.gov/800-63-3/sp800-63-3.html))

The authoritative U.S. standard for identity and authentication assurance. Three independent scales — a narrative claiming strength in one doesn't imply strength in the others.

**IAL — Identity Assurance Level** (how confident are we the person is who they claim to be, at enrollment)
- IAL1: Self-asserted identity attributes, no verification
- IAL2: Evidence collected and verified against authoritative sources (remote or in-person)
- IAL3: In-person (or supervised remote) verification with physical or biometric evidence

**AAL — Authenticator Assurance Level** (how strong is the login/authentication method)
- AAL1: Single-factor (password only) or basic two-factor
- AAL2: Two-factor, at least one being a cryptographic authenticator (e.g., TOTP app, push notification) — but still phishable if not hardware/possession-bound
- AAL3: Hardware-based, phishing-resistant authenticator (e.g., FIDO2/WebAuthn, PIV/CAC) with verifier impersonation resistance

**FAL — Federation Assurance Level** (how strong is the assertion when identity is federated across systems, e.g., SSO)
- FAL1: Signed assertion
- FAL2: Signed and encrypted assertion
- FAL3: Assertion plus proof of possession of a cryptographic key bound to the authentication

**Why this matters for narrative review:** "MFA is deployed" or "we've enabled MFA on all admin accounts" is common language in identity narratives, but it collapses a meaningful distinction. SMS-based OTP and push notifications sit at a weaker point than phishing-resistant AAL3 methods, and the gap between them is exactly the kind of thing that gets exploited (MFA fatigue attacks, SIM-swapping) and exactly the kind of thing a security-literate reader will probe. If a narrative doesn't specify authenticator type, it's an ungrounded MFA claim.

## Primary Framework 2: CISA Zero Trust Maturity Model — Identity Pillar (ref: [link](https://www.cisa.gov/zero-trust-maturity-model))

CISA's model defines four maturity stages across each zero trust pillar. For the Identity pillar specifically, look at claims against these stage definitions:

| Capability | Traditional | Initial | Advanced | Optimal |
|---|---|---|---|---|
| Authentication | Password-based, static | MFA introduced, some phishing-resistant options | Phishing-resistant MFA widely enforced | Phishing-resistant MFA enforced continuously, risk-based step-up |
| Identity stores | Siloed, on-prem directories | Some consolidation begins | Consolidated, cloud-integrated | Fully unified, real-time synchronized |
| Access (authorization) | Static, role-based only | Some attribute-based elements introduced | Automated, attribute- and risk-based | Just-in-time, continuously evaluated per request |
| Visibility & analytics | Manual log review | Basic automated alerting | Centralized analytics, some automated response | Continuous, automated, real-time risk scoring driving access decisions |
| Automation & orchestration | Manual provisioning/de-provisioning | Partial automation of lifecycle | Automated lifecycle for most identity types | Fully automated across human and non-human identities |
| Governance | Periodic, manual access reviews | Scheduled certifications, limited evidence | Risk-based, more frequent reviews | Continuous, automated entitlement right-sizing |

**Why this matters for narrative review:** When a narrative claims "advanced" or "mature" identity posture, check the capabilities actually described against this table. A narrative that describes password-based login as primary, siloed directories, and only annual manual access reviews is describing **Traditional/Initial** capabilities — regardless of what maturity label the writer chose to use. That mismatch is a finding.

## Supplementary References (Use to Support, Not Replace, the Above)

These are recognized but secondary — cite them only if directly relevant to a specific claim, and don't require narratives to map to all of them:
| Control | Definition | Link |
|---|---|---|
|**CIS Controls v8.1**, Control 5 (Account Management) and Control 6 (Access Control Management) | Practical, checklist-style controls for account lifecycle and access management. | [Link](https://www.cisecurity.org/controls/v8-1) |
|**Identity Defined Security Alliance (IDSA) Identity Security Framework** | Practitioner-built outcomes and best practices across access management, privileged access, and identity governance, useful when a narrative discusses program strategy rather than a specific technical claim. | [Link](https://www.idsalliance.org/wp-content/uploads/2022/06/IDSA_Framework_Whitepaper-1.pdf) |
|**ISO/IEC 27001 Annex A** (A.5 and A.8 control areas) | Relevant if the narrative is written for an audit/compliance audience already fluent in ISO control language. | |

## How to Apply This Without Becoming an Architecture Review

You are checking the narrative's own words against these benchmarks — not requesting technical evidence packages or auditing systems. A finding under Rule 11 sounds like:

> "You describe this as 'strong MFA coverage,' but the document only mentions SMS-based one-time codes. Per NIST 800-63B, SMS OTP sits at a weaker point on the authenticator assurance scale and is a known phishing/SIM-swap target — 'strong' may overstate this to a reader who knows the standard."

Not:

> "Please provide your NIST 800-63 compliance documentation for review."

The first is a narrative-quality finding. The second is an architecture audit. Stay in the first lane.
