# Glofox (glofox)

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
