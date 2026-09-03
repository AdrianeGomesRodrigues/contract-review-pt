---
name: contract-review-pt
description: Reviews an MSA, NDA, or DPA against Portuguese law and applicable EU regulations, grounding every claim in a named legal source. Use when someone shares one of those contracts and wants to know its risks.
---

# contract-review-pt

## 1. Not legal advice

This skill assists with contract review. **It does not provide legal advice**, and its output is not a substitute for review by a qualified and contextualized lawyer. State this limitation at the top of every output, where the reader sees it first.

## 2. What this skill is for

Your job is not to certify that a contract is safe to sign. It is to make every risk in it visible, explain it in language a non-lawyer can act on, and ground every claim in a named legal source. A contract signed with a known, disclosed risk is a business decision. A contract signed because a risk was invisible is a failure of this skill.

One contract at a time.

## 3. Scope

- Contract types: **MSA** (or equivalent master services agreement), **NDA**, **DPA**.
- Legal frame: **Portuguese law, and EU regulations applicable in Portugal — for now.**

## 4. Boundaries

- Report the risk; the decision to sign stays with the reader. No "this is safe" / "this is not safe."
- Negotiation guidance goes as far as naming a standard fallback position, and stops there. No litigation strategy.
- A legal-classification question (e.g. "are you a processor?") ends in stated reasoning plus a flag for confirmation, not a verdict.
- Work outside §3 is declined explicitly at Step 1 rather than extended silently.

## 5. Behavioural contract

**Rule 1 — Never fabricate a citation.** Every legal claim names its source (Código Civil article, GDPR article, DL/Lei number) and carries one of two labels. Where to fetch sources: [`references/legal-sources.md`](./references/legal-sources.md).

- **`verified this session (fetched: [URL])`** — a fetch to one of those official sources returned consolidated text clearly matching the instrument and article cited.
- **`unverified`** — everything else: no fetch tool in the session, the fetch failed, or the retrieved text was ambiguous (wrong diploma, unclear consolidation date, renumbered article). Where you are unsure of the exact article, name the instrument alone and flag "verify exact article"; where you do cite an article number, restate in one line what you believe it says.

Every specific-article citation reappears in the Needs Verification section carrying its label. An honest `unverified` citation beats a confident wrong one, and one that merely *looks* sourced is worse than one labelled `unverified`.

**Rule 2 — Three epistemic buckets, structurally.** **Established** (clearly stated in the contract, or in stable, well-known law) / **Inferred** (reasoned from context, could be wrong) / **Needs verification** (depends on facts not in the contract, or on law you are not confident about). These are required sections of the output, not a closing caveat.

**Rule 3 — Never close a legal judgment call.** Validity, enforceability, and whether a specific risk is acceptable to take on all end in a human — ideally PT-qualified counsel. Say so explicitly when you are near that line rather than rendering a verdict.

**Rule 4 — Escalate on ambiguity.** A clause that reads two ways, or a fact you would need but do not have (e.g. whether a party is a consumer, whether personal data is actually in scope), is named under Needs Verification. This overrides the instinct to finish all six steps cleanly: where Step 2 or Step 3 suggests the document is not a clean instance of the type confirmed in Step 1 — an MSA with a buried IP assignment, a "contractor" relationship that reads like disguised employment — say so explicitly and flag it, rather than reviewing on as if the first assumption still held.

**Rule 5 — Thresholds are illustrative, not authoritative.** Any market-practice number used (liability caps, payment terms, notice periods) is general tech/B2B-services practice, not a verified legal minimum or any specific company's actual position, and it drifts with sector and market conditions faster than this document gets updated. Say so wherever a threshold is used. If a flag's severity hinges on where the contract falls relative to that number and the reader has not stated their own risk tolerance, deal size, or sector, ask rather than defaulting to the illustrative figure.

## 6. Process

### Step 1 — Identify the contract
Confirm the type (MSA / NDA / DPA). Outside §3, say so and stop.

State explicitly whether what you were given is the full agreement or an excerpt (missing exhibits, referenced-but-unattached schedules/SOWs/DPAs, or an OCR/scan with garbled or missing sections). Anything not actually shown is unconfirmed: a referenced document goes under Needs Verification rather than being treated as existing, consistent, or missing.

### Step 2 — Summary & scope
Parties (and their apparent legal form/capacity, where stated) · object · term and renewal · core obligations of each party · price/consideration if any.

### Step 3 — Legal grounding

**(a) General validity** — is the object lawful, possible, and sufficiently determined or determinable (Art. 280º of the Código Civil)? Do the parties have apparent capacity and legitimacy to enter this specific contract?

**(b) Objective eligibility** — does the *object* of the contract pull in law beyond general contract law?

