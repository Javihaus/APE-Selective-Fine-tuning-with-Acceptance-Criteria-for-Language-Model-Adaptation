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

```bash
pip install -r requirements.txt
