# Cybersecurity_dataset_analysis_2025_uss

Scripts, prompts, and analysis pipeline for our Systematization of Knowledge (SoK) paper on cybersecurity research domains and dataset usage trends (2015–2024) using large language models (LLMs).

---

## Quick Start

### 1) Clone the repository
```bash
git clone <this-repository-url>
cd Cybersecurity_dataset_analysis_2025_uss
```

### 2) Set up Python environment
```bash
python -m venv .venv
# Windows:
.venv\Scripts\activate
# macOS/Linux:
source .venv/bin/activate

pip install --upgrade pip
pip install -r requirements.txt
```

### 3) Launch JupyterLab or VS Code
```bash
jupyter lab
```

---

## Repository Structure

### `scripts/`
- **`dataset_llm_final_uss.ipynb`** – Main prompting workflow for metadata extraction. Includes runner and saving scripts, cleaning raw outputs into separate files, and domain analysis.  
- **`dataset_summary_and_unique_datasets.ipynb`** – Extracts paper–dataset instances categorized into *Created by Authors (CA)* and *Used by Authors (UA)*. Also performs unique dataset analysis and category-wise analysis.  
- **`CUSTOM_CREATED_DATASET_DEEP_ANALYSIS.ipynb`** – Focused analysis of *custom-created datasets* only.  
- **`dataset_llm-test.ipynb`** – Test run with 101 papers.  
- **`dataset_llm-test-subset_20.ipynb`** – Test run with 22 papers.  

### `txt/`
Prompt files (all versions):
- `ver1_prompt.txt`  
- `ver2_prompt.txt`  
- `ver3_prompt.txt`

### Manual validation files (`.xlsx`)
- `keyword_validation.xlsx`  
- `human_validation_101.xlsx` *(101 papers)*

### `results/`
- **`analysis_results/raw_counts_custom_created`** – Raw outputs from prompting, custom-created datasets.  
- **`analysis_results`** – Cleaned CSVs and containing processed dataset and domain trends, and results.  

---

## How to Run

1) **Full prompting & metadata extraction**: open `scripts/dataset_llm_final_uss.ipynb`  
2) **UA/CA + paper–dataset + unique datasets**: open `scripts/dataset_summary_and_unique_datasets.ipynb`  
3) **Custom dataset analysis**: open `scripts/CUSTOM_CREATED_DATASET_DEEP_ANALYSIS.ipynb`  
4) **Test runs**: open `scripts/dataset_llm-test.ipynb` (101 papers) and `scripts/dataset_llm-test-subset_20.ipynb` (22 papers)

---

## Validation

- **Scope:** Manual validation of subsets (101-paper and 22-paper sets) against model-extracted results.  
- **Metrics:** Accuracy (AC), Precision (PR), Recall (RC), F1.  
- **Artifacts:** Per-paper comparisons and summary tables saved to `results/analysis/` as CSV and Excel (`.xlsx`), e.g., `validation_summary.xlsx`, `per_paper_validation.xlsx`.  
- **Reproduce:** Run the test notebooks listed above and compare with provided `.xlsx` files.

---

## Dependencies

Install with:
```bash
pip install -r requirements.txt
```

**requirements.txt**
```txt
openai>=1.0.0
python-dotenv>=1.0.1
PyPDF2>=3.0.1
chardet>=5.2.0
matplotlib>=3.8.0
jupyterlab>=4.2.0
ipykernel>=6.29.0
```

---

## Tips

- If Jupyter isn’t found, install it in your venv:
  ```bash
  pip install jupyterlab ipykernel
  ```

