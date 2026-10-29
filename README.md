# Proposed Oracle FP&A and GenBI reference model

This repository contains one downloadable ZIP, organized by team role, with a proposed Oracle financial core, workbook-derived candidate policies, GenBI metadata contracts, graph/vector specifications, draft SQL and offline test evidence.

Download [Oracle_FPA_team_package_by_folder.zip](Oracle_FPA_team_package_by_folder.zip), extract it, and read START_HERE.md. SHA256SUMS records the archive checksum.

| Folder | Intended audience | Contents |
|---|---|---|
| 01_team_review | Finance, FP&A and stakeholders | Single guide, candidate policies, pending confirmations and final review |
| 02_engineering_implementation | Architects, Oracle DBAs and developers | Proposed model, dictionary, relationships, SQL, configuration and contracts |
| 03_validation_and_tests | QA, finance control and security reviewers | Frozen synthetic fixtures, expected results, test runners and observed evidence |
| 04_complete_reference | Model owners and data stewards | Complete technical files and extracted reference-workbook evidence |

## Current status

The selected core has 27 proposed tables and 233 documented columns. All company source mappings remain UNBOUND. Workbook candidate policies, proposed definitions and synthetic financial data remain separate. The original Excel workbook is not included, but extracted catalog evidence is included.

Observed offline results: 50 golden cases, seven metadata mutation checks, three additional controls, 90 contract checks, 12 final-review regressions and 13 source/prompt checks passed. These are finite offline checks, not a production accuracy guarantee or independent finance/security certification.

The wider enterprise specification is only partially implemented. Oracle DDL and queries remain DRAFT_UNEXECUTED. Exact installed Oracle release/edition, real-source reconciliation, native security validation and production approval remain pending. Read final_review.md in the archive for corrections and known gaps.

## Public copy

Two local computer path strings were removed from the inspection script and workbook metadata, and affected checksums were regenerated. This cleanup did not change the financial model, fixture calculations or test assertions. PUBLIC_COPY_NOTES.md in the archive records the changes.

## Reproduce the offline checks

Extract the archive and use a separate Python 3.12 or later environment. Install the requirements listed in the relevant folder. From 03_validation_and_tests run:

```text
python run_tests.py
python test_contracts.py
python test_final_review.py
```

Rechecking the source extraction requires the original prompt and Excel plus audit_source.py in 04_complete_reference. No script is authorized to deploy to a live Oracle database merely by being included here.
