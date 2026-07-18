# Opportunity Taxonomy

PerkCommons uses one primary category, zero or more category-specific
subcategories, and independent tags. Categories describe **what an opportunity
is**. The `eligibility` field describes **who can access it**.

The machine-readable source is
`PerkCommons/data/taxonomy/opportunity-taxonomy.json`. Display labels and
descriptions must come from that file rather than being copied into records.

## Categories

| Identifier | Label | Subcategories |
| --- | --- | --- |
| `startup-benefits` | Startup Benefits | cloud credits, infrastructure credits, SaaS discounts, incorporation support, legal support, accounting support, banking and finance, marketing tools, customer support tools, analytics and observability, security tools, developer tooling |
| `student-benefits` | Student Benefits | software discounts, education plans, student developer packs, free courses, certification discounts, hardware discounts, student memberships, academic resources |
| `nonprofit-benefits` | Nonprofit Benefits | software donations, nonprofit discounts, cloud credits, fundraising tools, communications tools, productivity tools, security tools, nonprofit consulting |
| `developer-programs` | Developer Programs | API credits, open-source programs, developer preview programs, beta access, maintainer support, developer grants, bug bounty programs, ambassador programs |
| `funding` | Funding | grants, microgrants, prizes, fellowships with funding, research funding, creator funds, community funds, open-source sponsorships |
| `accelerators-incubators` | Accelerators and Incubators | startup accelerators, nonprofit accelerators, student incubators, university incubators, climate accelerators, social-impact accelerators, AI accelerators, pre-accelerators |
| `competitions-hackathons` | Competitions and Hackathons | online hackathons, in-person hackathons, startup competitions, pitch competitions, innovation challenges, data science competitions, design competitions, student competitions |
| `fellowships` | Fellowships | technical, research, policy, entrepreneurship, social-impact, creator, student, and open-source fellowships |
| `internships-work-experience` | Internships and Work Experience | internships, apprenticeships, externships, residencies, traineeships, job-shadowing programs, returnships, project-based experience |
| `research-opportunities` | Research Opportunities | research internships, research assistantships, lab programs, visiting researcher programs, dataset access, compute credits, academic challenges, publication support |
| `mentorship-community` | Mentorship and Community | mentorship programs, peer communities, founder communities, student communities, technical communities, office hours, expert networks, accountability groups |
| `education-training` | Education and Training | courses, bootcamps, workshops, certifications, learning paths, scholarships, tuition support, exam vouchers |
| `open-source` | Open Source | contributor programs, maintainer programs, sponsorships, issue bounties, mentorship programs, project grants, fiscal hosting, infrastructure support |
| `social-impact-civic-tech` | Social Impact and Civic Tech | civic-tech, humanitarian, public-interest technology, climate, accessibility, education-impact, health-impact, and community-development programs |
| `creator-media` | Creator and Media Opportunities | creator funds, media fellowships, journalism grants, podcast grants, film grants, design residencies, writing programs, publishing support |
| `events-conferences` | Events and Conferences | conference scholarships, travel grants, speaker opportunities, community tickets, student tickets, startup showcases, demo days, networking events |
| `discounts-perks` | Discounts and Perks | professional software, productivity tools, design tools, communications tools, hosting, hardware, memberships, travel and coworking |
| `volunteer-service` | Volunteer and Service | skilled volunteering, nonprofit projects, civic volunteering, open-source volunteering, mentorship volunteering, community service, pro bono work, remote volunteering |
| `awards-recognition` | Awards and Recognition | innovation, student, open-source, community, research, social-impact, creator, and founder awards |
| `early-access` | Early Access and Experimental Programs | private betas, public betas, research previews, developer previews, pilot programs, product testing, waitlists, early-adopter programs |

The taxonomy data file contains the authoritative identifier for every
subcategory and a short description for every top-level category.

## Choosing a Category

1. Classify the opportunity's main mechanism, not every audience it might
   serve. A research grant belongs in `funding`, even when only students are
   eligible.
2. Prefer the most specific top-level category that describes the offer. A
   nonprofit software donation belongs in `nonprofit-benefits`, not the general
   `discounts-perks` category.
3. Select only subcategories defined beneath the chosen primary category.
4. Put cross-cutting concepts such as `remote`, `climate`, or a technology name
   in `tags`.
5. Explain audience, geography, stage, and other access restrictions in
   `eligibility`.

## Examples

| Opportunity type | Primary category | Subcategory |
| --- | --- | --- |
| Startup cloud credit | `startup-benefits` | `cloud-credits` |
| Student software benefit | `student-benefits` | `software-discounts` |
| Nonprofit discount | `nonprofit-benefits` | `nonprofit-discounts` |
| Research grant | `funding` | `research-funding` |
| Online hackathon | `competitions-hackathons` | `online-hackathons` |
| Technical fellowship | `fellowships` | `technical-fellowships` |
| Internship | `internships-work-experience` | `internships` |
| Startup accelerator | `accelerators-incubators` | `startup-accelerators` |
| Open-source mentorship | `open-source` | `mentorship-programs` |
| Conference travel scholarship | `events-conferences` | `conference-scholarships`, `travel-grants` |
| Remote volunteer opportunity | `volunteer-service` | `remote-volunteering` |
| Private beta program | `early-access` | `private-betas` |

These examples classify formats only. They do not establish eligibility or
verification status.

## Maintaining the Taxonomy

Category identifiers are public API values and stable URL segments. To add a
category, update the taxonomy data, JSON Schema, site compile-time identifier
type, documentation, fixtures, and validation tests in one coordinated change.

Do not silently rename or delete an identifier. Add the replacement, retain a
legacy alias in the taxonomy, migrate current records and private submissions,
and preserve existing opportunity URLs. Display-label changes do not require a
record migration but still require review because they affect navigation and
search.

Recognized legacy values are normalized at the data and site boundaries. New
submissions must use canonical identifiers. Unknown values and subcategories
that do not belong to the selected primary category are rejected.
