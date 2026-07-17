# ADR 0005: Limit moderation data retention

**Status:** Accepted

## Context

Moderation requires short-lived contact details and keyed abuse fingerprints,
but retaining them indefinitely would create unnecessary privacy and security
risk. PerkCommons also needs enough audit history to investigate moderation
decisions without retaining private data forever.

## Decision

Automatically redact submission and report contact data and fingerprints 90
days after a final decision. Retain sensitive notes for one year and minimal
moderation actions, resolved flags, and resolved reports for three years.
Delete expired temporary ban records after 90 days and review permanent bans
annually. Retain normalized public opportunity data while useful.

A daily Supabase Cron job performs mechanical cleanup and retains aggregate run
counts for one year. It never makes submission decisions or removes normalized
public opportunities. The accountable maintainer reviews stale submissions,
permanent bans, and job results quarterly.

## Consequences

Private moderation context eventually becomes unavailable, limiting very old
abuse investigations. This is preferable to indefinite retention. Policy
changes require a new ADR and a reviewed database migration so documentation
and behavior remain aligned.
