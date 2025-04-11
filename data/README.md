# Data Directory

This directory is a placeholder for dataset information. The experiments use the **CNN/DailyMail dataset (v3.0.0)**, accessed via the `datasets` library in the notebooks.

## Accessing the Dataset

- **Source:** Hugging Face Datasets (`cnn_dailymail`, version `3.0.0`).
- **Loading:** Automatically downloaded when running the notebooks with `load_dataset("cnn_dailymail", "3.0.0")`.
- **Requirements:** Stable internet connection and ~1 GB temporary storage.

## Dataset Details

- **Scaled-Down Experiment:** 1,200 training articles, 300 test articles.
- **Full-Scale Experiment:** 4,000 training articles, 300 test articles.
- **License:** CNN/DailyMail dataset is publicly available; refer to Hugging Face for usage terms.

No local data files are included here due to size constraints. Ensure connectivity to Hugging Face during execution.
