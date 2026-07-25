---
name: Look up a federally regulated financial institution
description: Find an institution OSFI supervises in the Who We Regulate register and read its type, industry group, trade name, principal representative and authorized insurance classes.
api: https://open.canada.ca/data/en/api/3/action
provider: OSFI
actions:
  - package_show
  - datastore_search
generated: '2026-07-25'
method: generated
source: live CKAN Action API probes; conventions/osfi-conventions.yml
---
## When to use

Use this when you need to confirm whether a company is federally regulated in Canada, what kind of
institution it is, or which insurance classes it is authorized to write. This is the register, not
financial data.

## Contract

- Base: `https://open.canada.ca/data/en/api/3/action`
- Auth: **none**. Send no credentials.
- **Send a browser `User-Agent`.** A default curl/script UA gets an HTML "Request Rejected" page
  under HTTP 200. Assert `Content-Type: application/json` before parsing.

## Steps

1. Confirm the register resource is still current with `package_show`:

   ```
   GET /package_show?id=b27ec3ef-7338-4e76-a6fd-128339a92df5
   ```

   Use the resource whose `datastore_active` is `true`. On 2026-07-25 the English financial-institution
   file is `945045fa-2de0-47d4-aad2-144d69467824` (349 records) and the private-pension-plan file is
   `2282e8c7-f949-454d-9c34-b6a78d94b162` (1,002 records).

2. Search by name with `datastore_search`:

   ```
   GET /datastore_search?resource_id=945045fa-2de0-47d4-aad2-144d69467824&q=Manulife&limit=10
   ```

   For an exact column match use `filters`:

   ```
   GET /datastore_search?resource_id=945045fa-2de0-47d4-aad2-144d69467824&filters={"FI Industry Name":"Life Insurance Companies"}&limit=100
   ```

3. Read the answer from `result.records[]`. Fields: `Company Name`, `FI Type Name`, `FI Group Name`,
   `FI Industry Name`, `Canadian Trade Company Name`, `Representative Name`, `Title`, address fields,
   `Authorized Insurance Classes`. Schema: `json-schema/osfi-who-we-regulate-financial-institutions.json`.

4. Page with `limit` + `offset`; `result.total` gives the count and `result._links.next` gives the
   next page.

## Rules

- `_id` is a CKAN row id. Never present it as an OSFI identifier.
- The register is refreshed monthly on the 1st. Do not treat it as real time.
- Absence from the register means *not federally regulated* — it does not mean unregulated.
  Provincial regulators (FSRA, AMF) supervise separately.
- If you get `{"success": false, "error": {"__type": "Not Found Error"}}`, the resource id has
  rotated: re-run step 1.
