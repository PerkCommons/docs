# Data Schema

The canonical machine-readable contract is
`PerkCommons/data/schema/opportunity.schema.json` using JSON Schema 2020-12.

## Required fields

| Field | Meaning |
| --- | --- |
| `id` | Immutable lowercase, hyphenated identifier; also the filename |
| `provider` | Organization controlling the opportunity |
| `title` | Public program name |
| `category` | One controlled top-level category |
| `tags` | Lowercase discovery terms |
| `description` | Neutral, source-supported summary |
| `eligibility` | Material audience and restrictions |
| `value` | Concrete benefit and known limits |
| `sourceUrl` | Evidence used by the reviewer, HTTPS only |
| `officialUrl` | Canonical destination, HTTPS only |
| `status` | Editorial state described below |
| `submissionType` | `community`, `company`, or `maintainer` |
| `sponsor` | Disclosure of a current commercial relationship |
| `reviewDate` | ISO 8601 date of the latest evidence check |

Optional fields include `regions` and editorial `notes`.

## Status values

- `active`: credible evidence indicates normal availability.
- `limited`: geography, cohort, eligibility, or partner restrictions are material.
- `waitlist`: the program exists but normal applications are unavailable.
- `unconfirmed`: previously credible but not recently reconfirmed.
- `expired`: no longer available or its deadline passed.
- `disputed`: a material factual concern is under review.

Status is descriptive, never a rating or endorsement.
