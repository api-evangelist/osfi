---
name: Discover what OSFI publishes machine-readably
description: Enumerate OSFI's datasets, their DCAT descriptions and their datastore-active resources before writing any integration.
api: https://open.canada.ca/data/en/api/3/action
provider: OSFI
actions:
  - status_show
  - package_search
  - package_show
generated: '2026-07-25'
method: generated
source: live CKAN Action API probes; conventions/osfi-conventions.yml
---
## When to use

Use this first, before any OSFI integration, and whenever a resource id stops resolving.

## Contract

- Base: `https://open.canada.ca/data/en/api/3/action`
- OSFI operates **no developer portal and no OpenAPI**. `developer.osfi-bsif.gc.ca`,
  `api.osfi-bsif.gc.ca` and `docs.osfi-bsif.gc.ca` do not resolve; `/developers`, `/api` and
  `/developer` on the corporate site return 404. Do not look for a spec — there is none.

## Steps

1. Confirm the platform:

   ```
   GET /status_show
   ```

   Returns the CKAN version (2.10.8 on 2026-07-25) and enabled extensions, including `dcat`,
   `dcat_json_interface`, `datastore` and `power_bi_view`.

2. List OSFI's datasets:

   ```
   GET /package_search?fq=organization:osfi-bsif&rows=100
   ```

   36 datasets on 2026-07-25; only the ones with a resource whose `datastore_active` is `true` are
   API-queryable. The rest are file downloads.

3. Read the DCAT description of any dataset in RDF terms:

   ```
   GET https://open.canada.ca/data/en/dataset/<package_id>.jsonld
   ```

   `.rdf` and `.ttl` work at the same path. Copies of all nine are saved under `json-ld/`.

4. For each dataset of interest, `package_show` and record the resource ids you need. Re-run this
   step whenever a `Not Found Error` appears — resource ids can rotate when OSFI republishes.

## Rules

- Every dataset ships three human companions: a data dictionary, a user manual, and a step-by-step
  API access guide (PDF). Read the data dictionary before interpreting any column.
- The FILING side is not part of this surface. Institutions submit returns through the Regulatory
  Reporting System behind a Bank of Canada Connect login (HTTP 401 anonymously) and there is no
  programmatic filing interface.
- The successor platform, the Regulatory Data Hub, is stated to go live late fall 2026 with no
  published API contract. Do not assume continuity of resource ids across that migration.
