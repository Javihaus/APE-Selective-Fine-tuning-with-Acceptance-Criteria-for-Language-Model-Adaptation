# Results Directory

This directory is a placeholder for experiment outputs, which are saved to Google Drive during notebook execution.

## Output Files

- **Scaled-Down Experiment:**
  - `models/baseline_model/`: Pre-trained T5-base before perturbations.
  - `models/final_model/`: T5-base after 15 iterations.
  - `qualitative_analysis/results.pkl`: Pickled qualitative results (article, reference, baseline, final summaries).
  - `summaries_for_evaluation.txt`: Text file for human evaluation.

- **Full-Scale Experiment:**
  - `models/baseline_model/`: Pre-trained T5-base before perturbations.
  - `models/final_model/`: T5-base after 17 iterations.
  - `results_summary.pkl`: Pickled dictionary of metric means and stds (BLEU, ROUGE-1, BERTScore, perplexity).
  - `plots/*.pdf`: Publication-quality plots for each metric.

## Access Instructions

- **Location:** `/content/drive/MyDrive/NeurIPS2025_Results` (default path in notebooks).
- **Storage:** Requires ~5 GB free space on Google Drive.
- **Links:** Outputs are not hosted here due to size. Run the notebooks to generate them locally, or contact the authors via the NeurIPS portal for sample results (anonymized for review).
