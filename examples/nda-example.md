# Worked Example — NDA

> Fictional scenario, built to exercise the skill. Party names, terms, and facts are invented for
> demonstration only.

## Input: contract excerpt

**Mutual Non-Disclosure Agreement** between **Coimbra Robotics Lab, Lda.** and **Meridian Ventures
S.A.**, entered into to evaluate a potential investment/partnership.

> **1. Confidential Information.** Means any and all information disclosed by either party, in any
> form, including without limitation business plans, technical data, and any other information the
> receiving party should reasonably understand to be confidential.
>
> **4. Term.** The obligations of confidentiality under this Agreement shall survive indefinitely.
>
> **5. Residuals.** Notwithstanding anything to the contrary herein, either party may use for any
> purpose Residuals resulting from access to the other party's Confidential Information, where
> "Residuals" means information retained in the unaided memory of persons who had access to such
> Confidential Information.
>
> **7. Non-Solicitation.** During the term of this Agreement and for twenty-four (24) months
> thereafter, neither party shall solicit for employment any employee of the other party.
>
> **9. Governing Law.** This Agreement shall be governed by Portuguese law, with the courts of
> Coimbra having exclusive jurisdiction.

## Output: skill review

*Not legal advice. Portuguese law + applicable EU regulations only. Verify citations and thresholds
before relying on this.*

### Summary & Scope
Mutual NDA between two Portuguese entities ahead of an investment/partnership evaluation. Broad
definition of confidential information, indefinite confidentiality term, a residuals clause, and a
24-month mutual non-solicitation obligation. Governed by Portuguese law, courts of Coimbra.

### Legal Grounding
- **General validity** — Established. Object (mutual protection of information during an evaluation)
  is lawful, possible, and determinable; both parties appear to have capacity as registered companies
  (Art. 280º CC).
- **Objective eligibility** — Needs verification. Whether any personal data (e.g. named employee or
  founder information) will actually be exchanged isn't stated; if it will, GDPR obligations attach
  to that subset of the exchange even though this is a confidentiality instrument, not a DPA.
  Established: §1's "business plans, technical data" falls within the kind of information the Regime
  Jurídico da Proteção de Segredos de Negócio (DL n.º 110/2018) protects — a distinct, narrower regime
  from the NDA's own contractual definition, relevant to Red Flag #3. Nothing else beyond general
  contract law is evidently triggered by the object as described.
- **Subjective eligibility** — Established. Both parties are Portuguese commercial entities; no
  consumer, public-sector, or non-EU party is involved, so no additional regime beyond general
  contract law is triggered on this axis.
- **Governing law & jurisdiction** — Established and internally consistent: Portuguese law, Coimbra
  courts, matching both parties' apparent location.

### Red Flags

| # | Flag | Why it's a risk | How to fix | Severity |
|---|------|------------------|------------|----------|
| 1 | §1 — very broad definition, no carve-outs | No exclusions for information that is independently developed, already public, or already known before disclosure. As written, the receiving party could be in breach for using information it obtained legitimately elsewhere. | Add standard carve-outs: independently developed, publicly available through no fault of the receiving party, rightfully known prior to disclosure, and legally compelled disclosure (with notice). | 🔴 |
| 2 | §4 — indefinite confidentiality term | An unlimited obligation is hard to manage operationally (nobody tracks it forever) and can be challenged as unreasonable in scope/duration if ever contested. | Set a defined term — 3–5 years post-disclosure is common practice for general business information; trade secrets can be carved out for indefinite protection specifically. | 🟡 |
| 3 | §5 — residuals clause | This clause, combined with §1's broad definition, substantially undercuts the NDA's purpose: anything a person remembers (not just deliberately memorised) can be reused freely. For an investment-evaluation NDA where the disclosing party's core value may be its unaided-memory-transmissible know-how, this is a significant giveback — and to the extent that know-how would otherwise qualify as a trade secret under DL n.º 110/2018, a residuals clause this broad risks undercutting the "reasonable steps to keep it secret" element that regime itself requires, independent of what the NDA's contract text says. | Narrow or remove the residuals clause; if kept, restrict it to general skills/know-how and exclude anything resembling trade secrets or specific business/technical plans. | 🔴 |
| 4 | §7 — non-solicitation embedded in an NDA | This is scope creep: a confidentiality agreement is being used to carry a restrictive covenant. It's not inherently improper, but it should be negotiated and understood as its own commitment, not waved through while reviewing "just an NDA." | Either move non-solicitation into its own clause reviewed on its own terms, or confirm both parties intend and understand it as a real 24-month restriction. | 🟡 |

### Key Passages Explained

- **§1 (Confidential Information):** As drafted, almost anything shared could count as confidential,
  with no exceptions. In practice this makes the obligation both over-broad and hard to enforce
  precisely, because there's no clear boundary of what's excluded.
- **§5 (Residuals):** This is the clause with the most practical impact. It means that even without
  copying any documents, a person who reviewed the other side's confidential materials can later use
  whatever they remember — which, paired with §1's breadth, can hollow out the protection the rest of
  the agreement appears to offer.
- **§7 (Non-Solicitation):** A separate promise not to poach each other's staff for two years after
  the relationship ends — worth noticing because it's easy to sign an "NDA" without registering that
  it also creates this longer-tail obligation.

### Overall Status
🔴 — Two material (🔴) flags: an unqualified confidential-information definition and a residuals
clause that, together, significantly weaken the practical protection this NDA is meant to provide.
Recommend renegotiating §1 and §5 before signing.

### Needs Verification
- Whether personal data (beyond general business information) will be part of what's exchanged.
- Whether the residuals clause is standard practice for this counterparty/sector, or a non-standard
  ask worth pushing back on outright.
- **Art. 280º CC** (cited above, not independently verified this session — no fetch tool used): the
  object of a legal transaction must be physically and legally possible, lawful, and sufficiently
  determined or determinable, or the transaction is void.
- **DL n.º 110/2018** (cited above, not independently verified this session — no fetch tool used):
  protects trade secrets where the holder has taken reasonable steps to keep the information secret
  and it has commercial value from not being generally known — a standard the NDA's own contractual
  definition of "confidential information" doesn't automatically satisfy just by being broadly worded.
