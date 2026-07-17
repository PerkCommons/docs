# PerkCommons Documentation

Public policies, architecture, governance, and operating guidance for
PerkCommons. Documentation is version controlled so material policy changes can
be reviewed like code.

## Start here

- [PROJECT_CHARTER.md](PROJECT_CHARTER.md): mission and public commitments
- [ARCHITECTURE.md](ARCHITECTURE.md): system boundaries and data flow
- [DATA_SCHEMA.md](DATA_SCHEMA.md): published record contract
- [CONTRIBUTING.md](CONTRIBUTING.md): ways to participate
- [SECURITY.md](SECURITY.md): private reporting and security model
- [PRIVACY.md](PRIVACY.md): private-data use and retention commitments
- [ROADMAP.md](ROADMAP.md): milestone-based delivery plan
- [DECISIONS.md](DECISIONS.md): architectural decision index

Source material from the founding process is retained in `source-material/`.

## OpenAI Build Week

PerkCommons was developed for OpenAI Build Week with GPT-5.6 and Codex as
engineering collaborators. They accelerated the work without replacing source
verification, editorial judgment, or human moderation.

### How GPT-5.6 was used

GPT-5.6 supported the reasoning and design work behind the project, including:

- evaluating static-first architecture and repository boundaries;
- reviewing security, privacy, abuse-prevention, and data-retention tradeoffs;
- shaping the submission and moderation workflows;
- reasoning about accessible mobile, keyboard, and swipe interactions;
- drafting and refining technical and policy documentation; and
- analyzing implementation risks and production failures.

### How Codex was used

Codex worked directly with the version-controlled repositories to:

- inspect the existing code and follow established project conventions;
- implement the Astro, TypeScript, Tailwind CSS, Cloudflare Worker, and
  Supabase changes;
- create and review PostgreSQL migrations;
- build unit and Playwright test coverage across desktop and mobile layouts;
- run clean installs, type checks, tests, static builds, and browser tests;
- diagnose Cloudflare and Supabase production failures using structured logs;
- prepare feature branches, conventional commits, and reviewed pull requests;
  and
- verify deployments without committing credentials or private moderation
  data.

### Human responsibility

PerkCommons does not use AI to generate or automatically publish listings.
Every published opportunity must be supported by an official source and pass
human review. Moderation decisions, bans, sponsorship disclosures, and policy
changes remain accountable human responsibilities. AI-assisted code and
documentation are reviewed, tested, and version controlled through the same
contribution process as other project changes.
