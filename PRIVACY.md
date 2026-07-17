# Privacy Policy

**Status:** Adopted  
**Effective date:** 2026-07-17

PerkCommons collects only the private data needed to receive contributions,
operate moderation, investigate abuse, and maintain the integrity of the public
index. Published opportunity data is intentionally public and reusable; private
submission and moderation data is not part of the open dataset.

## Data collected

Public submission and report forms may collect optional names, email addresses,
free-text notes, linked opportunity details, and report details. The intake
service also derives keyed, one-way fingerprints from normalized email
addresses, IP addresses, and bounded user-agent strings. It stores the country
code supplied by Cloudflare when available. Raw IP addresses are not stored.

Moderator accounts use Supabase Authentication. Private moderation records may
include decisions, flags, reports, internal notes, abuse controls, and the UUID
of the moderator responsible for an action.

## Use and disclosure

Private data is used only for submission review, contributor communication,
rate limiting, abuse investigation, security, and moderation accountability.
It is not sold, included in the public dataset, or used for advertising.
Cloudflare and Supabase process data as infrastructure providers. A moderator
may copy an unredacted review brief only into a trusted service and receives an
explicit warning before doing so.

Country, IP, email, and user-agent signals are fallible. Shared networks, VPNs,
mobile address changes, disposable email, and geographic routing can produce
false positives. No such signal may be the sole basis for rejection or a ban.

## Retention schedule

| Data | Retention |
| --- | --- |
| Pending, reviewing, or flagged submissions | Human review required after 180 days; no automatic decision |
| Submitter contact details and fingerprints after rejection, withdrawal, or publication | 90 days |
| Resolved report contact details and fingerprints | 90 days |
| Expired temporary ban records | 90 days after expiry |
| Permanent bans | Manual review every 12 months |
| Sensitive internal notes and resolved report details | 1 year |
| Minimal moderation actions, resolved flags, and resolved reports | 3 years |
| Normalized public opportunity data | Indefinite while useful |

A daily automated job applies mechanical deletion and redaction. It never makes
submission decisions or removes normalized public opportunities. Deleted data
may remain in encrypted provider backups until those backups expire under the
provider's backup lifecycle.

`CodWasTaken` is the initial accountable maintainer for quarterly retention-job
reviews, submissions awaiting review for more than 180 days, and permanent bans
older than one year. Future stewardship changes must update this policy.

## Requests and changes

Privacy or deletion requests may be sent to `security@perkcommons.org`. Some
public opportunity facts or minimal audit records may be retained when needed
for the open index, security, legal obligations, or moderation accountability.

Material changes to this policy require a reviewed pull request and an
architecture decision record. The version history remains public in Git.
