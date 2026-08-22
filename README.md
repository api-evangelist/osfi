# OSFI (osfi)

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

The Office of the Superintendent of Financial Institutions (OSFI / BSIF) is Canada's federal prudential regulator, supervising more than 400 federally regulated financial institutions and over 1,200 private pension plans. On the insurance side it supervises federally regulated life insurance companies, property and casualty insurers, mortgage insurers and fraternal benefit societies for solvency and capital adequacy — issuing the LICAT, MCT and BAAT capital guidelines and collecting the LF1/LF2/LF3, PC1–PC4 and MI1–MI5 regulatory returns. Market conduct is not OSFI's remit; that sits with the provinces (FSRA in Ontario, AMF in Quebec), and Canada has no open-insurance mandate — Consumer-Driven Banking excludes insurance entirely.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/osfi/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/osfi/refs/heads/main/apis.yml)

## Tags

- Insurance
- Canada
- Regulator
- Life Insurance
- Property and Casualty
- Financial Regulation
- Prudential Supervision
- Open Data
- Risk Data
- Market Infrastructure

## Timestamps

- **Created:** 2026-07-25
- **Modified:** 2026-07-25

## API posture

OSFI operates **no first-party developer portal**. `developer.osfi-bsif.gc.ca`, `developers.osfi-bsif.gc.ca`, `docs.osfi-bsif.gc.ca` and `api.osfi-bsif.gc.ca` do not resolve, and `/developers`, `/developer`, `/api` all return HTTP 404. There is no OpenAPI, Swagger, AsyncAPI, GraphQL, gRPC or public Postman collection.

What OSFI does publish machine-readably is real. Its insurance regulatory returns (FINDAT) and its "Who we regulate" register are pushed to Canada's Open Government portal as datastore-active CKAN datasets and can be read **anonymously** over the CKAN 3 Action API. OSFI ships a step-by-step API usage guide PDF alongside each dataset, so the API route is explicitly sanctioned. This is Canada's closest analogue to the FCA Financial Services Register API — but it is Government-of-Canada CKAN infrastructure, not an OSFI-branded API product.

The filing side is institution-gated: insurers submit their returns through the Regulatory Reporting System behind a Bank of Canada Connect login (HTTP 401 anonymously). The successor Regulatory Data Hub, part of the Data Collection Modernization project, is stated to go live in late fall 2026 with no published API contract.

**ACORD posture: no ACORD reference found.** Zero of the 3,622 URLs in the osfi-bsif.gc.ca sitemap mention ACORD, AL3, ACORD XML, NGDS or IVANS. OSFI collects insurance data in its own return schemas, which is expected for a prudential supervisor — ACORD governs carrier/broker policy and claims transactions, not solvency reporting.

None of the four insurance API verbs — quote, bind, issue, FNOL — are exposed. OSFI writes no policies and settles no claims.

## APIs

### OSFI Who We Regulate Register

Public register of the federally regulated financial institutions OSFI supervises, including every federally regulated insurer with its Authorized Insurance Classes, FI industry group, trade name and principal representative. Confirmed live 2026-07-25 — 349 institution records.

