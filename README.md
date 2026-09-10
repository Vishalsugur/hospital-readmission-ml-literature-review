# hospital-readmission-ml-literature-review
AI-assisted literature review pipeline using EndNote and Claude for structured data extraction and validation
# AI-Assisted Literature Review: Machine Learning Models for Predicting Hospital Readmission Risk

**Author:** Vishal Sugur
**Date:** September 2026
**Tools used:** EndNote (reference management), PubMed (literature search), Claude (AI-assisted structured extraction)

## Objective

To build a small, structured literature review pipeline that combines academic citation management with AI-assisted document analysis — including validating AI outputs against source material and documenting errors — as a practical skill-building exercise for roles involving clinical/scientific data curation.

## Method

1. **Literature search:** Searched PubMed for "machine learning models predicting hospital readmission risk," selecting 8 relevant results published 2022–2026.
2. **Reference management:** Exported citations from PubMed in NBIB format and imported into EndNote. Organized into a dedicated group ("Hospital Readmission ML"). Generated a formatted APA bibliography via EndNote's Copy Formatted Citation function.
3. **AI-assisted extraction:** Used Claude to extract structured fields (study type, sample size, data/features, methods compared, best-performing model, key quantitative outcome, and conclusion) from each abstract.
4. **Validation / error-check:** Manually reviewed each AI-generated extraction against the source abstract to confirm accuracy and identify anomalies, inconsistencies, or misleading simplifications.

## Extraction Table

| Study | Type | N | Best Model | Key Metric |
|---|---|---|---|---|
| Afrash et al. (2022) | Retrospective cohort (COVID-19) | 5,791 | XGBoost | Accuracy 91.7%, AUC 0.91 |
| Davis et al. (2022) | Retrospective population-level cohort | 428,669 | Gradient Boosting (manual + ML features) | AUC 0.83 vs. LACE baseline 0.66 |
| Halac et al. (2025) | Retrospective cohort, single-center | 3,388 | Random Forest | C-statistic 0.64 |
| Oh et al. (2025) | Retrospective, single-center (EMR + nursing data) | 12,977 | Random Forest / CatBoost | AUROC 0.62–0.64 |
| Sharda et al. (2025) | Systematic review (PRISMA) | 9 studies reviewed | ANN / Random Forest (best across reviewed studies) | N/A — review-level synthesis |
| Silva et al. (2024) | Retrospective cohort, pediatric | 9,080 | XGBoost (bagging imputation) | AUC 0.814, J-index 0.484 |
| Zhang (2026) | Retrospective cohort (clinical + SDOH data) | 3,018 | XGBoost | ROC-AUC 0.79, PR-AUC 0.71 |

## Data Quality / Anomaly Findings

During this process, three issues were identified and documented — the core "test and validate AI-supported analysis, document anomalies and sources of error" skill this exercise was designed to practice:

1. **Duplicate reference:** The Afrash et al. (2022) paper was imported into EndNote twice under separate record numbers (#1 and #11), traced to overlapping PubMed export and EndNote search results. Resolved using EndNote's Find Duplicates tool before analysis — a reminder that reference deduplication is a necessary QA step before any downstream analysis, not an optional one.

2. **Study-type heterogeneity risk:** Sharda et al. (2025) is a systematic review of 9 prior studies, not a primary study with its own patient cohort. An AI extraction run without this distinction being checked could incorrectly report a "sample size" or include it in pooled statistics alongside primary studies, materially skewing any aggregate analysis (e.g., average N, average AUC).

3. **Performance metrics are not directly comparable across studies:** AUC/AUROC/C-statistic values ranged from ~0.60 (Halac, Oh — models built mainly
