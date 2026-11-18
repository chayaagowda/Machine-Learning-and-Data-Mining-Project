# Credit Card Fraud Detection

Comparison of resampling, class weighting, and ensembles under extreme class imbalance. E1–E6, tuning, SMOTE, feature selection, threshold selection, stability checks, and final evaluation are complete.

## Main finding

The primary model is **RandomForestClassifier(class_weight="balanced", n_estimators=100, random_state=42)**. This differs from the BalancedRandomForestClassifier tested in E5. On 56,746 holdout transactions including 95 frauds, AP was 0.8012. At the training-selected threshold 0.23, TP=76, FP=11, FN=19, TN=56,640; precision=0.8736 and recall=0.8000. Assumed cost 10×FN+FP was 201. The comparison model is seven-neighbor KNN with ten features selected inside its pipeline; AP=0.7850.

## Review existing results

Open `Fraud_Setup_and_E1_Baseline.ipynb` in VS Code. Saved outputs are included; rerunning is unnecessary to review them. Read `Final_Report.docx` and `CONSISTENCY_CHECK.md`. Full mean/std development comparisons are in `All_experiments_cv_summary.csv`.

## Data and preprocessing

Place the original ULB/Kaggle `creditcard.csv` in this folder. Dataset: https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud. The data is excluded from Git. Exact duplicate removal reduces 284,807 rows to 283,726, including 473 frauds. Scale Time and Amount within applicable training-fold pipelines; bin inputs for categorical Naive Bayes. Resample only within training folds.

## Files

| File or pattern | Purpose |
|---|---|
| `Fraud_Setup_and_E1_Baseline.ipynb` | Completed code and saved outputs |
| `Final_Report.docx` | Methods, findings, figures, and limitations |
| `E1*` through `E6*`, `KNN_cv*` | Original fold-level and summary experiments |
| `Person_A_*tuning*` | Parameter-search results |
| `Person_A_KNN_feature_selection*` | Ten-, twenty-, and thirty-feature KNN comparisons |
| `Person_A_SMOTE*` | Logistic regression with SMOTE |
| `Person_A_setup_metadata.json` | Dataset fingerprint and recorded environment |
| `Person_A_split_and_folds_seed42.npz` | Cleaned-data split and five CV folds |
| `split_deduplicated_seed42.npz` | Same cleaned train/test positions |
| `Finalists_oof*`, `Finalists_threshold*` | Training predictions, selected thresholds, and comparisons |
| `Finalists_stability*` | Additional-fold-seed checks within the original training partition |
| `Finalists_holdout*` | Reserved holdout metrics and probabilities |
| `Finalists_time_ordered_results.csv` | Retrospective chronological sensitivity check |
| `figures/` | Final PR curves and confusion matrices |
| `results_A.csv`, `split_seed42.npz` | Preliminary pre-deduplication artifacts; excluded from final comparisons |
| `SUBMISSION_GUIDE.md` | Local installation of this package and GitHub commands |

## Reproduce experiments only if needed

Run from this project directory. The recorded environment used Python 3.13.5; see the metadata and requirements for exact package versions. Existing-environment use is preferable to changing packages while preparing submission.

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
```

Select this virtual environment as the notebook kernel. Set `DATA_PATH` to your dataset and update the later `project = Path("/Users/mac/Desktop/FINAL PROJECT")` assignment if the folder differs. Preserve the cleaned split and metadata files. Run cells in order only when intentionally reproducing: they train models, can take hours, and overwrite saved artifacts. Reproduction was not executed during editorial cleanup. Data hashing depends on pandas representation and may fail under a different environment; do not bypass a mismatch without verifying dataset and versions.

## Evaluation scope

Selection and tuning used training folds. Only the two finalists received the cleaned-data holdout evaluation at default and training-selected thresholds. AP is scikit-learn average precision, not trapezoidal PR area. The 10:1 cost is illustrative. Additional seeds repeat CV within one training partition; the proposal's repeated 80/20 splits with retuning were omitted. The chronological check is retrospective, not independent prospective validation. See the report for limitations.
