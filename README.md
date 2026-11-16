cat > README.md <<'EOF'
# ICDFA-DFIR-AI-026
## AI-Assisted IP Evidence Identification and Model Evaluation

### Project overview
This project evaluates an offline workflow for extracting IP-like strings, validating IPv4 candidates, and classifying text using machine-learning models.

### Evidence and preservation
Original supplied materials are stored in `originals/`. Extracted working copies are stored in `working/`. The evidence manifest is available at `evidence_manifest.csv`.

Do not modify original evidence files. Refer to the manifest and recorded hashes when verifying evidence integrity.

### Project structure
- `originals/` – original supplied archive
- `working/` – extracted working material and datasets
- `logs/` – command output and validation records
- `scripts/` – analysis and processing scripts
- `notebooks/` – project notebooks
- `results/candidate_reviews/` – extracted candidate review
- `results/predictions/` – model predictions and analyst review sample
- `results/charts/` – evaluation and historical metric charts
- `reports/` – phase reports, intelligence memo, and executive brief
- `screenshots/` – assignment evidence screenshots

### Workflow summary
1. Preserve and document supplied evidence.
2. Inspect the supplied CSV and JSONL datasets.
3. Extract IP-like strings using a regular expression.
4. Validate IPv4 candidates using Python's `ipaddress` module.
5. Train and evaluate offline TF-IDF and classification pipelines.
6. Compare Logistic Regression and Linear SVM against a majority-class baseline.
7. Review historical fine-tuning metrics without treating them as independently reproduced results.
8. Evaluate model predictions and document limitations.
9. Prepare an intelligence memo and executive brief.

### Model evaluation
The Linear SVM achieved 93.48% accuracy on the supplied 46-record holdout set. It produced 9 true negatives, 3 false positives, 0 false negatives, and 34 true positives.

The result must be interpreted cautiously. Eleven of the 25 unique test prompts overlap with training prompts. The dataset is imbalanced, and its labels are not independently verified ground truth.

### Reproduction
Run the scripts from the project root and follow the phase reports for the relevant workflow and outputs. The offline model workflow uses TF-IDF and scikit-learn classifiers. The random seed used for model evaluation is 42.

### Safety and interpretation
This project is an educational forensic analysis. A syntactically valid IP address or a positive model prediction does not prove maliciousness, attribution, or intent. All candidates and predictions require contextual examination and independent corroboration.

Do not execute historical scripts that upload data or submit jobs to external services. No external upload is required for the offline workflow.
EOF

ls -lh README.md reports/phase_*.md
