# Cybersecurity_dataset_analysis_2025_uss

Prompts, runner(processing) script, and analysis pipeline for our Systematization of Knowledge (SoK) paper on cybersecurity research domains and dataset usage trends (2015–2024) using large language models (LLMs).

---

# Cybersecurity Paper Extractor & Analyzer

This repository contains scripts to:
1) **Extract** text and titles from PDFs into a JSONL corpus  
2) **Run LLM tasks** (title, authors, conference, year, schools, ACM-CCS domain, dataset name, dataset analysis, and dataset categories) over each paper  
3) **Incrementally save & resume** results  
4) **Aggregate and analyze** results (CSVs/plots)

> Works best with Python 3.10+.

---
## What’s Included

- **PDF Extraction**: Read PDFs from a folder, extract full text and a best-effort title, save as JSONL.
- **LLM Pipeline**: Prompted tasks for metadata and dataset analysis using OpenAI.
- **Incremental Runner**: Skip already-processed papers and keep appending results to a JSONL.
- **Analysis Utilities**: Quick scripts to compute dataset-related counts by year and per conference, with simple matplotlib charts.

### 1) Set up Python environment
**Create & activate a virtualenv**
```bash
python -m venv .venv
# Windows
.venv\Scripts\activate
# macOS/Linux
source .venv/bin/activate
```
2) **Install dependencies**
Install with:
```bash
pip install -r requirements.txt
```


## Repository Structure

### `script/`
- **`dataset_llm_final_uss.ipynb`** – Main prompting workflow for metadata extraction. Includes runner and saving scripts, cleaning raw outputs into separate files, and domain analysis.  
- **`dataset_summary_and_unique_datasets.ipynb`** – Extracts paper–dataset instances categorized into *Created by Authors (CA)* and *Used by Authors (UA)*. Also performs unique dataset analysis and category-wise analysis.  
- **`CUSTOM_CREATED_DATASET_DEEP_ANALYSIS.ipynb`** – Focused analysis of *custom-created datasets* only.  
- **`dataset_llm-test.ipynb`** – Test run with 101 papers.  
- **`dataset_llm-test-subset_20.ipynb`** – Test run with 22 papers(subset2).  

### `txt/`
Prompt files (all versions):
- `ver1_prompt.txt`  
- `ver2_prompt.txt`  
- `ver3_prompt.txt`

### `validation/`
- `keyword_validation.xlsx`  
- `human_validation_101.xlsx` *(101 papers)*
- `custom_created_manual_verification_author_ab.xlsx`
- `subset_manual_validation.xlsx` *(22 papers)*
- 
### `results/`
- **`results/`** - Cleaned CSVs and containing processed dataset and domain trends, and results. Raw Output file in JSON and CSV(results_merged_full_final.csv and results_merged_full_final.jsonl)
- **`results/raw_counts_custom_created`** – custom-created datasets tasks.
- **`results/unique_datasets_updated_new_last_final.csv`** - deduplicate list of datasets (master catalogue).
- **`results/datasets_summary_updated_final_new.csv`** - paperxdataset instances (2280)
---

## How to Run

1) **Full prompting & metadata extraction**: open `script/dataset_llm_final_uss.ipynb`  
2) **UA/CA + paper–dataset + unique datasets**: open `script/dataset_summary_and_unique_datasets.ipynb`  
3) **Custom dataset analysis**: open `script/CUSTOM_CREATED_DATASET_DEEP_ANALYSIS.ipynb`  
4) **Test runs**: open `script/dataset_llm-test.ipynb` (101 papers) and `scripts/dataset_llm-test-subset_20.ipynb` (22 papers)

---

## Tips

- If Jupyter isn’t found, install it in your venv:
  ```bash
  pip install jupyterlab ipykernel
  ```

