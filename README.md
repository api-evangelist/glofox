# Glofox (glofox)

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

Glofox is boutique gym and fitness studio management software - member management, class/appointment scheduling, bookings, memberships, credits, payments, and lead conversion for studios, gyms, and fitness franchises. Glofox was acquired by ABC Fitness Solutions in August 2022 (a deal reported at upwards of €200 million) and now operates as the **ABC Glofox** business unit within ABC's broader fitness technology platform, alongside sibling acquisitions like Trainerize and GymSales.

Glofox publishes a real partner/developer REST API - the "ABC Glofox API Developer Portal" - covering members, memberships, plans, credits, classes/events, bookings, purchases/payments, branches, and leads, plus outbound CDC (change data capture) webhooks for member and access-control events. **Access is gated**: this is not a self-serve, open API. Integrators email a request-access template (business/studio name, use case, branch ID, expected daily volume, environments needed) to `apiactivation@abcfitness.com`, and are issued `x-api-key` and `x-glofox-api-token` credentials scoped by an `x-glofox-branch-id` header. Because the authoritative endpoint-by-endpoint reference lives behind a JavaScript-rendered Swagger UI that requires those approved credentials, the API groupings documented here reflect Glofox's own published resource model (from its Common Concepts and integration-flow docs), not a fully enumerated, credential-verified endpoint list.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/glofox/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/glofox/refs/heads/main/apis.yml)

## Tags

- Fitness
- Gym Management
- Boutique Fitness
- Class Scheduling
- Bookings
- Memberships
- Leads
- ABC Fitness
- CDC Webhooks

## Timestamps

- **Created:** 2026-07-03
- **Modified:** 2026-07-03

## APIs

### Glofox Members API

Access, create, and edit member records - the central pivot of the Glofox data model, spanning leads, active members, and ex-members (soft-deleted via an `active` flag rather than hard-deleted). The documented credential-verification call is a GET against `/2.0/members`.

- **Human URL:** [https://apidocs-plat.aws.glofox.com/authentication/](https://apidocs-plat.aws.glofox.com/authentication/)
- **Base URL:** `https://gf-api.aws.glofox.com/prod/2.0`

### Glofox Memberships, Plans & Credits API

Manage Plans (terms, duration, pricing), a member's Membership against a given Plan, and Credits - the units of value redeemed to book Classes, Appointments, or Facilities.

- **Human URL:** [https://apidocs-plat.aws.glofox.com/common-concepts/](https://apidocs-plat.aws.glofox.com/common-concepts/)
- **Base URL:** `https://gf-api.aws.glofox.com/prod/2.0`

### Glofox Classes & Events API

Scheduled Events - classes, appointments, and facility slots - with capacity and attendance tracking that members book against within a given Location/Branch.

- **Human URL:** [https://apidocs-plat.aws.glofox.com/common-concepts/](https://apidocs-plat.aws.glofox.com/common-concepts/)
- **Base URL:** `https://gf-api.aws.glofox.com/prod/2.0`

### Glofox Bookings API

Create and manage a member's booking - the record of intent to attend a scheduled Event - governed by available Credits and Event capacity.

- **Human URL:** [https://apidocs-plat.aws.glofox.com/flows/book/](https://apidocs-plat.aws.glofox.com/flows/book/)
- **Base URL:** `https://gf-api.aws.glofox.com/prod/2.0`

### Glofox Payments & Purchases API

Purchase products and plans and process payments through the Payment Collector flow - a hosted, domain-authorized iframe kept out of direct API credential exposure - covering transaction handling for memberships, classes, and retail products.

- **Human URL:** [https://apidocs-plat.aws.glofox.com/flows/purchase-product/](https://apidocs-plat.aws.glofox.com/flows/purchase-product/)
- **Base URL:** `https://gf-api.aws.glofox.com/prod/2.0`

### Glofox Leads API

Capture prospective members as leads and convert them into paying members through the "Lead Sale" integration flow documented in the developer portal.

- **Human URL:** [https://apidocs-plat.aws.glofox.com/flows/lead-sale/](https://apidocs-plat.aws.glofox.com/flows/lead-sale/)
- **Base URL:** `https://gf-api.aws.glofox.com/prod/2.0`

### Glofox Branches (Locations) API

Locations/Branches are the physical studios or gyms that contextualize Plans, Events, and Bookings. Every API request is scoped to a branch via the required `x-glofox-branch-id` header.

- **Human URL:** [https://apidocs-plat.aws.glofox.com/common-concepts/](https://apidocs-plat.aws.glofox.com/common-concepts/)
- **Base URL:** `https://gf-api.aws.glofox.com/prod/2.0`

### Glofox CDC Webhooks

Outbound change-data-capture webhooks - an HMAC-SHA256-signed Member Webhook (`MEMBER_CREATED`, `MEMBER_UPDATED`; no `MEMBER_DELETED`, deletes are soft via an `active` flag) and an Access Webhook that keeps barcode identifiers in sync with access-control hardware. Delivery is at-least-once HTTP POST with a 5-second response timeout and up to three attempts.

- **Human URL:** [https://apidocs-plat.aws.glofox.com/cdc-webhooks/](https://apidocs-plat.aws.glofox.com/cdc-webhooks/)
- **Base URL:** `https://gf-api.aws.glofox.com/prod/2.0`

## Access Model

- **Request access:** email a template (studio/business name, contact, use case/data flows, branch ID(s), expected daily volume, environments) to `apiactivation@abcfitness.com` (subject: "API Access Request"), or reach Glofox Integrations at `glofox.APISupport@abcfitness.com`.
- **Credentials:** `x-api-key` and `x-glofox-api-token`, plus a required `x-glofox-branch-id` header on every call. Separate credential sets exist for development/staging and production.
- **Security requirement:** credentials are for backend integrations only and must be proxied through a secure server - never exposed in a browser or client-side code.
- **Rate limits:** live accounts get 10 requests/second with a 1000-request burst; sandbox accounts get 3 requests/second with a 300-request burst.
- **Errors:** JSON body with `message` and `message_code`; standard HTTP codes (400/401/403/404/429/500), with a documented legacy exception where some older endpoints return HTTP 200 with `success: false`.

## Common Properties

- [GitHub Organization](https://github.com/glofoxinc)
- [LinkedIn](https://www.linkedin.com/company/abcglofox)
- [Website](https://www.glofox.com)
- [Documentation](https://apidocs-plat.aws.glofox.com/)
- [Plans](plans/glofox-plans-pricing.yml)
- [Rate Limits](rate-limits/glofox-rate-limits.yml)
- [Fin Ops](finops/glofox-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
