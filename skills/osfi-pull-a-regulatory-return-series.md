---
name: Pull an OSFI regulatory return series
description: Read FINDAT regulatory-return data points (capital adequacy, balance sheet, income) for banks, insurers, trust and loan companies out of the Open Government datastore.
api: https://open.canada.ca/data/en/api/3/action
provider: OSFI
actions:
  - package_search
  - package_show
  - datastore_info
  - datastore_search
generated: '2026-07-25'
method: generated
source: live CKAN Action API probes; conventions/osfi-conventions.yml
---
## When to use

Use this to get actual reported numbers — LICAT and MCT capital, BCAR/Basel III capital adequacy,
consolidated balance sheet, income — for federally regulated Canadian institutions.

## Contract

- Base: `https://open.canada.ca/data/en/api/3/action`
- Auth: **none**. Browser `User-Agent` required.
- `datastore_search_sql` is **disabled** here (HTTP 400). Use `datastore_search` filters.

## Steps

1. Find the sector dataset:

   ```
   GET /package_search?fq=organization:osfi-bsif&rows=100
   ```

   Nine datasets carry datastore-active resources: Banks, Foreign bank branches, Trust companies,
   Loan companies, Retail associations, Life insurance companies, Fraternal benefit societies,
   Property and casualty companies, and Who we regulate.

2. Pick the return series with `package_show` and take the `resource_id` of the series you want.
   Series titled `(Active)` are current; series titled `(Inactive Qx/YYYY)` stopped being collected
   in that quarter but remain queryable for history.

3. Optionally inspect columns first:

   ```
   GET /datastore_info?id=<resource_id>
   ```

4. Query the fact table:

   ```
   GET /datastore_search?resource_id=f3ddcfbc-a852-4dee-be3c-5b08864c9afe&filters={"Fiscal Year/Annee fiscale":"2026"}&limit=1000
   ```

   Verified resource ids (2026-07-25): LF1 life core `f3ddcfbc-a852-4dee-be3c-5b08864c9afe`
   (531,347 records) · PC1 P&C core `d4c1d98d-c19e-4730-ab2d-6e64160351a7` (693,693) ·
   banks BA/BCAR `fe7617f7-a676-4966-aae3-c4cfbab4b935` (299,223) · banks M4 consolidated balance
   sheet `d0f6040e-671c-4301-a235-e9e7ba164604` (1,555,044).

5. Interpret the row: `Id` is the institution, `Return/Releve` + `Return Title` the return,
   `Data Point Address/Adresse de point de donnee` + `Data Point Address Label` the cell, the period
   is `Fiscal Year` + `Fiscal Quarter` (quarterly series) or `Calendar Year` + `Calendar Month`
   (monthly series), and `Measure Value/Valeur de mesure` is the number.

## Rules

- **Cast the numbers yourself.** Every column, including `Measure Value`, is typed `text`.
- **Pick a language side.** Columns come in English/French pairs.
- Never invent a cell meaning. Resolve `Data Point Address Label` against the financial reporting
  instructions and `vocabulary/osfi-vocabulary.yml`.
- These are millions of rows. Page with `limit` + `offset`; do not request whole series in one call.
- Publication cadence: monthly data on the 15th, quarterly data in late May, August, November and
  March. Query for a quarter that has not been published yet and you get zero records, not an error.
