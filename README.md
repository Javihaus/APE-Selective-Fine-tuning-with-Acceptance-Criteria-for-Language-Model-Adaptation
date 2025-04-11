# APE: Adjacent Possible Exploration for LLM Adaptation

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![License](https://img.shields.io/badge/License-CC%20BY%204.0-green.svg)
![Hardware](https://img.shields.io/badge/Hardware-T4%20GPU-orange.svg)

## Overview

This repository contains the official implementation of **Adjacent Possible Exploration (APE)**, a data-centric methodology for efficiently adapting large language models (LLMs) to text summarization tasks, as presented in the NeurIPS 2025 submission:

**"APE: A Data-Centric Benchmark for Efficient LLM Adaptation in Text Summarization"**  
*Authors:* [Anonymous for Submission]  
*Submission Date:* April 10, 2025  

APE leverages iterative data perturbations inspired by Stuart Kauffman’s "adjacent possible" theory to fine-tune LLMs (T5-base) with minimal computational resources. This repository includes two experiments:
- **Scaled-Down Experiment:** Fine-tunes on 1,200 CNN/DailyMail articles over 15 iterations, focusing on qualitative analysis.
- **Full-Scale Experiment:** Fine-tunes on 4,000 articles over 17 iterations, providing quantitative metrics (BLEU, ROUGE-1, BERTScore, perplexity).

## Repository Structure

- **`notebooks/`**: Jupyter notebooks for both experiments.
  - `ape_scaled_down_experiment.ipynb`: Scaled-down setup with qualitative outputs.
  - `ape_full_scale_experiment.ipynb`: Full-scale setup with quantitative results and plots.
- **`data/`**: Placeholder for dataset access instructions (CNN/DailyMail hosted externally).
- **`results/`**: Placeholder for output files (models, summaries, plots) stored on Google Drive.
- **`requirements.txt`**: List of Python dependencies.
- **`LICENSE`**: Creative Commons Attribution 4.0 License.
- **`.gitignore`**: Excludes unnecessary files (e.g., checkpoints, logs).

## Prerequisites

- **Hardware:** Google Colab with T4 GPU (16 GB VRAM, 7.5 TFLOPS recommended).
- **Software:** Python 3.8+, Google Colab environment.
- **Dependencies:** See `requirements.txt` for full list.

## Setup Instructions

### Install Dependencies

pip install -r requirements.txt

### Alternative Installation
Alternatively, run the notebooks in Google Colab, which includes a commented !pip install cell for dependency installation directly within the notebook environment.

### Access Data
The CNN/DailyMail dataset (v3.0.0) is loaded via the datasets library. See data/README.md for details. Ensure a stable internet connection for dataset download.

### Google Drive Setup
Mount your Google Drive in Colab to save outputs (requires ~5 GB free space). Update BASE_DIR in the notebooks if using a different path.

### Running the Experiments
**Scaled-Down Experiment**
- **Notebook**: notebooks/ape_scaled_down_experiment.ipynb
- **Purpose**: Fine-tune T5-base on 1,200 articles, generate qualitative summaries for 100 test articles.
- **Runtime**: ~2-3 hours on T4 GPU.
- **Outputs**: Baseline/final models, qualitative results (results.pkl), human evaluation text file.
**Run in Colab**
- Upload the notebook to Colab.
- Execute all cells sequentially.
- Results are saved to /content/drive/MyDrive/NeurIPS2025_Results.

**Full-Scale Experiment**
- **Notebook**: notebooks/ape_full_scale_experiment.ipynb
- **Purpose**: Fine-tune T5-base on 4,000 articles, compute quantitative metrics, and plot results.
- **Runtime**: ~4-5 hours on T4 GPU.
- **Outputs**: Baseline/final models, metric history (results_summary.pkl), plots (PDFs).
**Run in Colab**
- Upload the notebook to Colab.
- Execute all cells sequentially.
- Results are saved to /content/drive/MyDrive/NeurIPS2025_Results.

### Results
- **Scaled-Down**: Qualitative summaries for human evaluation (see paper Section 5.2).
- **Full-Scale**: Quantitative improvements (e.g., 33.9% BLEU increase) and plots (see paper Figure 2).
Outputs are stored in Google Drive as linked in the notebooks. See results/README.md for access instructions.

### Reproducibility
Random seeds are set (np.random.seed(42), torch.manual_seed(42)) for consistent results.
Environment checks ensure compatibility (Python 3.8+, T4 GPU, package versions).

Note: All code is self-contained within the notebooks, with external data accessed via datasets.


### Citation
Pending acceptance at NeurIPS 2025. For now, please cite as:

[Anonymous Authors]. (2025). "APE: A Data-Centric Benchmark for Efficient LLM Adaptation in Text Summarization." Submitted to NeurIPS 2025.

### Contact
For inquiries, please use the NeurIPS submission portal (anonymized for review).
