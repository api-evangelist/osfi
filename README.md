# OSFI

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

The Office of the Superintendent of Financial Institutions (OSFI / BSIF) is Canada's federal prudential regulator, supervising more than 400 federally regulated financial institutions and over 1,200 private pension plans. On the insurance side OSFI supervises federally regulated life insurance companies, property and casualty insurers, mortgage insurers and fraternal benefit societies for solvency and capital adequacy — issuing the LICAT, MCT and BAAT capital guidelines and collecting the LF1/LF2/LF3, PC1-PC4 and MI1-MI5 regulatory returns. It does NOT regulate market conduct; that sits with the provinces (FSRA in Ontario, AMF in Quebec), and Canada has no open-insurance mandate — Consumer-Driven Banking excludes insurance entirely. OSFI publishes no first-party developer portal and no OpenAPI — developer.osfi-bsif.gc.ca, api.osfi-bsif.gc.ca and docs.osfi-bsif.gc.ca do not resolve, and /developers, /api and /developer all return 404. Its real machine-readable surface is its insurance and banking regulatory data (FINDAT) plus the "Who we regulate" register, published as datastore-active datasets on Canada's Open Government portal and readable anonymously through the CKAN 3 Action API (datastore_search; the SQL passthrough datastore_search_sql is disabled on the portal) — OSFI ships a step-by-step API usage guide PDF with each dataset. The filing side (the Regulatory Reporting System) is institution-gated behind a Bank of Canada Connect login. Everything else is a documentation-and-rulebook corpus of 313 guidance-library pages and 142 financial reporting instruction pages.

**Areas:** Insurance · Canada · Regulator · Life Insurance · Property and Casualty · Financial Regulation · Prudential Supervision · Open Data · Risk Data · Market Infrastructure · Banking · Basel III

## OSFI on APIs.io

