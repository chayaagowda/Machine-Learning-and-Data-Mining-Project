# Finish the submission

## Copy files into your project

Extract this package. Copy its contents into `/Users/mac/Desktop/FINAL PROJECT`, replacing the cleaned notebook and `.gitignore` when prompted. Keep your local dataset and environment. Do not replace your entire project folder with this smaller reviewed copy. No experiment rerun is required. The package retains `results_A.csv` and `split_seed42.npz` as explicitly labelled preliminary artifacts.

## Review the report

Open `Final_Report.docx` in Word. Add your actual name, teammate name if applicable, course number, and instructor details if required. Do not claim an unperformed teammate contribution. Check your instructor's rubric for page limits, citations, presentation requirements, accepted report format, and required submission files. The supplied proposal does not establish the current final-submission rubric. Export the report to PDF if required.

## Review and commit in Terminal

```bash
cd "/Users/mac/Desktop/FINAL PROJECT"
git status --short
git ls-files '*.joblib' creditcard.csv
```

If the second command prints any model or dataset paths, stop and share that output before staging: `.gitignore` does not untrack files already committed.

Otherwise, stage the reviewed artifacts explicitly:

```bash
git add -- .gitignore README.md Final_Report.docx CONSISTENCY_CHECK.md SUBMISSION_GUIDE.md All_experiments_cv_summary.csv Fraud_Setup_and_E1_Baseline.ipynb figures

git add -- '*.csv' '*.json' split_deduplicated_seed42.npz Person_A_split_and_folds_seed42.npz requirements.txt Credit_Card_Fraud_Project_Proposal.pdf

git diff --cached --check
git diff --cached --stat
git diff --cached --name-only
```

Review the staged list; it should contain no dataset, virtual environment, secrets, or large fitted model. Any unrelated changes previously staged also need review. If `git diff --cached --check` prints issues, resolve them before committing.

```bash
git commit -m "Complete fraud detection evaluation and final report"
git push
git status --short
```

If push fails, share the error; do not force-push. These commands must run on your Mac because the review archive contains no Git metadata or authenticated repository checkout. GitHub publication has not been performed by the assistant.

## Portal checklist

- Report has the correct author and course details and required format.
- Notebook opens with saved results and figures.
- Required results, thresholds, split archives, metadata, and environment file are included.
- Omitted repeated outer splits are stated explicitly.
- GitHub push succeeded; submit its link if required.
- Upload required files to the course portal and verify its confirmation.
- Prepare slides only if required by the rubric.
