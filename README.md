# Security Policy & NIST-Aligned Risk Assessment

A GRC (Governance, Risk & Compliance) case study built around a hypothetical
40-employee software consultancy, **Nexora Solutions Pvt Ltd**. The goal was
to learn how GRC is actually practiced — not by summarizing what ISO 27001
or NIST 800-30 say, but by producing the three interlocking deliverables a
real GRC analyst produces, and understanding why each one exists.

## How this was built

I worked from primary sources such as:

- **NIST SP 800-30** (*Guide for Conducting Risk Assessments*) — used its
  Likelihood and Impact tier definitions (Table 3-4 / 3-5) to score every
  risk. Each of the 15 risk entries has a written justification tracing the
  score back to a specific tier definition, not just a number.
- **ISO/IEC 27001:2022 Annex A** — went through all 93 controls individually
  (not just a convenient subset) to build the Statement of Applicability.
- **ISO/IEC 27001 Clause 9.2** — used the internal audit requirement to
  design a sampling-based verification exercise, rather than just re-stating
  the policy.
- **NIST CSF 2.0** — used as a light secondary lens to map the policy's
  provisions to the six CSF functions (Govern/Identify/Protect/Detect/
  Respond/Recover).

The three documents are designed to be **internally consistent**, in the way
a real ISMS (Information Security Management System) is supposed to be:
risks identified in the Risk Register drove control decisions in the SoA,
and the Internal Audit tested whether those SoA claims were actually true.
Four non-conformities were found — all four trace directly back to High-rated
risks already flagged in the Risk Register, which is the intended behavior
of a working ISMS, not a coincidence.

## What's in here

| Document | What it answers |
|---|---|
| [`01-security-policy-risk-assessment`](docs-pdf/01-security-policy-risk-assessment.pdf) | Access Control, Password, and Incident Reporting policy; 15-asset Risk Register scored via NIST SP 800-30 methodology, with rationale for every score; CSF 2.0 mapping |
| [`02-statement-of-applicability`](docs-pdf/02-statement-of-applicability.pdf) | All 93 ISO/IEC 27001:2022 Annex A controls assessed Yes / Partial / No for Nexora, with justification for each |
| [`03-internal-audit-checklist`](docs-pdf/03-internal-audit-checklist.pdf) | 15 sample audit checks (ISO 27001 Clause 9.2) verifying SoA claims against evidence; 4 non-conformities raised |

(PDF versions above render directly in GitHub; `.docx` originals are in
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

## Methodology note on tooling

Parts of this repository were drafted with AI assistance (research
synthesis and document formatting). The risk scoring methodology, control
applicability judgments, and audit findings were independently reasoned
through by me against the source standards (NIST SP 800-30 Tables 3-4/3-5,
ISO/IEC 27001:2022 Annex A) — I can walk through the justification for any
individual score or decision in this repository on request.
