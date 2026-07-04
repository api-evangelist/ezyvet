# ezyVet (ezyvet)

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
