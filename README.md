# Proposed Oracle FP&A and GenBI reference model

Correction release: reference-2026-11-01-02. Internal contract version: 2. Delivery consistency revision: 2. Proposed, not production approved.

Download [the organized ZIP](Oracle_FPA_team_package_by_folder.zip), extract it and read START_HERE.md. SHA256SUMS records its checksum. RELEASE_NOTES.md inside the ZIP explains the audit corrections and breaking schema changes.

| Folder | Audience | Contents |
|---|---|---|
| 01_team_review | Finance, FP&A, leadership | Updated four-slide presentation, guide, policies and pending confirmations |
| 02_engineering_implementation | Architects, Oracle and GenBI engineers | Corrected schema/SQL, contracts, generators and offline candidate admission |
| 03_validation_and_tests | QA, finance control, security | Synthetic fixtures, executable tests and observed results |
| 04_complete_reference | Model owners and stewards | Full technical snapshot and extracted workbook evidence |

The presentation is `01_team_review/Oracle_FPA_GenBI_leadership_brief.pptx`. It retains four slides, including the simplified confirmation table on slide 3.

## Delivery consistency revision

Generated requirement notes now use current model counts. The remaining-work register distinguishes supported offline admission from unfinished loader/native publication integration. Slide 4 explicitly labels the GenBI architecture as proposed. Run test_delivery_consistency.py from 04_complete_reference; add --archive pointing to the downloaded ZIP to check every inventory entry, duplicate folder file, one-line index, guide and PPT claim. Historical reviews retain their original counts under explicit historical notices.

## Corrections and scope

The current core has **29 tables, 248 columns and 15 proposed metrics**. Corrections address release-aware history/relationships, native report-line plans, ledger coverage, supported offline admission, finite/range/precision checks, replay, transitive metric certification and allocation receivers. The graph has 35 proposed nodes and 21 dependency edges. Vector work remains metadata/corpus specifications, with no embeddings or live index.

Version 2 changes composite keys. Do not run it over existing populated objects without an approved migration. Company source mappings remain UNBOUND, workbook policies remain candidates, and no company metric is certified. The wider enterprise application, source-specific loaders and native security remain incomplete. Oracle scripts remain DRAFT_UNEXECUTED.

## Reproduce the bounded offline evidence

Use Python 3.12+ with requirements.txt in a separate environment. From 03_validation_and_tests:

```text
python run_tests.py
python test_contracts.py
python test_final_review.py
python test_correction_release.py
python publication_validation.py --input publication_fixture.json
```

Observed results: 50 golden cases, 7 metadata mutations, 3 additional controls, 96 contract checks, 12 prior regressions, 25 correction regressions and 13 source/prompt checks passed. The correction suite's SQLite projections test portable relational behavior only, not Oracle execution. The validator returns candidate evidence and never publishes data or production approval. Some admission domains explicitly remain unsupported.

Repeating the workbook/prompt check requires the original files and audit_source.py in the complete reference. The 60 additional question templates remain unexecuted. Native Oracle/driver/security/performance testing, actual-source reconciliation and independent finance/security/operations acceptance remain pending.

The original workbook is unchanged and not included. Extracted candidate evidence is included. Public-copy cleanup removes two local computer paths and updates manifests. The pre-correction audit and previous review are clearly labeled historical inside the full reference. No script is authorization to deploy to a live database.
