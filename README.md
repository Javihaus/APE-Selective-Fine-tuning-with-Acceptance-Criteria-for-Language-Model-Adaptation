# APE: A Data-Centric Benchmark for Efficient LLM Adaptation in Text Summarization

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![License](https://img.shields.io/badge/License-CC%20BY%204.0-green.svg)
![Hardware](https://img.shields.io/badge/Hardware-T4%20GPU-orange.svg)

This repository is the official implementation of "APE: A Data-Centric Benchmark for Efficient LLM Adaptation in Text Summarization," submitted to NeurIPS 2025. During the review process, this code is provided as supplementary material to maintain anonymity. Post-review, the public repository will be released.

> **Abstract:** APE leverages iterative data perturbations inspired by the "adjacent possible" theory to fine-tune T5-base for text summarization, achieving efficient adaptation with limited resources.  
> **BibTeX (Pending Acceptance):**
> ```
> @misc{anon2025ape,
>   title={APE: A Data-Centric Benchmark for Efficient LLM Adaptation in Text Summarization},
>   author={[Anonymous for Submission]},
>   year={2025},
>   note={Submitted to NeurIPS 2025},
> }
> ```

## Requirements
- Installation: To install requirements:

```bash
pip install -r requirements.txt
```
Alternatively, run the notebooks in Google Colab, which include a commented !pip install cell for convenience.

- Environment: Python 3.8+, Google Colab with T4 GPU (16 GB VRAM recommended).
- Dataset: CNN/DailyMail v3.0.0, automatically downloaded via the datasets library. Ensure a stable internet connection.
- Storage: Mount Google Drive in Colab with ~5 GB free space for outputs. Update BASE_DIR in notebooks if using a custom path.

### Training
To train the APE model(s) as described in the paper, use the provided Jupyter notebooks:

### Scaled-Down Experiment
- Command: Open notebooks/ape_scaled_down_experiment.ipynb in Colab and run all cells.
- Details: Fine-tunes T5-base on 1,200 CNN/DailyMail articles over 15 iterations (80 articles/batch).
- Hyperparameters: Fixed learning rate = 3e-6, epochs = 3, gradient accumulation steps = 4.
- Runtime: ~2-3 hours on T4 GPU.
  
### Full-Scale Experiment
- Command: Open notebooks/ape_full_scale_experiment.ipynb in Colab and run all cells.
- Details: Fine-tunes T5-base on 4,000 articles over 17 iterations (~235 articles/batch).
- Hyperparameters: Fixed learning rate = 3e-6, epochs = 3, gradient accumulation steps = 4.
- Runtime: ~4-5 hours on T4 GPU.

**Note**: No standalone train.py script is provided; training is embedded in the notebooks for reproducibility. See the “Perturbation” sections in each notebook for implementation details.

### Evaluation
To evaluate the trained models as reported in the paper:

**Scaled-Down Experiment**
- Command: Run notebooks/ape_scaled_down_experiment.ipynb in Colab.
- Output: Generates qualitative summaries for 100 test articles, saved as summaries_for_evaluation.txt for human evaluation (Section 5.2).

**Full-Scale Experiment**
- Command: Run notebooks/ape_full_scale_experiment.ipynb in Colab.
- Output: Computes BLEU, ROUGE-1, BERTScore, and perplexity on 300 test articles, with results saved in results_summary.pkl and plots in plots/.
- Metrics Reproduction: See the “Compute Metrics” section in the notebook for exact calculations.

**Note**: Evaluation is integrated into the notebooks. Results match Tables 3 and Figure 2 in the paper.

### Pre-trained Models
Pre-trained models are not hosted publicly during review to maintain anonymity. They are generated during notebook execution:

- Baseline Model: T5-base before perturbations, saved as models/baseline_model/ in Google Drive.
- Final Models:
    - Scaled-Down: After 15 iterations, saved as models/final_model/.
    - Full-Scale: After 17 iterations, saved as models/final_model/.
    - Training Details: Fine-tuned on CNN/DailyMail with fixed LR=3e-6, as described in Section 4.
    - Access: Run the notebooks to generate these models locally. Post-review, links to pre-trained models will be added here if accepted.

### Results
APE achieves the following performance on the CNN/DailyMail dataset:

**Text Summarization on CNN/DailyMail**
**Full-Scale Experiment (Quantitative Metrics)**
  Model	BLEU	ROUGE-1	BERTScore	Perplexity
  Baseline T5-base	0.062	0.290	0.343	13.0
  APE (17 iters)	0.083	0.329	0.398	8.3
**Scaled-Down Experiment (Human Evaluation)**
  Metric	Baseline	APE (15 iters)
  Informativeness	2.24	3.17
  Fluency	2.09	3.43
  Factual Accuracy	2.32	3.05
  Reproduction: Run ape_full_scale_experiment.ipynb to reproduce quantitative results (Figure 2) and ape_scaled_down_experiment.ipynb for   qualitative summaries (Table 3). See PapersWithCode for context.

### Contributing
This project is licensed under the . You are free to share and adapt the material for non-commercial purposes with appropriate credit.

To contribute:

Fork the repository post-review (once public).
Submit pull requests with bug fixes, enhancements, or additional experiments.
Contact the authors via the NeurIPS portal during review for suggestions.
Note: Contributions are welcome after the review process when the repository is made public. For now, please refrain from direct modifications to maintain anonymity.