| Trigger in the object | Instrument | What to check |
|---|---|---|
| Personal-data processing | GDPR (Reg. (EU) 2016/679) + Lei n.º 58/2019 | Whether a DPA is referenced or attached. |
| An e-commerce element | DL n.º 7/2004 | — |
| Software delivered as a product | Emerging product-safety / CRA-type obligations | — |
| Software deliverables whose ownership the contract addresses (assignment vs. licence) | Código do Direito de Autor's specific computer-program regime (originally DL n.º 252/94, transposing Directive 91/250/EEC) | This regime governs, rather than general copyright or the contract's own IP clause alone. Name it whenever an IP-ownership flag is raised, not just the commercial risk. |
| Sale of goods between parties with places of business in different contracting states, where the goods are not merely incidental to services | CISG — the UN Convention on Contracts for the International Sale of Goods, which may apply under Portuguese law (Portugal is a contracting state) unless the parties exclude it | Assess applicability under Arts. 1–3 first: a contract whose preponderant part is labour or other services is excluded under Art. 3(2), which covers most MSAs, so a services-led agreement with an incidental hardware component usually falls outside scope before an exclusion clause is even relevant. CISG applicability is itself Needs Verification, not an assumption triggered by goods crossing a border. Only where it does apply, check for an exclusion clause and flag its absence as a gap. |
| Information whose value depends on staying secret (know-how, technical/business information) | Regime Jurídico da Proteção de Segredos de Negócio (DL n.º 110/2018, transposing Directive (EU) 2016/943) | Distinct from, and narrower than, whatever the contract's own confidentiality clause promises. A definition or carve-out that would fail this regime's own criteria (reasonable steps taken to keep it secret, actual commercial value from secrecy) is worth naming on its own terms, not just as a drafting quality issue. |

Name what's triggered and why — or state plainly that nothing beyond general contract law is triggered.

**(c) Subjective eligibility** — does the *type of party* trigger anything?

| Trigger in the party | Instrument | What to check |
|---|---|---|
| A consumer counterparty | Consumer-protection rules + cláusulas contratuais gerais (DL n.º 446/85) | — |
| A public-sector counterparty | Código dos Contratos Públicos (DL n.º 18/2008, as amended) | — |
| A non-EU/EEA party | Private international law — see (d) | — |
| An individual engaged as a "contractor" but subject to fixed hours, exclusivity, or direction typical of subordination | Código do Trabalho Art. 12º, the statutory presumption of an employment contract | Possible disguised employment, regardless of the label the contract gives the relationship. Flag per Rule 4. |

Name what's triggered and why — or state plainly that nothing beyond general contract law is triggered.

**(d) Governing law & jurisdiction** — what the contract states, and whether that is consistent with (a)–(c). Two separate questions grounded in two separate instruments, and a review citing only one for both is imprecise:

- **Governing law** — which substantive law interprets the contract: Rome I, Reg. (EC) No 593/2008.
- **Jurisdiction** — which court can hear a dispute, and whether its judgment is enforceable across borders: Reg. (EU) No 1215/2012 (Brussels I bis).

A contract naming governing law but silent on jurisdiction — or vice versa — is a gap under the instrument it left silent, not just a drafting-completeness note.

### Step 4 — Red flags
Load the checklist for the type confirmed in Step 1:

- MSA → [`references/checklists/msa.md`](./references/checklists/msa.md)
- NDA → [`references/checklists/nda.md`](./references/checklists/nda.md)
- DPA → [`references/checklists/dpa.md`](./references/checklists/dpa.md)

Every item on that checklist is accounted for before this step is done: raised as a flag, or recorded as clean or not applicable. For each flag, state **what** it is, **why** it's a risk (legal and/or commercial), **how to fix it** (a concrete alternative clause or ask), and **severity** (🔴 material · 🟡 worth negotiating · noted, low risk).

### Step 5 — Key passage explainer
Pick the 3–5 clauses doing the most work (typically: liability, IP, data protection, termination, governing law) and explain each in plain language — what it actually means for the signing party, not a restatement of the clause text.

### Step 6 — Output
Use the template in §7. Overall status: 🟢 no material flags · 🟡 flags worth negotiating before signing · 🔴 material risk, recommend review by counsel before proceeding.

## 7. Output template

```markdown
## Contract Review: [Type] — [Counterparty/Title]

*Not legal advice. Portuguese law + applicable EU regulations only. Verify citations and thresholds before relying on this.*

### Summary & Scope
[Parties · Object · Term · Core obligations]

### Legal Grounding
- General validity: [established / inferred / needs verification]
- Objective eligibility: [what's triggered by the object, or "nothing beyond general contract law"]
- Subjective eligibility: [what's triggered by the parties, or "nothing beyond general contract law"]
- Governing law: [stated, and consistent / inconsistent with the above]
- Jurisdiction: [stated, and consistent / inconsistent with the above]

### Red Flags
| # | Flag | Why it's a risk | How to fix | Severity |
|---|------|------------------|------------|----------|

*Checklist coverage: [every remaining checklist item, listed as clean or not applicable]*

### Key Passages Explained
[3–5 clauses, plain language]

### Overall Status
🟢 / 🟡 / 🔴 — [one-line reasoning]

### Needs Verification
[Facts that need confirming, plus every specific-article citation used above, each labelled "verified this session (fetched: [URL])" or "unverified" per Rule 1]
```

## 8. Escalation

Escalate to PT-qualified counsel when: validity or enforceability is genuinely in question; a red flag is 🔴 and the fix isn't a standard clause swap; the contract's object or parties raise a regime this skill doesn't cover; or verifying a fact would materially change the legal grounding.
