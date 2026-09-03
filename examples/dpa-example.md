# Worked Example — DPA

> Fictional scenario, built to exercise the skill. Party names, terms, and facts are invented for
> demonstration only.

## Input: contract excerpt

**Data Processing Addendum** between **Braga HealthTech, Lda.** ("Controller") and **CloudOps
Solutions Unipessoal, Lda.** ("Processor"), attached to a hosting and support services agreement.

> **2. Subject Matter.** Processor will process personal data as necessary to provide the hosting and
> support services described in the Agreement.
>
> **4. Sub-processors.** Processor may engage sub-processors as it deems necessary to perform the
> Services. Processor will maintain a list of sub-processors available upon request.
>
> **6. Security.** Processor shall implement industry-standard security measures appropriate to the
> risk.
>
> **8. Breach Notification.** Processor shall notify Controller of any personal data breach without
> undue delay.
>
> **10. Data Return/Deletion.** Upon termination, Processor shall delete or return Controller's
> personal data within a commercially reasonable time.
>
> **12. Audit.** Controller may request information regarding Processor's security practices.

## Output: skill review

*Not legal advice. Portuguese law + applicable EU regulations only. Verify citations and thresholds
before relying on this.*

### Summary & Scope
DPA attached to a hosting/support agreement; Braga HealthTech as controller, CloudOps Solutions as
processor. Covers subject matter, sub-processors, security, breach notification, data return/deletion,
and audit — but several required elements are either thin or missing.

### Legal Grounding
- **General validity** — Established. Object (processing personal data to deliver hosting/support
  services) is lawful, possible, and determinable (Art. 280º CC).
- **Objective eligibility** — Established. The object is personal-data processing itself, so GDPR
  (Reg. (EU) 2016/679) and Lei n.º 58/2019 apply directly and centrally — this is precisely what a DPA
  exists to govern. Given the controller's name ("HealthTech"), health data (a special category under
  Art. 9 GDPR) may be in scope — see Needs Verification.
- **Subjective eligibility** — Needs verification. Whether either party is established outside the
  EU/EEA, or uses infrastructure located outside it, isn't stated here and materially affects whether
  an international-transfer mechanism (§4/§7 gap, below) is actually required.
- **Governing law & jurisdiction** — Not stated in this excerpt; needs confirming against the main
  hosting agreement.

### Red Flags

| # | Flag | Why it's a risk | How to fix | Severity |
|---|------|------------------|------------|----------|
| 1 | §2 — subject matter lacks required detail | GDPR Art. 28(3) requires the DPA to specify the duration of processing, the categories of personal data, and the categories of data subjects — none of which appear here. | Add explicit duration, data categories, and data-subject categories to §2. | 🔴 |
| 2 | §4 — general sub-processor authorisation with no notice/objection right | Controller has no visibility into who is actually handling its data, and no ability to object before a new sub-processor starts processing. | Require either specific authorisation per sub-processor, or general authorisation with advance written notice and a defined objection window. | 🔴 |
| 3 | §6 — "industry-standard" security with no specifics | This doesn't meet Art. 32 GDPR's expectation of measures appropriate to the actual risk (e.g. encryption, access control, testing) and is unenforceable as drafted — nobody can point to a concrete standard being breached. | Reference specific measures or a named standard (e.g. ISO 27001, SOC 2 Type II) and require evidence on request. | 🟡 |
| 4 | §8 — breach notification "without undue delay," no timeframe | Controller must notify the supervisory authority within 72 hours of becoming aware (Art. 33 GDPR); if Processor's own notice to Controller isn't meaningfully faster than that, Controller may not be able to meet its own deadline. | Set a concrete processor→controller notice window, e.g. 24–48 hours. | 🔴 |
| 5 | §10 — "commercially reasonable time" for deletion/return | Vague and unenforceable; data could persist well beyond what Controller expects or beyond what GDPR's storage-limitation principle supports. | Set a specific number of days (e.g. 30–90) for deletion or return after termination. | 🟡 |
| 6 | §12 — audit right limited to "requesting information" | This falls short of GDPR Art. 28(3)(h), which requires the processor to make available information necessary to demonstrate compliance and allow for audits/inspections. | Add an actual audit/inspection right, which can be satisfied in practice by accepting a current SOC 2/ISO 27001 report plus a right to audit for cause. | 🟡 |
| 7 | No international-transfer clause at all | If any sub-processor or infrastructure sits outside the EU/EEA, there's no stated transfer mechanism (SCCs, adequacy decision) — a gap, not a "not applicable." | Add a transfer clause, or an explicit statement that all processing stays within the EU/EEA if that's factually true. | 🔴 (if transfers occur) / 🟡 (until confirmed) |

### Key Passages Explained

- **§4 (Sub-processors):** "As it deems necessary," with a list only "available upon request," means
  Controller finds out who's touching its data by asking, not by being told. That's the opposite of
  the oversight GDPR expects a controller to maintain over its processing chain.
- **§8 (Breach Notification):** "Without undue delay" sounds reassuring but is legally vague — it
  doesn't commit Processor to notifying fast enough for Controller to hit its own 72-hour regulatory
  clock, which starts running from Controller's own awareness, not from when Processor gets around to
  telling it.
- **§10 (Deletion/Return):** "Commercially reasonable" is Processor's own judgment call, not a
  deadline Controller can hold it to.

### Overall Status
🔴 — Four material (🔴) flags, most centrally the missing subject-matter detail (§2) and the
uncontrolled sub-processor clause (§4), both of which are Art. 28 GDPR requirements, not optional
niceties. Recommend this DPA is not executed as-is.

### Needs Verification
- Whether Art. 9 special-category data (health data) is actually processed, which would raise the
  bar further (e.g. explicit consent or another Art. 9(2) condition, alongside the Art. 6 basis).
- Whether any processing or sub-processing occurs outside the EU/EEA.
- Governing law and jurisdiction, not visible in this excerpt.
- **Art. 280º CC, 28(3), 32, 33, 9, 6, and 28(3)(h) GDPR** (all cited above): **not independently
  verified this session — no fetch tool used.** Best-understanding restatements, to be checked against
  the source (see [`references/legal-sources.md`](../references/legal-sources.md)) before relying on
  the exact wording or paragraph numbering:
  - Art. 280º CC: the object of a legal transaction must be physically and legally possible, lawful,
    and sufficiently determined or determinable, or the transaction is void.
  - Art. 28(3) GDPR: a processing contract must specify the subject matter, duration, nature and
    purpose of processing, the type of personal data and categories of data subjects, and set out the
    processor's obligations (documented instructions, confidentiality, security, sub-processor
    conditions, assistance duties, deletion/return, and audit).
  - Art. 32 GDPR: controller and processor must implement technical and organisational measures
    appropriate to the actual risk (e.g. pseudonymisation/encryption, ongoing confidentiality and
    resilience, and regular testing).
  - Art. 33 GDPR: the controller must notify a personal data breach to the supervisory authority
    without undue delay and, where feasible, within 72 hours of becoming aware of it.
  - Art. 9 GDPR: processing special categories of data (health included) is prohibited unless a
    specific exception applies, such as explicit consent.
  - Art. 6 GDPR: processing personal data is lawful only if at least one listed legal basis applies
    (e.g. consent, contract necessity, legal obligation, legitimate interests).
  - Art. 28(3)(h) GDPR: the processor must make available all information necessary to demonstrate
    compliance and allow for, and contribute to, audits/inspections by the controller.
