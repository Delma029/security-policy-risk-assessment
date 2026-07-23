# Security Policy & NIST-Aligned Risk Assessment

A GRC (Governance, Risk & Compliance) case study built around a hypothetical
40-employee software consultancy, **Nexora Solutions Pvt Ltd**. The goal was
to learn how GRC is actually practiced — not by summarizing what ISO 27001
or NIST 800-30 say, but by producing the interlocking deliverables a real
GRC analyst produces, and understanding why each one exists and how they
verify one another.

## How this was built

I worked from primary sources rather than relying on templates alone:

- **NIST SP 800-30** (*Guide for Conducting Risk Assessments*) — used its
  Likelihood and Impact tier definitions to score every risk in the
  register. Each of the 15 entries has a written justification tracing the
  score back to a specific tier definition, not just a number.
- **ISO/IEC 27001:2022 Annex A** — the full 93-control list (37
  Organizational, 8 People, 14 Physical, 34 Technological) was verified
  against a live, current source rather than recalled from memory, to build
  the Statement of Applicability control-by-control.
- **ISO/IEC 27001 Clause 9.2** — used the internal audit requirement to
  design a sampling-based verification exercise against the SoA's claims.
- **NIST CSF 2.0** — used as a light secondary lens to map the policy's
  provisions to the six CSF functions (Govern/Identify/Protect/Detect/
  Respond/Recover).
- The remediation roadmap follows the general structure of a **Plan of
  Action & Milestones (POA&M)**, the standard format used in US federal and
  contractor GRC practice (e.g. FedRAMP), applied to consolidate the SoA
  gaps and audit non-conformities into a single, owned action plan.

The four documents are designed to be **internally consistent**, in the way
a real ISMS (Information Security Management System) is supposed to be:
risks identified in the Risk Register drove control decisions in the SoA,
the Internal Audit tested whether those SoA claims were actually true, and
every non-conformity found feeds directly into the Remediation Roadmap.
Four non-conformities were raised — all four trace back to High-rated risks
already flagged in the Risk Register, which is the intended behavior of a
working ISMS, not a coincidence.

## What's in here

| Document | What it answers |
|---|---|
| [`01-security-policy-risk-assessment`](docs-pdf/01-security-policy-risk-assessment.pdf) | Access Control, Password, and Incident Reporting policy; 15-asset Risk Register scored via NIST SP 800-30 methodology, with rationale for every score; CSF 2.0 mapping |
| [`02-statement-of-applicability`](docs-pdf/02-statement-of-applicability.pdf) | All 93 ISO/IEC 27001:2022 Annex A controls assessed Yes / Partial / No for Nexora, with justification for each |
| [`03-internal-audit-checklist`](docs-pdf/03-internal-audit-checklist.pdf) | 15 sample audit checks (ISO 27001 Clause 9.2) verifying SoA claims against evidence; 4 non-conformities raised |
| [`04-gap-analysis-remediation-roadmap`](docs-pdf/04-gap-analysis-remediation-roadmap.pdf) | POA&M-style prioritized action plan consolidating all open SoA gaps and audit findings, with owners and target dates |
| [`05-grc-control-tracker.xlsx`](docs/05-grc-control-tracker.xlsx) | Operational spreadsheet: all 93 controls with SoA status, audit result, and linked remediation item, with live summary formulas |

(PDF versions render directly in GitHub; `.docx`/`.xlsx` originals are in
[`/docs`](docs/) for editing.)

## Scope and limitations — what I'd do differently at enterprise scale

This is a single-person exercise at SME scale, built to learn the
methodology end-to-end. It is not a certification-ready ISMS. Specifically:

- Risk scores and control decisions were made solo; in practice they'd be
  agreed with actual asset owners and business stakeholders.
- The 15-asset inventory is illustrative, not exhaustive — a real
  organization's asset inventory is usually pulled from a CMDB and runs far
  larger.
- No external/accredited audit has reviewed this — several controls are
  honestly marked "No" or "Partial," which a real certification would
  require closing first.
- Scoring is qualitative only; enterprise risk decisions often add
  quantitative methods (Single/Annualized Loss Expectancy) when budget is
  on the line.

I'm noting these gaps explicitly rather than glossing over them, because
knowing the difference between a learning exercise and a production ISMS is
itself part of understanding GRC.

## Sources referenced

**Directly verified against a live source while building this repo:**
- ISO/IEC 27001:2022 Annex A control taxonomy (all 93 controls and their
  four themes) — checked against a current published reference rather than
  recalled from memory, to keep the Statement of Applicability accurate.

**Primary standards consulted for methodology (free, publicly available):**
- NIST SP 800-30 Rev 1 — *Guide for Conducting Risk Assessments*
  (csrc.nist.gov) — source of the Likelihood/Impact tier definitions used
  in the Risk Register.
- NIST SP 800-53 Rev 5 — control catalog referenced for NIST-family control
  terminology (csrc.nist.gov).
- NIST SP 800-53A — assessment procedures; informed the Method/Evidence
  structure of the Internal Audit Checklist.

**Recommended further reading (format/structure awareness, not verbatim
sources for this repo's content):**
- SANS Institute free policy templates — sans.org/information-security-policy
- ISO27001security.com risk register/SoA toolkit (Gary Hinson)
- FedRAMP POA&M template — fedramp.gov — the general POA&M structure this
  repo's roadmap follows is standard federal/contractor GRC practice; the
  specific FedRAMP document itself is worth reading directly for anyone
  going deeper on this format.
- UK NCSC small business security guidance — ncsc.gov.uk

## Methodology note on tooling

Parts of this repository were drafted with AI assistance (research
synthesis and document formatting). The risk scoring methodology, control
applicability judgments, and audit findings were independently reasoned
through by me against the source standards — I can walk through the
justification for any individual score or decision in this repository on
request.
