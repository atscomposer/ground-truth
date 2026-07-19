# Ground Truth — Identity Security Risk Narrative Editor

An AI editor that critiques how identity/IAM security posture gets translated into narratives for executives, boards, and risk committees — MFA coverage, privileged access, access certifications, stale accounts, non-human identity, and related metrics.

**This editor does not rewrite your narrative.** It points at the specific lines that won't land with your audience, explains why, and hands it back for you to fix. If you want something to write the narrative for you, this isn't that tool — see [The Angle](#why-it-doesnt-rewrite) below for why that's intentional.

---

## Who is this for
Built for security engineers, IAM program managers, and CISOs who write security risk updates and want a second set of eyes before the room does.

---

## What this folder is

|File|Purpose|Version|
|---|---|---|
| identity.md | Defines who the editor is, what it reviews, and what "good" looks like | v1 & v2 |
| rules.md | The critique methodology — the rules governing every review, including the no-rewrite rule | v2 |
| examples.md | Worked examples contrasting generic (fail) feedback against specific (pass) feedback | v2 |
| reference/metrics-context-checklist.md | What context each common identity metric needs to be meaningful | v1 & v2 |
| reference/audience-calibration-guide.md | How to judge jargon and detail level against board/exec/audit/steering-committee audiences | v1 & v2 |
| reference/risk-narrative-structure-framework.md | The Risk-Exposure-Ask structure used to diagnose structural problems | v1 & v2 |
| reference/common-failure-patterns.md | A named catalog of recurring failure patterns (Compliance Theater Framing, Buried Lede, etc.) | v1 & v2 |
| reference/identity-security-framework.md | A reference that grounds every risk/maturity claim in two authoritative, identity-specific benchmarks: NIST SP 800-63-3 (IAL/AAL/FAL assurance levels) and the CISA Zero Trust Maturity Model, Identity pillar (Traditional → Initial → Advanced → Optimal), with CIS Controls v8, IDSA, and ISO 27001 noted as supplementary | v1 & v2 |
| v1/rules.md | The critique methodology — the rules governing every review, including the no-rewrite rule | v1 |
| v1/examples.md | Worked examples contrasting generic (fail) feedback against specific (pass) feedback | v1 |

---

## Versioning

Ask which version of the editor the user would like prior to each run

| Version | Purpose | When to use |
|----|---|
| v1 | Older base version | Used if user says to use version 1 |
| v2 | Improved version with best practice identification and recommendations based on idustry identity security frameworks  | default unless v1 is specified directly |

---

## How to Use This

### Option A: Claude Project (recommended)
1. Create a new Claude Project.
2. Upload every file in this folder (including the `reference/` files) as project knowledge.
3. In the project instructions, add one line: *"You are the Identity Risk Narrative Editor. Follow identity.md, rules.md, examples.md, and the reference/ files exactly."*
4. Start a chat in the project and paste in your draft narrative. Tell it who the audience is (board, audit committee, exec sponsor, etc.) — the editor needs this to calibrate.

### Option B: Single conversation
Paste the contents of `identity.md`, `rules.md`, and `examples.md` at the start of a conversation, then paste your draft. Reference files can be added if the review needs metric- or audience-specific depth.

---

## What to Give It

- The narrative or excerpt you want reviewed (a paragraph, a slide's worth of talking points, a full monthly update)
- The intended audience (board, exec, audit committee, steering committee, sponsor) — if you don't say, it will ask
- Optionally, any constraints (word count, slide format, a specific finding you already know is sensitive)

---

## What You'll Get Back

A structured list of the 3-5 most important issues, each with the exact line quoted, why it fails for your audience, and a question or directive that pushes you to fix it — never a rewritten sentence. See `examples.md` for the exact format and the difference between what this editor does and what a generic "strengthen your intro" tool does.

---

## Why It Doesn't Rewrite

An editor that hands you a fixed version teaches you nothing and doesn't scale — you're back next quarter needing the same fix. An editor that shows you *why* a naked metric or a buried risk fails, by name, builds a skill you keep. That's the trade this tool makes deliberately: less convenient in the moment, more useful every time after.

---

## Scope

This editor reviews narrative and framing quality for identity risk communication. It does not review IAM architecture, do compliance framework mapping, or provide financial/legal risk quantification. If you paste something out of scope, it will tell you and stop rather than attempt a review it's not built for.

---

## The trigger

The person typing **PRD** — or asking to spec out a recurring piece of work — starts the interview. Run it per `skills/prd-interview.md`. Until then, don't launch into the interview; wait for the trigger.

---

## Naming conventions

One run produces a linked set, sharing a lowercase-hyphenated `[slug]` (e.g. `session-prep`):

- `output/prd-[slug].md` — the PRD
- `output/build-notes-[slug].md` — the freeform companion
- `output/transcript-[slug].md` — the near-verbatim record of the person's responses

The `[slug]` is the index that ties the three together.

---

## License

MIT — use, fork, and adapt freely. If you build on it, a link back is appreciated but not required.

