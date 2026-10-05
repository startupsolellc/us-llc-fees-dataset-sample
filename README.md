# US LLC State Requirements Dataset — Preview Sample

![Jurisdictions](https://img.shields.io/badge/Full_dataset-51_jurisdictions-blue?style=flat-square)
![Sources](https://img.shields.io/badge/Verified-Official_state_publishers-blue?style=flat-square)
![Format](https://img.shields.io/badge/Format-JSON-orange?style=flat-square)
![License](https://img.shields.io/badge/License-All_rights_reserved-red?style=flat-square)

> **This is a preview, not the dataset.** It publishes one complete, unmodified record from each
> namespace of the **US LLC State Requirements Dataset** so the structure, depth and sourcing of
> the data can be inspected. The full dataset is maintained in a private repository,
> `startupsolellc/us-llc-fees-dataset`, and is available under licence only.
> **To use the data — this sample or the full dataset — [get in touch](#access-and-licensing).**

## What the full dataset is

A machine-readable dataset of **US limited liability company formation costs, naming rules,
assumed-name (DBA) filing rules, taxes, processing times and recurring compliance facts**,
covering all 50 states and the District of Columbia.

Every field is hand-verified against official state government sources: statutes,
administrative codes, Secretary of State pages, and state fee schedules. Every record carries
the sources it was built from and the date it was last checked. The dataset is actively
maintained; the records here are a snapshot taken on **2026-10-05**.

## What is in this preview

One record per namespace, copied byte-for-byte from the full dataset, plus the JSON Schemas.

| Namespace | Full dataset | Record in this preview | Last verified | What the namespace covers |
|---|---|---|---|---|
| `states.json` | 50 states | Wyoming | 2026-09-03 | Formation fee, annual report fee and due date, official links |
| `entitysearch-state-data/` | 51 | [Delaware](entitysearch-state-data/states/delaware.json) | 2026-08-22 | Agency contact details, addresses, hours, business entity search portals, renewal links, filing facts |
| `name-rules/` | 51 | [Florida](name-rules/states/florida.json) | 2026-07-17 | LLC name designators, distinguishability standard, restricted words, name reservation cost, hold period and processing time, naming statutes |
| `dba-rules/` | 51 | [Texas](dba-rules/states/texas.json) | 2026-07-17 | DBA terminology, filing level (state or county), fees, duration and renewal, publication requirements, statutes |
| `tax-rules/` | 51 | [California](tax-rules/states/california.json) | 2026-08-08 | Recurring state-level LLC taxes and the personal income tax posture toward a default pass-through LLC |
| `processing-time/` | 51 | [Maryland](processing-time/states/maryland.json) | 2026-08-09 | Expedite tiers for LLC formation (fee, turnaround, channels) and the standard processing time |
| `foreign-qualification/` | 51 | [Washington](foreign-qualification/states/washington.json) | 2026-08-08 | Registering an out-of-state LLC: fee, official form, the agency that takes it, ongoing obligations |
| `agent-rules/` | 51 | [Nevada](agent-rules/states/nevada.json) | 2026-08-09 | Who may serve as an LLC's registered agent and the address rule in the state's own words |
| `compliance-rules/` | 51 | [Illinois](compliance-rules/states/illinois.json) | 2026-08-11 | Late fees, how long delinquency may run before administrative dissolution, reinstatement cost |
| `filing-deadlines/` | 6 (expanding to 51) | [Delaware](filing-deadlines/states/delaware.json) | 2026-08-22 | A typed projection for the next periodic-report date or window |
| `anonymous_llc_available/` | 51 | New Mexico | 2026-08-10 | Whether an LLC's ownership can be kept off the public record, derived from the state's own filings |

"51" means the 50 states plus the District of Columbia.

The two root-level files (`states.json`, `anonymous_llc_available/states.json`) hold every
jurisdiction in a single file in the full dataset. Here they are cut down to one record each;
their header carries a `note` saying so. Every file under a `states/` directory is an exact copy.

## How to check that it is real

Each record names the official pages it was read from. Open any `sources[].url`, `source_url`
or `statuteUrl` in a record and compare it with the value next to it. In the newer namespaces
(`tax-rules`, `processing-time`, `foreign-qualification`, `agent-rules`, `compliance-rules`)
every value is bound to a verbatim `quote` from the cited page, so the check is a text search
on the official page.

Fees and rules change without notice, and a record is only as current as its `lastVerified`
date.

## Methodology in brief

- **Official sources only.** A source is official when the government body responsible for the
  fact publishes it: a Secretary of State, a Division of Corporations, a state legislature or
  law revisor, a tax authority, or the county office that takes the filing.
- **No third parties.** Blogs, formation-service pages and commercial legal aggregators are not
  accepted as sources, including as corroboration.
- **Provenance per record.** Every record carries its sources and a `lastVerified` date, meaning
  the cited sources were opened on that date and the values confirmed.
- **Real cost, not only the statutory fee.** Where the amount a filer actually pays differs from
  the fee the statute names, both are recorded and the difference explained.
- **Nothing estimated.** Where a state does not publish a fact, the field is `null` and the
  record says why, rather than carrying a guess.

## Joining namespaces

A jurisdiction carries the same `stateSlug` — which is also its filename — in every per-state
namespace. `stateAbbr` is the stable identifier across all of them, including the two root-level
files, which key by abbreviation. In this preview, Delaware appears in both
`entitysearch-state-data` and `filing-deadlines` to show a join: the deadline record's `lineage`
points into the entity-search record.

## Access and licensing

This repository is **not open data**. All rights are reserved; see [LICENSE](LICENSE).

You may read and evaluate the files here. Any other use — copying the data into a product,
website, dataset or model, redistributing it, or building on it commercially or otherwise —
requires prior written permission.

To request a licence for the full dataset, or permission to use this sample,
**[open an issue in this repository](../../issues/new)** describing who you are and what you
intend to do with the data.

## Disclaimer

This is a dataset, not legal advice. State requirements change without notice. Verify any figure
against the official source cited in the record before relying on it. Only the relevant state
agency can decide an actual filing.

---

© 2026 StartupSole LLC. All rights reserved.
