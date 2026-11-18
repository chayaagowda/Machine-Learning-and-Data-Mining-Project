# Saved artifact consistency check

Verified without training models.

- PASS: E1_cv_folds_deduplicated_seed42.csv: 20 rows and no missing metrics
- PASS: E2_cv_folds_deduplicated_seed42.csv: 30 rows and no missing metrics
- PASS: E3_cv_folds_deduplicated_seed42.csv: 15 rows and no missing metrics
- PASS: KNN_cv_folds_deduplicated_seed42.csv: 20 rows and no missing metrics
- PASS: E4_cv_folds_seed42.csv: 20 rows and no missing metrics
- PASS: E5_cv_folds_seed42.csv: 15 rows and no missing metrics
- PASS: E6_cv_folds_seed42.csv: 5 rows and no missing metrics
- PASS: Person_A_SMOTE_cv_folds_seed42.csv: 5 rows and no missing metrics
- PASS: Holdout predictions: 56,746 rows and 95 frauds
- PASS: Random forest balanced default: confusion counts match saved predictions
- PASS: Random forest balanced default: accuracy matches
- PASS: Random forest balanced default: precision matches
- PASS: Random forest balanced default: recall matches
- PASS: Random forest balanced default: f1 matches
- PASS: Random forest balanced default: f2 matches
- PASS: Random forest balanced default: average_precision matches
- PASS: Random forest balanced default: roc_auc matches
- PASS: Random forest balanced default: cost_10to1 matches
- PASS: Random forest balanced cost_selected: confusion counts match saved predictions
- PASS: Random forest balanced cost_selected: accuracy matches
- PASS: Random forest balanced cost_selected: precision matches
- PASS: Random forest balanced cost_selected: recall matches
- PASS: Random forest balanced cost_selected: f1 matches
- PASS: Random forest balanced cost_selected: f2 matches
- PASS: Random forest balanced cost_selected: average_precision matches
- PASS: Random forest balanced cost_selected: roc_auc matches
- PASS: Random forest balanced cost_selected: cost_10to1 matches
- PASS: Random forest balanced: locked JSON threshold matches
- PASS: KNN top 10 default: confusion counts match saved predictions
- PASS: KNN top 10 default: accuracy matches
- PASS: KNN top 10 default: precision matches
- PASS: KNN top 10 default: recall matches
- PASS: KNN top 10 default: f1 matches
- PASS: KNN top 10 default: f2 matches
- PASS: KNN top 10 default: average_precision matches
- PASS: KNN top 10 default: roc_auc matches
- PASS: KNN top 10 default: cost_10to1 matches
- PASS: KNN top 10 cost_selected: confusion counts match saved predictions
- PASS: KNN top 10 cost_selected: accuracy matches
- PASS: KNN top 10 cost_selected: precision matches
- PASS: KNN top 10 cost_selected: recall matches
- PASS: KNN top 10 cost_selected: f1 matches
- PASS: KNN top 10 cost_selected: f2 matches
- PASS: KNN top 10 cost_selected: average_precision matches
- PASS: KNN top 10 cost_selected: roc_auc matches
- PASS: KNN top 10 cost_selected: cost_10to1 matches
- PASS: KNN top 10: locked JSON threshold matches
- PASS: Both cleaned split archives use identical train and test positions
- PASS: Cleaned train and test positions do not overlap
- PASS: Fold 1: fit and validation positions do not overlap
- PASS: Fold 2: fit and validation positions do not overlap
- PASS: Fold 3: fit and validation positions do not overlap
- PASS: Fold 4: fit and validation positions do not overlap
- PASS: Fold 5: fit and validation positions do not overlap
- PASS: Notebook has one E5 ensemble code cell
- PASS: Obsolete feature-selection code cell removed
- PASS: Stability results contain 20 rows

## Boundaries

The source dataset and large fitted model were intentionally excluded from the review archive. Dataset fingerprint recomputation and a complete fresh-kernel training run were not performed. CSV consistency does not establish statistical significance. Final figures are the supplied saved figures; their labels and counts were visually reviewed. The current course rubric, author names, submission portal requirements, and live GitHub state require your review.
