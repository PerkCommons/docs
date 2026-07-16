# ADR 0003: Separate repositories by ownership

**Status:** Accepted

## Decision

Maintain independent repositories for site, data, docs, and branding.

## Consequences

Licensing, release cadence, contribution review, and ownership stay explicit.
Cross-repository CI is slightly more involved; builds check out the exact data
revision they consume.
