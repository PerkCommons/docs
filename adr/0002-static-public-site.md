# ADR 0002: Keep the public site static

**Status:** Accepted

## Context

Most traffic reads data that changes only after moderation.

## Decision

Generate the public site with Astro and index output with Pagefind. Deploy static
artifacts to Cloudflare Pages.

## Consequences

Browsing is fast, resilient, cacheable, and low-cost. Publication requires a
build, which is acceptable because reviewed data already passes through Git.
