# ezyVet (ezyvet)

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

ezyVet is cloud-based veterinary practice information management software (PIMS) for clinics, specialty, and emergency hospitals - covering patient records, scheduling, clinical workflows, billing, inventory, and diagnostics. Founded in New Zealand in 2006, ezyVet was **acquired by IDEXX Laboratories in June 2021** and sits alongside IDEXX's Cornerstone and Neo PIMS offerings (the acquisition also included Vet Radar).

ezyVet exposes a documented RESTful API of roughly **216 endpoints**. Access is **partner-gated** - developer access requires an approved integration application and issued client credentials - but the endpoint catalog, best-practice guides, and a full Postman collection are publicly documented at [developers.ezyvet.com](https://developers.ezyvet.com/docs/v1/). Authentication is **OAuth 2.0 Client Credentials** (`POST /v1/oauth/access_token`) issuing bearer tokens with a 12-hour TTL. Base URLs are `https://api.ezyvet.com` (production) and `https://api.trial.ezyvet.com` (trial).

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/ezyvet/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/ezyvet/refs/heads/main/apis.yml)

## Tags

- Veterinary
- Practice Management
- PIMS
- Healthcare
- Animal Health
- IDEXX
- Partner Gated

## Timestamps

- **Created:** 2026-07-04
- **Modified:** 2026-07-04

## Grounding

The OAuth token endpoint, the `/v1/contact` CRUD endpoints, the `/v2/prescription` GET, the Standard Diagnostic Integration, and the base URLs / rate-limit behavior are **confirmed** from ezyVet's public developer documentation. The remaining resource paths (animal, appointment, consult, invoice, product, and their reference resources) are **modeled** on ezyVet's documented `/v1/{resource}` REST pattern and published resource categories; exact paths and verbs should be verified against the official partner Postman collection. See [review.yml](review.yml) for the confirmed-vs-modeled endpoint breakdown.

## APIs

### ezyVet Authentication API

OAuth 2.0 Client Credentials token endpoint. Exchange `partner_id`, `client_id`, `client_secret`, `grant_type`, and `scope` for a bearer access token (12-hour TTL) that authorizes every other API call.

- **Human URL:** [https://developers.ezyvet.com/docs/v1/](https://developers.ezyvet.com/docs/v1/)
- **Base URL:** `https://api.ezyvet.com`

### ezyVet Animals (Patients) API

Manage animal (patient) records - species, breed, sex, colour, microchip, owner linkage, and clinical metadata - plus reference resources for species and breeds.

- **Human URL:** [https://developers.ezyvet.com/docs/v1/](https://developers.ezyvet.com/docs/v1/)
- **Base URL:** `https://api.ezyvet.com`

### ezyVet Contacts (Clients) API

Create, list, retrieve, update, and delete contacts - the clients (pet owners), businesses, vendors, and staff a practice interacts with - along with their addresses and details. (`/v1/contact` CRUD confirmed.)

- **Human URL:** [https://developers.ezyvet.com/docs/v1/](https://developers.ezyvet.com/docs/v1/)
- **Base URL:** `https://api.ezyvet.com`

### ezyVet Appointments API

Book and manage appointments against animals, contacts, resources, and users, with appointment type and status reference resources.

- **Human URL:** [https://developers.ezyvet.com/docs/v1/](https://developers.ezyvet.com/docs/v1/)
- **Base URL:** `https://api.ezyvet.com`

### ezyVet Consultations (Clinical) API

Access clinical consultations - the visit-level records tying an animal, contact, and presenting problem to history, diagnoses, and treatment - plus related clinical resources.

- **Human URL:** [https://developers.ezyvet.com/docs/v1/](https://developers.ezyvet.com/docs/v1/)
- **Base URL:** `https://api.ezyvet.com`

### ezyVet Invoices (Billing) API

Read and manage invoices, invoice lines, and payments for services and products billed to clients.

- **Human URL:** [https://developers.ezyvet.com/docs/v1/](https://developers.ezyvet.com/docs/v1/)
- **Base URL:** `https://api.ezyvet.com`

### ezyVet Products (Inventory) API

Browse and manage the product and inventory catalog - billable products, services, and stock items - plus product groups and pricing.

- **Human URL:** [https://developers.ezyvet.com/docs/v1/](https://developers.ezyvet.com/docs/v1/)
- **Base URL:** `https://api.ezyvet.com`

### ezyVet Diagnostics API

Diagnostic request and result resources powering ezyVet's Standard Diagnostic Integration, letting lab and imaging partners push results back against a patient's clinical record over a RESTful, OAuth 2.0 Client Credentials interface. (Integration confirmed.)

- **Human URL:** [https://developers.ezyvet.com/docs/v1/integrations/diagnostic/](https://developers.ezyvet.com/docs/v1/integrations/diagnostic/)
- **Base URL:** `https://api.ezyvet.com`

### ezyVet Prescriptions and Vaccinations API

Manage prescriptions (including a v2 prescription resource and external Rx flows for pharmacy partners) and vaccination records.

- **Human URL:** [https://developers.ezyvet.com/guides/external-pharmacy.html](https://developers.ezyvet.com/guides/external-pharmacy.html)
- **Base URL:** `https://api.ezyvet.com`

## Common Properties

- **LinkedIn:** [https://www.linkedin.com/company/ezyvet](https://www.linkedin.com/company/ezyvet)
- **Website:** [https://www.ezyvet.com](https://www.ezyvet.com)
- **Documentation:** [https://developers.ezyvet.com/docs/v1/](https://developers.ezyvet.com/docs/v1/)
- **Plans:** [plans/ezyvet-plans-pricing.yml](plans/ezyvet-plans-pricing.yml)
- **Rate Limits:** [rate-limits/ezyvet-rate-limits.yml](rate-limits/ezyvet-rate-limits.yml)
- **FinOps:** [finops/ezyvet-finops.yml](finops/ezyvet-finops.yml)

## Rate Limits

- ~60 requests/minute per endpoint
- ~180 calls/minute per practice database per partner
- HTTP 429 on excess; inspect `x-ratelimit-remaining` and `x-ratelimit-reset` headers
- Bearer tokens: 12-hour TTL

## Maintainers

- **Kin Lane** — kin@apievangelist.com
