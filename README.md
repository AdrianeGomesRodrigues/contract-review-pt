# Contract Review Skill — MSA · NDA · DPA (Portuguese Law + EU)

A Claude skill that reviews commercial contracts against Portuguese law and applicable EU regulations. Give it an MSA, NDA, or DPA and it returns a structured review: 
* What the contract does;
* What law it triggers beyond its own text;
* Where the red flags are and how to fix them; 
* Plain-language walkthrough of the clauses that matter most.

**This is a self-built demonstration framework and it is not legal advice**, and its output is not a substitute for review by a qualified and contextualized lawyer.

## Scope

Contract review is one of the places a small legal/ops function feels its size most: every MSA, NDA, and DPA that crosses the desk needs the same disciplined pass: (i) what does this actually commit us to; (ii) what law does it pull in beyond its own text; (iii) and what's the specific fix for each risk.
This skill is my attempt to encode that discipline: not to replace legal judgment, but to make sure nothing gets signed because a risk was simply never surfaced.

The scope is deliberately narrow: one contract at a time. It asks what *this specific document*
triggers, and where the gaps are. As such it is not a project-wide regulatory map, just a disciplined pass on the paper in front of you.

## How it works

Given a contract, the skill runs six steps:

1. **Identify the contract type** — MSA, NDA, or DPA. Anything else, it says so rather than improvising.
2. **Summarise** — parties, object, term, core obligations.
3. **Ground it in law** — general validity (is the object lawful/possible/determinable, do the parties have capacity, etc.), then two separate checks: does the contract's **object** pull in law beyond general contract law (e.g. personal-data processing → GDPR), and does the **type of party** pull in anything (e.g. a consumer counterparty → consumer-protection rules)? Either, both, or neither can fire — it's assessed each time, never assumed.
4. **Red flags** — a type-specific checklist, each flag stated as what it is, why it's a risk, how to fix it, and its severity.
5. **Key passages explained** — the 3–5 clauses doing the most work, in plain language.
6. **Output** — a single structured review with an overall 🟢/🟡/🔴 status and a list of anything that still needs verifying before the review can be relied on.

The full logic is in [`SKILL.md`](./SKILL.md); the type-specific red-flag checklists are in
[`references/checklists/`](./references/checklists/), loaded at Step 4 for whichever type the contract
turns out to be. Where to fetch (when a session has that tool) any citation it makes is in
[`references/legal-sources.md`](./references/legal-sources.md).

## See it work — worked examples

Three fictional scenarios, run through the skill, with the full review shown. All party names, terms
and facts are invented for demonstration.

- **[MSA example](./examples/msa-example.md)** — a services agreement with unlimited liability and a missing DPA for in-scope personal-data processing. Overall: 🔴
- **[NDA example](./examples/nda-example.md)** — a mutual NDA with an over-broad confidentiality definition and a residuals clause that undercuts its own purpose. Overall: 🔴
- **[DPA example](./examples/dpa-example.md)** — a processing addendum missing several Art. 28 GDPR required elements (sub-processor control, breach-notification timing, deletion timeline). Overall: 🔴

## Use it yourself

This is a Claude skill — everything runs in your own Claude environment, on your own account. Nothing you input is sent to or stored by me.

1. Download this repository (or just `SKILL.md`).
2. Add it as a skill in Claude Code, Claude Desktop, or Cowork (see Anthropic's documentation for adding a custom skill).
3. Share a contract (MSA, NDA, or DPA) and ask it for a review.

## Scope and limits

- Contract types: MSA, NDA, DPA only.
- Legal frame: Portuguese law and EU regulations applicable in Portugal, for now.
- Never renders a verdict on whether to sign, never closes a legal-classification question, and escalates to human counsel rather than guessing on anything genuinely ambiguous. Full rules in `SKILL.md` §5.

## What's next

- Expanding contract types (SOW, vendor/supplier agreements).
- A clause-library reference so suggested fixes can cite a standard fallback position, not just describe one.
- Testing against real (properly anonymised) contract patterns, if I find a defensible way to do that without exposing anything confidential.

## About

Built by Adriane Gomes Rodrigues — [LinkedIn](https://www.linkedin.com/in/adriane-gomes-rodrigues/)
