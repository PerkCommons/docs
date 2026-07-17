# Security Policy

## Reporting

Report suspected vulnerabilities privately to
[`security@perkcommons.com`](mailto:security@perkcommons.com). Do not open a
public issue for an exploitable vulnerability or include real personal data in
a report. Include the affected component, reproduction steps, impact, and a
safe proof of concept where possible.

The project will acknowledge reports as capacity allows, triage severity,
coordinate a fix, and credit reporters who request attribution. No bounty is
promised.

## Baseline controls

- Hardware-backed MFA for critical owner accounts.
- Two administrators and documented recovery for critical assets.
- Protected default branches and required CI review.
- Secret scanning, Dependabot, and least-privilege workflow permissions.
- Server-side validation, Turnstile, and rate limiting for submissions.
- No anonymous database policies on private moderation records.
- Structured logs without email addresses, source URLs, or submitted text.
- Defined deletion periods for rejected submissions and operational logs.

Secrets belong in Cloudflare, Supabase, or GitHub secret stores. They must never
be committed, placed in public environment variables, or included in diagnostics.
