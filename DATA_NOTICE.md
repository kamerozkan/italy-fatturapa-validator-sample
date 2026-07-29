# Data Notice

## Purpose

This repository is a technical sample for the [Italy FatturaPA Validator](https://apify.com/kamerozkan/italy-fatturapa-validator). It contains three real Actor output rows and a standalone JSON Schema.

This is an independent, unofficial product. It is not affiliated with, sponsored by, or endorsed by Agenzia delle Entrate, Sogei, Sistema di Interscambio, any tax authority, or any invoice recipient.

## Audit snapshot

| Item | Verified value |
|---|---|
| Actor | `kamerozkan/italy-fatturapa-validator` |
| Actor ID | `wGcRt736F8h1gEuqL` |
| Successful run | `95PRKHFR5WAZGlx7n` |
| Build | `0.0.2`, build ID `BRX5nIlR1onFJjVS3` |
| Dataset | `VwGNYgKd34KDOfiEM`, 3 records |
| Run time | 2026-07-29 |
| Charged validation events | 2 |

The run and dataset identifiers are included for owner-side provenance. This repository does not claim that either resource is publicly readable.

## Output provenance

- [`01_live_accepted_output.json`](01_live_accepted_output.json) is the verbatim accepted dataset row.
- [`02_live_rejected_output.json`](02_live_rejected_output.json) is the verbatim rejected dataset row.
- [`03_live_not_evaluated_output.json`](03_live_not_evaluated_output.json) is the verbatim unsupported-syntax dataset row.

The records were generated from synthetic release-test inputs. No omitted value was inferred, reconstructed, or converted into a success claim.

## Artifact boundary

The Actor bundles pinned compatibility schemas derived from Apache-2.0 open-source baselines. The output states `schemaSource: OPEN_SOURCE_DERIVED` and `officialArtifactsBundled: false`. The repository and Actor do not present those derived schemas as official Agenzia delle Entrate or SdI artifacts.

The Actor does not contact or submit to SdI. External state, transmission, recipient, duplicate-history, and downstream acceptance checks are reported as `NOT_EVALUATED_EXTERNAL_STATE`.

## Privacy and security

This repository contains no customer invoice, raw XML, base64 payload, report body, access token, cookie, signed URL, webhook URL, email address, IBAN, customer account identifier, or private key.

Real invoice validation can process personal, financial, tax, and commercial data. Users remain responsible for lawful processing, access control, retention, deletion, and all applicable privacy, tax, accounting, database, and contractual requirements.

## Interpretation limits

- `ACCEPTED` means the submitted bytes passed the required offline technical checks pinned in the result.
- `REJECTED` means processing completed and at least one required offline technical check failed.
- `NOT_EVALUATED` means no technical decision was possible.
- A result does not prove legal or tax validity, authenticity, authorization, delivery, payment, or recipient acceptance.
- A result does not guarantee acceptance by SdI, Agenzia delle Entrate, an ERP, a recipient, a tax authority, or another downstream system.

Check the Actor page for the current rules, supported profiles, pricing, and limits before production use.

## License boundary

The MIT License applies only to the original documentation, output samples, and JSON Schema committed here. It does not relicense FatturaPA specifications, SdI material, validator software, schema baselines, test documents, third-party names, marks, or source data.