- **Human URL:** [https://open.canada.ca/data/en/dataset/b27ec3ef-7338-4e76-a6fd-128339a92df5](https://open.canada.ca/data/en/dataset/b27ec3ef-7338-4e76-a6fd-128339a92df5)
- **Base URL:** `https://open.canada.ca/data/en/api/3/action`

### OSFI Life Insurance Companies Financial Data

LCA/LCQ (LICAT capital), LF1 Life Core Financial Statement Return, LF2 Life Supervisory Quarterly Return and LF3 Life Supervisory Annual Return, plus inactive legacy returns — 13 datastore-active CSV resources. Confirmed live 2026-07-25; the LF1 resource alone returns 531,347 records.

- **Human URL:** [https://open.canada.ca/data/en/dataset/1358284b-26e7-4c69-abd8-398d3da2c270](https://open.canada.ca/data/en/dataset/1358284b-26e7-4c69-abd8-398d3da2c270)
- **Base URL:** `https://open.canada.ca/data/en/api/3/action`

### OSFI Property and Casualty Companies Financial Data

PC1 P&C Core Financial Statement Return, PC2/PC3 supervisory returns, PC4 Minimum Capital Test and Branch Adequacy of Assets Test, and the MI/MI3/MI4/MI5 mortgage-insurance series — 14 datastore-active CSV resources. Confirmed live 2026-07-25; the PC1 resource returns 693,693 records.

- **Human URL:** [https://open.canada.ca/data/en/dataset/4c6c515f-7c44-4bb6-ab56-c5f79f75f705](https://open.canada.ca/data/en/dataset/4c6c515f-7c44-4bb6-ab56-c5f79f75f705)
- **Base URL:** `https://open.canada.ca/data/en/api/3/action`

### OSFI Fraternal Benefit Societies Financial Data

The LICAT (LCA/LCQ) and LF1/LF2/LF3 life-return series applied to Canada's mutual-aid insurers, plus inactive legacy returns — 13 datastore-active CSV resources.

- **Human URL:** [https://open.canada.ca/data/en/dataset/7ad44bfe-aa26-4b5b-930b-e7845023dd4c](https://open.canada.ca/data/en/dataset/7ad44bfe-aa26-4b5b-930b-e7845023dd4c)
- **Base URL:** `https://open.canada.ca/data/en/api/3/action`

### OSFI Banks Financial Data

M4 Consolidated Balance Sheet, BA BASEL III Capital Adequacy Reporting (BCAR), E3 Allowances for Expected Credit Losses, LR Leverage Requirements Return and P3 Consolidated Statement of Income — seven datastore-active CSV resources. Confirmed live 2026-07-25; M4 returns 1,555,044 records and BCAR returns 299,223.

- **Human URL:** [https://open.canada.ca/data/en/dataset/91ed76b4-a1a2-4f87-9c4c-59cd64f7a9de](https://open.canada.ca/data/en/dataset/91ed76b4-a1a2-4f87-9c4c-59cd64f7a9de)
- **Base URL:** `https://open.canada.ca/data/en/api/3/action`

### OSFI Foreign Bank Branches Financial Data

M4, E3, K3 Supplementary Return for Foreign Bank Branches and P3 — five datastore-active CSV resources. Confirmed live 2026-07-25; K3 returns 28,337 records.

- **Human URL:** [https://open.canada.ca/data/en/dataset/c6879faf-2bc7-4c84-999c-0626ae33ec84](https://open.canada.ca/data/en/dataset/c6879faf-2bc7-4c84-999c-0626ae33ec84)
- **Base URL:** `https://open.canada.ca/data/en/api/3/action`

### OSFI Trust Companies Financial Data

M4, BA/BCAR, E3, LR and P3 — six datastore-active CSV resources. Confirmed live 2026-07-25; M4 returns 895,465 records.

- **Human URL:** [https://open.canada.ca/data/en/dataset/203bb08d-fdff-46f6-93ec-00e5d1d76a81](https://open.canada.ca/data/en/dataset/203bb08d-fdff-46f6-93ec-00e5d1d76a81)
- **Base URL:** `https://open.canada.ca/data/en/api/3/action`

### OSFI Loan Companies Financial Data

M4, BA/BCAR, E3, LR and P3 — six datastore-active CSV resources. Confirmed live 2026-07-25; M4 returns 301,455 records.

- **Human URL:** [https://open.canada.ca/data/en/dataset/79c99c29-deff-4093-9c55-fde484d20028](https://open.canada.ca/data/en/dataset/79c99c29-deff-4093-9c55-fde484d20028)
- **Base URL:** `https://open.canada.ca/data/en/api/3/action`

### OSFI Retail Associations Financial Data

M4, BA/BCAR, E3, LR and P3 for federally regulated cooperative retail associations — six datastore-active CSV resources. Confirmed live 2026-07-25; M4 returns 19,480 records.

- **Human URL:** [https://open.canada.ca/data/en/dataset/af61ecdd-1a40-4630-8e75-1470e721f318](https://open.canada.ca/data/en/dataset/af61ecdd-1a40-4630-8e75-1470e721f318)
- **Base URL:** `https://open.canada.ca/data/en/api/3/action`

## Artifacts

Enrichment round 2026-07-25. Everything below was probed live against `https://open.canada.ca/data/en/api/3/action`; nothing is fabricated.

- [`conventions/`](conventions/osfi-conventions.yml) — the CKAN 3 Action API contract as OSFI exposes it: 13 verified actions, limit/offset pagination with `_links`, the `{help, success, result}` envelope, the bilingual/all-text column shape, and two gotchas (the WAF rejects non-browser User-Agents; `datastore_search_sql` is **disabled**, HTTP 400).
- [`errors/`](errors/osfi-problem-types.yml) — the CKAN error envelope (not RFC 9457), with live-captured 404 and 400 cases and the HTML-under-HTTP-200 WAF failure mode.
- [`authentication/`](authentication/osfi-authentication.yml) — two surfaces, two models: anonymous read, gated human filing.
- [`lifecycle/`](lifecycle/osfi-lifecycle.yml) — CKAN v3 path versioning, OSFI's publication calendar, and deprecation-in-the-open (retired return series stay queryable, re-labelled `(Inactive Qx/YYYY)`).
- [`changelog/`](changelog/osfi-changelog.yml) — the Glossary of Terms Change Control Log: four dated amendments, including the 2018 rename of "Allowance for Impairment" to "Allowance for Expected Credit Losses".
- [`vocabulary/`](vocabulary/osfi-vocabulary.yml) — OSFI's published Glossary of Terms, the controlled vocabulary for the returns.
- [`conformance/`](conformance/osfi-conformance.yml) — what it conforms to (CKAN 3, DCAT, JSON-LD/RDF/Turtle, OGL-Canada, IFRS, Basel III) and what it does not (OpenAPI, OAuth, RFC 9457, ACORD).
- [`json-ld/`](json-ld/) — DCAT descriptions of all nine datastore-active datasets, saved verbatim.
- [`json-schema/`](json-schema/) — record schemas derived from the live datastore field lists.
- [`examples/`](examples/) — real captured request/response pairs, including the error case.
- [`data-model/`](data-model/osfi-data-model.yml) — the register/fact-table entity graph and the full resource catalog.
- [`skills/`](skills/_index.yml) — three agent skills grounded in verified actions and resource ids.
- [`mcp/`](mcp/osfi-mcp.yml) — a candidate MCP tool surface (no server is published).
- [`llms/`](llms/osfi-llms.txt), [`packages/`](packages/osfi-packages.yml), [`well-known/`](well-known/osfi-well-known.yml), [`rate-limits/`](rate-limits/osfi-rate-limits.yml), [`plans/`](plans/osfi-plans-pricing.yml), [`security/`](security/osfi-domain-security.yml).

## Links

- [Website](https://www.osfi-bsif.gc.ca/en)
- [Data and forms](https://www.osfi-bsif.gc.ca/en/data-forms)
- [Financial data on Open Government](https://www.osfi-bsif.gc.ca/en/data-forms/open-government-osfi-financial-data)
- [Working with Open Government data](https://www.osfi-bsif.gc.ca/en/data-forms/open-government-osfi-financial-data/working-open-government-data)
- [Guidance library](https://www.osfi-bsif.gc.ca/en/guidance/guidance-library)
- [Financial reporting instructions](https://www.osfi-bsif.gc.ca/en/data-forms/reporting-returns/filing-financial-returns/financial-reporting-instructions)
- [Reporting and returns](https://www.osfi-bsif.gc.ca/en/data-forms/reporting-returns)
- [Modernizing how we collect data from institutions](https://www.osfi-bsif.gc.ca/en/about-osfi/progress-our-initiatives/modernizing-we-collect-data-institutions)
- [OSFI datasets on Open Government](https://search.open.canada.ca/opendata/?owner_org=osfi-bsif)
- [Regulatory Reporting System sign-in (gated)](https://connect-connexion.bank-banque-canada.ca/igw/apps/ami/portal/login)
- [News](https://www.osfi-bsif.gc.ca/en/news)
- [LinkedIn](https://www.linkedin.com/company/office-of-the-superintendent-of-financial-institutions-of-canada)
- [X (Twitter)](https://twitter.com/OSFICanada)
- [YouTube](https://www.youtube.com/user/OSFIBSIF)
