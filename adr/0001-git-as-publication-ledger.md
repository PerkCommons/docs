# ADR 0001: Use Git as the publication ledger

**Status:** Accepted

## Context

Published changes must be transparent, reviewable, portable, and inexpensive.

## Decision

Store one JSON file per published opportunity in Git. Require schema validation
and pull-request approval before publication.

## Consequences

History, attribution, rollback, and reuse are native. Moderators work in a review
workflow contributors understand. Very large datasets may eventually need build
optimizations, but no database becomes the canonical public record.
