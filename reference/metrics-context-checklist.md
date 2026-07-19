# Reference: Metrics Context Checklist

Use this when auditing any identity metric in a narrative. Every metric below needs the listed context to be meaningful to a non-IAM reader. If the narrative doesn't supply it, that's a finding under Rule 3.

## MFA Coverage
- Coverage of what population? (all users, privileged users, contractors, service accounts)
- Coverage of what auth flows? (primary login only, or also VPN, admin consoles, API access)
- What's in the uncovered percentage — is any of it privileged or externally-facing?

## Privileged / Admin Access Counts
- How many of these are standing (always-on) vs. just-in-time (time-bound)?
- Is there a ratio or trend (growing or shrinking privileged population)?
- Are these tied to named owners, or orphaned/unowned?

## Stale or Dormant Accounts
- Staleness threshold used (30 days? 90 days? a year?) — and is that threshold appropriate to the account type?
- How many of the stale accounts carry privileged or elevated access?
- Are these human or non-human (service/machine) accounts?

## Access Certification / Recertification Completion
- Completion rate alone is a checkbox metric — what did the certification find?
- How many access grants were revoked or flagged as a result?
- What's the rubber-stamp rate (approvals with no evidence the reviewer actually checked)?

## Joiner-Mover-Leaver (JML) Metrics
- What's the actual time-to-revoke on leavers (not just "process exists")?
- Are mover scenarios (lateral moves, not just promotions) tracked separately from joiners/leavers?
- Any known backlog or manual steps standing in for automation?

## Non-Human Identity (NHI) / Service Account Metrics
- Total count relative to human identity count (often the more striking number)
- Rotation cadence on credentials/secrets — and how many are overdue
- Ownership: how many have a named human owner of record vs. orphaned

## Incident / ITDR Metrics
- Detection-to-containment time, and how that compares to a prior period or benchmark
- Whether the metric reflects one incident type (e.g., phishing) or the full identity attack surface (token theft, MFA fatigue, credential stuffing)

## General Rule for Any Metric Not Listed Above
If you can ask "compared to what?" or "out of what total?" and the document doesn't answer, it's a naked metric. Flag it.
