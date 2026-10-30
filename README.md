# Glofox

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Glofox is boutique gym and fitness studio management software - member management, class/appointment scheduling, bookings, memberships, credits, payments, and lead conversion for studios, gyms, and fitness franchises. Glofox was acquired by ABC Fitness Solutions in August 2022 and now operates as the ABC Glofox business unit within ABC's fitness technology platform. Glofox publishes a partner/developer REST API (the "ABC Glofox API Developer Portal") covering members, memberships, plans, credits, classes, bookings, purchases, branches, and leads, plus CDC (change data capture) webhooks for member and access-control events. Access is gated - integrators request x-api-key and x-glofox-api-token credentials by email before they can call the API.

**Areas:** Fitness · Gym Management · Boutique Fitness · Class Scheduling · Booking · Membership · Leads · ABC Fitness · CDC Webhooks

## Glofox on APIs.io

Everything profiled for Glofox is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/glofox/](https://apis.io/providers/glofox/)** — or go straight to one of the APIs or properties below.

### APIs (8)

- [Glofox Members API](https://apis.io/apis/glofox/glofox-members-api/) — Access, create, and edit member records - the central pivot of the Glofox data model, spanning leads, active members, and ex-members (soft-deleted via an…
- [Glofox Memberships, Plans & Credits API](https://apis.io/apis/glofox/glofox-memberships-plans-credits-api/) — Manage Plans (the terms, duration, and pricing of a service offering), a member's Membership against a given Plan, and Credits - the units of value a member…
- [Glofox Classes & Events API](https://apis.io/apis/glofox/glofox-classes-events-api/) — Scheduled Events - classes, appointments, and facility slots - with capacity and attendance tracking that members book against within a given Location/Branch.
- [Glofox Bookings API](https://apis.io/apis/glofox/glofox-bookings-api/) — Create and manage a member's booking - the record of intent to attend a scheduled Event - governed by available Credits and Event capacity. Documented end…
- [Glofox Payments & Purchases API](https://apis.io/apis/glofox/glofox-payments-purchases-api/) — Purchase products and plans and process payments through the Payment Collector flow - a hosted, domain-authorized iframe kept out of direct API credential…
- [Glofox Leads API](https://apis.io/apis/glofox/glofox-leads-api/) — Capture prospective members as leads and convert them into paying members through the "Lead Sale" integration flow documented in the developer portal.
- [Glofox Branches (Locations) API](https://apis.io/apis/glofox/glofox-branches-locations-api/) — Locations/Branches are the physical studios or gyms that contextualize Plans, Events, and Bookings. Every API request is scoped to a branch via the required…
- [Glofox CDC Webhooks](https://apis.io/apis/glofox/glofox-cdc-webhooks/) — Outbound change-data-capture webhooks - an HMAC-SHA256-signed Member Webhook (MEMBER_CREATED, MEMBER_UPDATED; deletes are soft via an active flag, no…

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Glofox Domain Security](https://apis.io/security/glofox/glofox-domain-security/)
- [Glofox Trust Center](https://apis.io/security/glofox/glofox-trust-center/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Glofox Plans Pricing](https://apis.io/plans/glofox/glofox-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Glofox Rate Limits](https://apis.io/rate-limits/glofox/glofox-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Glofox Finops](https://apis.io/finops/glofox/glofox-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.glofox.com)
- [Documentation](https://apidocs-plat.aws.glofox.com/)
- [Blog](https://www.glofox.com/feed/)
- [GitHub](https://github.com/glofoxinc)

## API Evangelist rating

**Kin Score 12.9** — emerging · rubric 0.24.0 · scored 2026-10-17

| Facet | Score |
|---|---|
| Discoverability | 71.4 |
| Contract quality | 0.0 |
| Contract governance | 0.0 |
| Operational transparency | 10.5 |
| Developer ergonomics | 9.5 |
| Access clarity | 15.8 |

**Agent readiness 0.6** — human-only

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | — |
| Agentic Access | — |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | — |
| Idempotency | — |
| Error Semantics | — |
| OpenAPI Examples | — |
| Rate Limit Signal | derived (partial credit) |
| Event Surface Described | — |
| Agent Skills | — |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |

**Regulatory alignment 10.8** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/glofox/](https://apis.io/providers/glofox/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Glofox: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/glofox/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