Everything profiled for OSFI is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/osfi/](https://apis.io/providers/osfi/)** — or go straight to one of the APIs or properties below.

### APIs (9)

- [OSFI Who We Regulate Register](https://apis.io/apis/osfi/osfi-who-we-regulate-register/) — Public register of the federally regulated financial institutions OSFI supervises, including every federally regulated insurer with its Authorized Insurance…
- [OSFI Life Insurance Companies Financial Data](https://apis.io/apis/osfi/osfi-life-insurance-financial-data/) — Publicly disclosable regulatory returns filed by federally regulated life insurance companies — LCA/LCQ (LICAT capital), LF1 Life Core Financial Statement…
- [OSFI Property and Casualty Companies Financial Data](https://apis.io/apis/osfi/osfi-property-casualty-financial-data/) — Publicly disclosable regulatory returns filed by federally regulated property and casualty insurers and mortgage insurers — PC1 P&C Core Financial Statement…
- [OSFI Fraternal Benefit Societies Financial Data](https://apis.io/apis/osfi/osfi-fraternal-benefit-societies-financial-data/) — Publicly disclosable regulatory returns filed by federally regulated fraternal benefit societies — the LICAT (LCA/LCQ) and LF1/LF2/LF3 life-return series…
- [OSFI Banks Financial Data](https://apis.io/apis/osfi/osfi-banks-financial-data/) — Publicly disclosable regulatory returns filed by federally regulated banks — M4 Consolidated Balance Sheet, BA BASEL III Capital Adequacy Reporting (BCAR),…
- [OSFI Foreign Bank Branches Financial Data](https://apis.io/apis/osfi/osfi-foreign-bank-branches-financial-data/) — Publicly disclosable regulatory returns filed by foreign bank branches operating in Canada — M4 Consolidated Balance Sheet, E3 Return of Allowances for…
- [OSFI Trust Companies Financial Data](https://apis.io/apis/osfi/osfi-trust-companies-financial-data/) — Publicly disclosable regulatory returns filed by federally regulated trust companies — M4 Consolidated Balance Sheet, BA BASEL III Capital Adequacy…
- [OSFI Loan Companies Financial Data](https://apis.io/apis/osfi/osfi-loan-companies-financial-data/) — Publicly disclosable regulatory returns filed by federally regulated loan companies — M4 Consolidated Balance Sheet, BA BASEL III Capital Adequacy Reporting…
- [OSFI Retail Associations Financial Data](https://apis.io/apis/osfi/osfi-retail-associations-financial-data/) — Publicly disclosable regulatory returns filed by federally regulated cooperative retail associations — M4 Consolidated Balance Sheet, BA BASEL III Capital…

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [osfi](https://apis.io/servers/osfi/osfi/)

#### JSON Schema (4)

The data models the API reads and writes.

- [OSFI FINDAT regulatory-return data point (fiscal-quarter return series)](https://apis.io/schemas/osfi/osfi-financial-return-datapoint/)
- [OSFI FINDAT regulatory-return data point (calendar-month return series)](https://apis.io/schemas/osfi/osfi-financial-return-datapoint-monthly/)
- [OSFI Who We Regulate — federally regulated financial institution record](https://apis.io/schemas/osfi/osfi-who-we-regulate-financial-institutions/)
- [OSFI Who We Regulate — federally regulated private pension plan record](https://apis.io/schemas/osfi/osfi-who-we-regulate-private-pension-plans/)

#### JSON-LD (9)

Linked-data contexts for the provider's vocabulary.

- [Osfi Banks Context](https://apis.io/jsonld/osfi/osfi-banks/)
- [Osfi Foreign Bank Branches Context](https://apis.io/jsonld/osfi/osfi-foreign-bank-branches/)
- [Osfi Fraternal Benefit Societies Context](https://apis.io/jsonld/osfi/osfi-fraternal-benefit-societies/)
- [Osfi Life Insurance Context](https://apis.io/jsonld/osfi/osfi-life-insurance/)
- [Osfi Loan Companies Context](https://apis.io/jsonld/osfi/osfi-loan-companies/)
- [Osfi Property Casualty Context](https://apis.io/jsonld/osfi/osfi-property-casualty/)
- [Osfi Retail Associations Context](https://apis.io/jsonld/osfi/osfi-retail-associations/)
- [Osfi Trust Companies Context](https://apis.io/jsonld/osfi/osfi-trust-companies/)
- [Osfi Who We Regulate Context](https://apis.io/jsonld/osfi/osfi-who-we-regulate/)

#### Vocabulary (1)

The provider's domain terms, defined.

- [OSFI Glossary of Terms — Reporting Manual for Deposit-Taking Institutions Vocabulary](https://apis.io/vocabularies/osfi/osfi-vocabulary/)

#### Examples (6)

Example requests and responses.

- [Osfi Datastore Search Banks Bcar Example](https://apis.io/examples/osfi/osfi-datastore-search-banks-bcar-example/)
- [Osfi Datastore Search Life Lf1 Example](https://apis.io/examples/osfi/osfi-datastore-search-life-lf1-example/)
- [Osfi Datastore Search Not Found Example](https://apis.io/examples/osfi/osfi-datastore-search-not-found-example/)
- [Osfi Datastore Search Pc1 Example](https://apis.io/examples/osfi/osfi-datastore-search-pc1-example/)
- [Osfi Datastore Search Who We Regulate Example](https://apis.io/examples/osfi/osfi-datastore-search-who-we-regulate-example/)
- [Osfi Package Search Example](https://apis.io/examples/osfi/osfi-package-search-example/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Osfi Authentication](https://apis.io/security/osfi/osfi-authentication/)
- [Osfi Domain Security](https://apis.io/security/osfi/osfi-domain-security/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Osfi Plans Pricing](https://apis.io/plans/osfi/osfi-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Osfi Rate Limits](https://apis.io/rate-limits/osfi/osfi-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.osfi-bsif.gc.ca/en)
- [Documentation](https://www.osfi-bsif.gc.ca/en/data-forms)
- [Getting started](https://www.osfi-bsif.gc.ca/en/data-forms/open-government-osfi-financial-data/working-open-government-data)
- [API reference](https://docs.ckan.org/en/2.10/api/index.html)
- [Support](https://www.osfi-bsif.gc.ca/en/contact-us)
- [Terms of service](https://www.osfi-bsif.gc.ca/en/terms-conditions)
- [Privacy policy](https://www.osfi-bsif.gc.ca/en/transparency/access-information-privacy)

## API Evangelist rating

**Kin Score 45.6** — developing · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 79.5 |
| Contract quality | 25.2 |
| Contract governance | 33.3 |
| Operational transparency | 52.6 |
| Developer ergonomics | 56.5 |
| Access clarity | 42.1 |

**Agent readiness 10.1** — agent-aware

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | — |
| Agentic Access | — |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | documented (partial credit) |
| OpenAPI Examples | documented (partial credit) |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | — |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | na |
| Operation Distinctiveness | na |

**Regulatory alignment 21.9** — Insurance

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/osfi/](https://apis.io/providers/osfi/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for OSFI: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/osfi/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
