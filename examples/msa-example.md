# Worked Example — MSA

> Fictional scenario, built to exercise the skill. Party names, terms, and facts are invented for
> demonstration only.

## Input: contract excerpt

**Master Services Agreement** between **Aveiro Software Studio, Lda.** ("Provider"), a Portuguese
private limited company, and **NordFin Payments GmbH** ("Client"), a company incorporated in Germany.

> **3. Services.** Provider shall deliver software development services as described in Statements
> of Work executed hereunder, which may include processing of Client's customer data for testing and
> support purposes.
>
> **7. Liability.** Provider's liability under this Agreement shall be unlimited, except that neither
> party shall be liable for indirect or consequential damages.
>
> **9. Intellectual Property.** All deliverables created under this Agreement shall be and remain the
> property of Provider unless otherwise agreed in writing in the applicable SOW.
>
> **11. Payment.** Client shall pay invoices within sixty (60) days of receipt.
>
> **14. Termination.** Client may terminate this Agreement for convenience upon fifteen (15) days'
> written notice. Provider may terminate only for Client's uncured material breach.
>
> **18. Governing Law.** This Agreement is governed by the laws of Germany.

## Output: skill review

*Not legal advice. Portuguese law + applicable EU regulations only. Verify citations and thresholds
before relying on this.*

### Summary & Scope
Software development services agreement between a Portuguese provider and a German client. Includes
processing of the client's customer data for testing/support (§3). Governed, per §18, by German law.

### Legal Grounding
- **General validity** — Established. The object (software development services) is lawful, possible,
  and determinable; both parties appear to have capacity as registered companies (Art. 280º CC).
- **Objective eligibility** — Established. §3 puts personal-data processing of Client's customers in
  scope on Provider's side → GDPR (Reg. (EU) 2016/679) applies regardless of the chosen governing law,
  and a DPA/processing annex is required (see Red Flag #3). Nothing else beyond general contract law
  is triggered by the object as described.
- **Subjective eligibility** — Needs verification. Whether NordFin Payments' own regulatory status
  (a "Payments" business name suggests possible e-money/payment-services licensing) pulls in sector
  rules that could flow down to Provider by contract is not answerable from this excerpt — worth
  asking directly.
- **Governing law & jurisdiction** — Inferred as inconsistent, and on two separate axes. **Governing
  law** (Rome I, Reg. (EC) No 593/2008): §18 selects German law for an agreement with a Portuguese
  provider — a valid choice under Rome I, but one with real consequences for how §7 (liability) and §9
  (IP) are interpreted and enforced. GDPR applies irrespective of this choice regardless (Art. 3 GDPR,
  territorial scope). **Jurisdiction** (Brussels I bis, Reg. (EU) No 1215/2012): §18 is silent on which
  court hears a dispute — a separate gap from the governing-law choice, not the same issue restated —
  see Red Flag #4.

### Red Flags

| # | Flag | Why it's a risk | How to fix | Severity |
|---|------|------------------|------------|----------|
| 1 | §7 — unlimited liability | No cap on direct damages exposes Provider to losses far exceeding the contract's value; the indirect/consequential carve-out doesn't limit the largest realistic exposure (e.g. a data breach). | Negotiate a cap, commonly 1–2x the fees paid in the preceding 12 months, with narrow carve-outs (gross negligence, wilful misconduct, confidentiality breach). | 🔴 |
| 2 | §9 — deliverables owned by Provider by default | Client likely expects to own what it pays for; "unless otherwise agreed in writing in the SOW" pushes a material IP term into documents that may never explicitly address it, creating ambiguity at delivery. As the deliverable is software, ownership is also shaped by the Código do Direito de Autor's computer-program regime (originally DL n.º 252/94), not just this clause. | State the default directly in the MSA: assignment to Client on full payment, with Provider's pre-existing IP and tools carved out and licensed. | 🟡 |
| 3 | §3 — personal-data processing with no DPA referenced | Provider processes Client's customer data but no processing agreement is attached or required; this is a GDPR Art. 28 gap, not a formality. | Attach a DPA (or reference an executed one) before any processing begins. | 🔴 |
| 4 | §18 — German governing law with no jurisdiction clause | The excerpt sets governing law (Rome I) but is silent on which court hears a dispute (Brussels I bis, Reg. (EU) No 1215/2012); combined with a Portuguese provider, this raises cost and uncertainty in any dispute. | Add an explicit jurisdiction clause, or reconsider governing law to match the provider's home jurisdiction if that better reflects negotiating leverage. | 🟡 |
| 5 | §14 — asymmetric termination for convenience | Client can exit in 15 days for any reason; Provider can only exit for uncured breach. This is a common client-favouring term, not automatically improper, but it concentrates all schedule/revenue risk on Provider. | Either mirror the convenience-termination right (with a longer notice period, e.g. 30–60 days) or price the asymmetry into the commercial terms. | 🟡 |

### Key Passages Explained

- **§7 (Liability):** "Unlimited" liability means there is effectively no ceiling on what Provider
  could owe if something goes wrong — not just for the value of the contract, but for whatever damage
  actually results. This is the single highest-impact term in the agreement.
- **§9 (IP):** Ownership defaults to Provider unless a separate document says otherwise. In practice,
  many SOWs are commercial documents that never revisit IP — so "otherwise agreed" may simply never
  happen, leaving the question unresolved rather than resolved in Client's favour.
- **§11 (Payment):** NET 60 is longer than common practice (NET 30) and extends Provider's exposure to
  Client's own cash-flow risk.
- **§14 (Termination):** The 15-day convenience-termination window is short — Provider may have staff
  allocated or committed costs that can't unwind that quickly.

### Overall Status
🔴 — Two material (🔴) flags: unlimited liability and a missing DPA for in-scope personal-data
processing. Recommend both are resolved, and the contract reviewed by counsel, before signing.

### Needs Verification
- NordFin Payments' regulatory status and whether any sector-specific obligations flow down by
  reference elsewhere in the full agreement (not visible in this excerpt).
- Whether a DPA already exists as a separate, unreferenced document.
- Exact interaction between §7's liability language and German mandatory law, which may itself limit
  or void a purported "unlimited liability" clause in ways this review cannot assess from PT law alone.
- **Art. 280º CC** (cited above, not independently verified this session — no fetch tool used): the
  object of a legal transaction must be physically and legally possible, lawful, and sufficiently
  determined or determinable, or the transaction is void.
- **Art. 3 GDPR** (cited above, not independently verified this session — no fetch tool used): GDPR
  applies to processing by a controller/processor established in the EU regardless of where the
  processing takes place, and can also reach non-EU controllers/processors targeting or monitoring EU
  data subjects.
- **DL n.º 252/94** (cited above, not independently verified this session — no fetch tool used): sets
  Portugal's specific computer-program copyright regime (transposing Directive 91/250/EEC), governing
  who owns rights in software absent a clear contractual assignment.
- **Reg. (EU) No 1215/2012 — Brussels I bis** (cited above, not independently verified this session —
  no fetch tool used): governs which EU member state's courts have jurisdiction over a cross-border
  contract dispute, and the cross-border enforcement of the resulting judgment — separate from which
  law governs the contract's substance (Rome I).
