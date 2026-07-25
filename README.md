# OSFI (osfi)

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
