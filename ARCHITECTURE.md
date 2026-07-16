# Architecture

## Principles

The public path stays static. Git is the publication ledger. Dynamic services are
restricted to private submission intake and moderation. Each boundary can be
replaced without losing the public dataset.

## Repositories

| Repository | Owns | License |
| --- | --- | --- |
| `PerkCommons/data` | Published JSON records, schema, validation | CC0 1.0 |
| `PerkCommons/site` | Astro frontend and submission Worker | Apache-2.0 |
| `PerkCommons/docs` | Policy, governance, architecture, ADRs | CC BY 4.0 |
| `PerkCommons/branding` | Marks, tokens, usage guidance | See repository license |

## Publication flow

```text
Contributor -> validation -> spam screening -> moderator review
            -> data pull request -> approval -> static site build -> Cloudflare Pages
```

The site workflow checks out an exact revision of `data`, generates HTML for each
record, runs Pagefind against the output, and deploys the static artifact. Public
browsing does not query Supabase.

## Submission boundary

`POST /api/submissions` runs as a Cloudflare Pages Function. It applies content
length and allow-list validation, HTTPS URL enforcement, a honeypot, Cloudflare
Turnstile, and an optional Cloudflare rate-limit binding. It writes to a private
Supabase/PostgreSQL table using a Worker-only service credential. Row-level
security exposes no anonymous read or write policy.

Moderators review the private queue and convert accepted records into a branch in
`data`. A GitHub pull request remains the publication gate and audit trail.

## Trust boundaries

- The browser receives no Supabase service credential or private submission data.
- Published JSON is untrusted until schema validation passes.
- Provider URLs remain external and are clearly presented as such.
- GitHub Actions use read-only permissions unless a deployment job needs more.
- Cloudflare and Supabase secrets are stored in their native secret managers.

## Availability and cost

Static pages and Pagefind avoid a search service, database reads, and origin
compute for public traffic. If the intake service is unavailable, published data
remains fully browsable and corrections can still arrive through GitHub.
