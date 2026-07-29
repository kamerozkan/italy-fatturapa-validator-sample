> **Live API:** [Run Italy FatturaPA Validator on Apify](https://apify.com/kamerozkan/italy-fatturapa-validator)

# Italy FatturaPA Validator API: Samples and JSON Schema

[![Apify Actor](https://img.shields.io/badge/Apify-Run%20Actor-00c7b7?logo=apify)](https://apify.com/kamerozkan/italy-fatturapa-validator)
![Profiles](https://img.shields.io/badge/FatturaPA-FPA12%20%7C%20FPR12%20%7C%20FSM10-005EA8)
![Validation](https://img.shields.io/badge/scope-OFFLINE__PREFLIGHT-137333)
![Samples](https://img.shields.io/badge/samples-3%20verified%20live%20rows-2f855a)
![License](https://img.shields.io/badge/license-MIT-blue)

Run structural and deterministic content checks on FatturaPA XML before submission. The Actor recognizes FPA12, FPR12, and FSM10 profiles, applies pinned open-source-derived compatibility schemas, and reports stable machine-readable findings.

> `ACCEPTED` is an offline technical preflight result. The Actor does not contact or submit to Sistema di Interscambio (SdI), and it does not guarantee SdI acceptance, delivery, legal validity, tax validity, authenticity, authorization, or payment.

## Verified repository contents

| File | Meaning |
|---|---|
| [`01_live_accepted_output.json`](01_live_accepted_output.json) | Real accepted FPR12 result |
| [`02_live_rejected_output.json`](02_live_rejected_output.json) | Real rejected FPR12 result with arithmetic and VAT evidence |
| [`03_live_not_evaluated_output.json`](03_live_not_evaluated_output.json) | Real unsupported-syntax result with no technical decision |
| [`dataset_record.schema.json`](dataset_record.schema.json) | JSON Schema 2020-12 contract for one dataset row |
| [`DATA_NOTICE.md`](DATA_NOTICE.md) | Provenance, privacy, artifact, and interpretation limits |

All three JSON rows came from successful Actor run `95PRKHFR5WAZGlx7n`, build `0.0.2`, dataset `VwGNYgKd34KDOfiEM`, on 2026-07-29. The run evaluated two documents and billed exactly two `invoice-validated` events. The `NOT_EVALUATED` unsupported document was not billed.

## Stable decision contract

- `ACCEPTED`: processing completed and no required offline rule failure was found.
- `REJECTED`: processing completed and at least one required offline rule failure was found.
- `NOT_EVALUATED`: the document could not receive a technical decision.
- `externalStateStatus: NOT_EVALUATED_EXTERNAL_STATE`: SdI state, recipient state, duplicate history, transmission outcome, and other external checks were not evaluated.
- `versions.schemaSource: OPEN_SOURCE_DERIVED`: the bundled schemas are compatibility artifacts derived from pinned Apache-2.0 baselines, not official Agenzia delle Entrate artifacts.
- `sha256`: digest of every document that was successfully loaded.

## Real output examples

<details>
<summary><strong>01. ACCEPTED</strong> - FPR12 passes the pinned offline checks</summary>

[`01_live_accepted_output.json`](01_live_accepted_output.json)

```json
{
  "inputIndex": 0,
  "documentId": "accepted-fpr12",
  "fileName": "accepted-fpr12.xml",
  "processingStatus": "SUCCEEDED",
  "conformanceStatus": "ACCEPTED",
  "previewConformanceStatus": "NOT_EVALUATED",
  "validationScope": "OFFLINE_PREFLIGHT",
  "externalStateStatus": "NOT_EVALUATED_EXTERNAL_STATE",
  "rulesetEffectiveAt": "2026-05-15",
  "sourceFormat": "XML",
  "validationFamily": "ITALY_FATTURAPA",
  "syntax": "FATTURAPA_XML",
  "profile": "FPR12",
  "scenario": "FatturaPA FPR12 private-sector invoice",
  "versions": {
    "validationScope": "OFFLINE_PREFLIGHT",
    "schemaSource": "OPEN_SOURCE_DERIVED",
    "officialArtifactsBundled": false,
    "ordinarySchema": {
      "formats": [
        "FPA12",
        "FPR12"
      ],
      "version": "1.2.3",
      "sha256": "10709324b24a5b5ba284bbf595392286cc94446d8b69defb2afd3a4f24f8213a",
      "baselineProject": "phax/ph-fatturapa",
      "baselineVersion": "ph-fatturapa-3.1.0",
      "baselineCommit": "c5fc3a97208bf22e50949b09dd9bd396cb18cc9f",
      "baselineSha256": "f40dda07ffc5790b02bda5fdad39705226c0a2b5bc6d42a60abd65e8e381ea5d",
      "license": "Apache-2.0"
    },
    "simplifiedSchema": {
      "format": "FSM10",
      "version": "1.0.2",
      "sha256": "698d4960a5e6121764e06157aef2593be5ea06fd4ab0938d52185643fcba4c29",
      "baselineProject": "invopop/gobl.fatturapa",
      "baselineVersion": "v0.69.0",
      "baselineCommit": "23b1ae16f7e5a243fa11f77e937912d0814db9e9",
      "baselineSha256": "0ced96c0e61c66eb88bb93f6eed55acabd18d96004a61d5fbf3b2e01ef1fc40f",
      "license": "Apache-2.0"
    },
    "xmlDsigSchemaSha256": "35cf8197da812c85e40d57891b35c94187569ed474a2dac813ce5090dafcd35c",
    "b2gProfile": {
      "schema": "VFPA12 1.2.3 derived compatibility schema",
      "formatSpecification": "FatturaPA 1.4",
      "sdiSpecification": "SdI 1.8.4",
      "controlReference": "Elenco controlli 2.0"
    },
    "b2bProfile": {
      "schemas": "VFPR12 1.2.3 and VFSM10 1.0.2 derived compatibility schemas",
      "technicalReference": "AdE Allegato A 1.9.1",
      "effectiveAt": "2026-05-15"
    },
    "deterministicChecksRevision": "2026-07-29",
    "activeRuleset": {
      "name": "FatturaPA offline profiles current from 2026-05-15",
      "effectiveAt": "2026-05-15"
    },
    "artifactManifestSha256": "0ef44ac189d98b098a988fc9fa7bfc401f0463e7d7458bd9ba63d7c9f8572f3f"
  },
  "counts": {
    "fatal": 0,
    "error": 0,
    "warning": 0,
    "information": 0
  },
  "findings": [],
  "findingsTruncated": false,
  "previewCounts": {
    "fatal": 0,
    "error": 0,
    "warning": 0,
    "information": 0
  },
  "previewFindings": [],
  "previewFindingsTruncated": false,
  "sha256": "a08f1d2bc65d5658860ccf15c5308f89617c87b2e3a5671a550d6288f100b7a7",
  "embeddedXmlSha256": null,
  "container": null,
  "checkedAt": "2026-07-29T10:49:44.442615Z",
  "reports": {},
  "error": null
}
```

</details>

<details>
<summary><strong>02. REJECTED</strong> - deterministic SdI-style arithmetic findings</summary>

[`02_live_rejected_output.json`](02_live_rejected_output.json)

```json
{
  "inputIndex": 1,
  "documentId": "rejected-arithmetic",
  "fileName": "rejected-arithmetic.xml",
  "processingStatus": "SUCCEEDED",
  "conformanceStatus": "REJECTED",
  "previewConformanceStatus": "NOT_EVALUATED",
  "validationScope": "OFFLINE_PREFLIGHT",
  "externalStateStatus": "NOT_EVALUATED_EXTERNAL_STATE",
  "rulesetEffectiveAt": "2026-05-15",
  "sourceFormat": "XML",
  "validationFamily": "ITALY_FATTURAPA",
  "syntax": "FATTURAPA_XML",
  "profile": "FPR12",
  "scenario": "FatturaPA FPR12 private-sector invoice",
  "versions": {
    "validationScope": "OFFLINE_PREFLIGHT",
    "schemaSource": "OPEN_SOURCE_DERIVED",
    "officialArtifactsBundled": false,
    "ordinarySchema": {
      "formats": [
        "FPA12",
        "FPR12"
      ],
      "version": "1.2.3",
      "sha256": "10709324b24a5b5ba284bbf595392286cc94446d8b69defb2afd3a4f24f8213a",
      "baselineProject": "phax/ph-fatturapa",
      "baselineVersion": "ph-fatturapa-3.1.0",
      "baselineCommit": "c5fc3a97208bf22e50949b09dd9bd396cb18cc9f",
      "baselineSha256": "f40dda07ffc5790b02bda5fdad39705226c0a2b5bc6d42a60abd65e8e381ea5d",
      "license": "Apache-2.0"
    },
    "simplifiedSchema": {
      "format": "FSM10",
      "version": "1.0.2",
      "sha256": "698d4960a5e6121764e06157aef2593be5ea06fd4ab0938d52185643fcba4c29",
      "baselineProject": "invopop/gobl.fatturapa",
      "baselineVersion": "v0.69.0",
      "baselineCommit": "23b1ae16f7e5a243fa11f77e937912d0814db9e9",
      "baselineSha256": "0ced96c0e61c66eb88bb93f6eed55acabd18d96004a61d5fbf3b2e01ef1fc40f",
      "license": "Apache-2.0"
    },
    "xmlDsigSchemaSha256": "35cf8197da812c85e40d57891b35c94187569ed474a2dac813ce5090dafcd35c",
    "b2gProfile": {
      "schema": "VFPA12 1.2.3 derived compatibility schema",
      "formatSpecification": "FatturaPA 1.4",
      "sdiSpecification": "SdI 1.8.4",
      "controlReference": "Elenco controlli 2.0"
    },
    "b2bProfile": {
      "schemas": "VFPR12 1.2.3 and VFSM10 1.0.2 derived compatibility schemas",
      "technicalReference": "AdE Allegato A 1.9.1",
      "effectiveAt": "2026-05-15"
    },
    "deterministicChecksRevision": "2026-07-29",
    "activeRuleset": {
      "name": "FatturaPA offline profiles current from 2026-05-15",
      "effectiveAt": "2026-05-15"
    },
    "artifactManifestSha256": "0ef44ac189d98b098a988fc9fa7bfc401f0463e7d7458bd9ba63d7c9f8572f3f"
  },
  "counts": {
    "fatal": 0,
    "error": 2,
    "warning": 0,
    "information": 0
  },
  "findings": [
    {
      "severity": "ERROR",
      "stage": "SDI_DETERMINISTIC",
      "ruleId": "00421",
      "message": "Imposta differs from the rounded VAT calculation by at least EUR 0.01",
      "location": "/FatturaElettronicaBody[1]/DatiBeniServizi/DatiRiepilogo[1]/Imposta",
      "ruleset": "ITALY_FPR_FSM_B2B_DETERMINISTIC_1.9.1"
    },
    {
      "severity": "ERROR",
      "stage": "SDI_DETERMINISTIC",
      "ruleId": "00422",
      "message": "The taxable summary for a VAT rate differs from its lines, pension contributions, and rounding by at least EUR 1.00",
      "location": "/FatturaElettronicaBody[1]/DatiBeniServizi/DatiRiepilogo",
      "ruleset": "ITALY_FPR_FSM_B2B_DETERMINISTIC_1.9.1"
    }
  ],
  "findingsTruncated": false,
  "previewCounts": {
    "fatal": 0,
    "error": 0,
    "warning": 0,
    "information": 0
  },
  "previewFindings": [],
  "previewFindingsTruncated": false,
  "sha256": "1fa834287d8a921c4ba1d80aa75bed47a5638ee0d46ba949997e97e600668463",
  "embeddedXmlSha256": null,
  "container": null,
  "checkedAt": "2026-07-29T10:49:44.598107Z",
  "reports": {},
  "error": null
}
```

</details>

<details>
<summary><strong>03. NOT_EVALUATED</strong> - unsupported UBL syntax receives no decision</summary>

[`03_live_not_evaluated_output.json`](03_live_not_evaluated_output.json)

```json
{
  "inputIndex": 2,
  "documentId": "unsupported-ubl",
  "fileName": "unsupported-ubl.xml",
  "processingStatus": "FAILED",
  "conformanceStatus": "NOT_EVALUATED",
  "previewConformanceStatus": "NOT_EVALUATED",
  "validationScope": "OFFLINE_PREFLIGHT",
  "externalStateStatus": "NOT_EVALUATED_EXTERNAL_STATE",
  "rulesetEffectiveAt": "2026-05-15",
  "sourceFormat": "UNKNOWN",
  "validationFamily": "UNKNOWN",
  "syntax": "UNKNOWN",
  "profile": "UNKNOWN",
  "scenario": null,
  "versions": {
    "validationScope": "OFFLINE_PREFLIGHT",
    "schemaSource": "OPEN_SOURCE_DERIVED",
    "officialArtifactsBundled": false,
    "ordinarySchema": {
      "formats": [
        "FPA12",
        "FPR12"
      ],
      "version": "1.2.3",
      "sha256": "10709324b24a5b5ba284bbf595392286cc94446d8b69defb2afd3a4f24f8213a",
      "baselineProject": "phax/ph-fatturapa",
      "baselineVersion": "ph-fatturapa-3.1.0",
      "baselineCommit": "c5fc3a97208bf22e50949b09dd9bd396cb18cc9f",
      "baselineSha256": "f40dda07ffc5790b02bda5fdad39705226c0a2b5bc6d42a60abd65e8e381ea5d",
      "license": "Apache-2.0"
    },
    "simplifiedSchema": {
      "format": "FSM10",
      "version": "1.0.2",
      "sha256": "698d4960a5e6121764e06157aef2593be5ea06fd4ab0938d52185643fcba4c29",
      "baselineProject": "invopop/gobl.fatturapa",
      "baselineVersion": "v0.69.0",
      "baselineCommit": "23b1ae16f7e5a243fa11f77e937912d0814db9e9",
      "baselineSha256": "0ced96c0e61c66eb88bb93f6eed55acabd18d96004a61d5fbf3b2e01ef1fc40f",
      "license": "Apache-2.0"
    },
    "xmlDsigSchemaSha256": "35cf8197da812c85e40d57891b35c94187569ed474a2dac813ce5090dafcd35c",
    "b2gProfile": {
      "schema": "VFPA12 1.2.3 derived compatibility schema",
      "formatSpecification": "FatturaPA 1.4",
      "sdiSpecification": "SdI 1.8.4",
      "controlReference": "Elenco controlli 2.0"
    },
    "b2bProfile": {
      "schemas": "VFPR12 1.2.3 and VFSM10 1.0.2 derived compatibility schemas",
      "technicalReference": "AdE Allegato A 1.9.1",
      "effectiveAt": "2026-05-15"
    },
    "deterministicChecksRevision": "2026-07-29",
    "activeRuleset": {
      "name": "FatturaPA offline profiles current from 2026-05-15",
      "effectiveAt": "2026-05-15"
    },
    "artifactManifestSha256": "0ef44ac189d98b098a988fc9fa7bfc401f0463e7d7458bd9ba63d7c9f8572f3f"
  },
  "counts": {
    "fatal": 0,
    "error": 0,
    "warning": 0,
    "information": 0
  },
  "findings": [],
  "findingsTruncated": false,
  "previewCounts": {
    "fatal": 0,
    "error": 0,
    "warning": 0,
    "information": 0
  },
  "previewFindings": [],
  "previewFindingsTruncated": false,
  "sha256": null,
  "embeddedXmlSha256": null,
  "container": null,
  "checkedAt": "2026-07-29T10:49:44.666072Z",
  "reports": {},
  "error": {
    "code": "UNSUPPORTED_DOCUMENT",
    "message": "The XML root does not match a supported invoice syntax"
  }
}
```

</details>

## Integrate

Use the [live Apify Actor](https://apify.com/kamerozkan/italy-fatturapa-validator) from the Console, API, schedules, webhooks, Make, n8n, or an MCP-capable agent. Validate each returned row against [`dataset_record.schema.json`](dataset_record.schema.json).

## Scope and licensing

This independent sample repository is not affiliated with or endorsed by Agenzia delle Entrate, Sogei, or Sistema di Interscambio. The MIT License covers only this repository's original documentation, output samples, and JSON Schema. See [`DATA_NOTICE.md`](DATA_NOTICE.md) for the artifact and data boundary.

