# ADR 0004: Isolate dynamic submission intake

**Status:** Accepted

## Decision

Use a Cloudflare Pages Function for validation and abuse controls, then store the
private moderation queue in Supabase PostgreSQL. Publication still requires a
pull request to the data repository.

## Consequences

Untrusted submissions never become public automatically. The service-role key
stays server-side, and an intake outage cannot break public browsing.
