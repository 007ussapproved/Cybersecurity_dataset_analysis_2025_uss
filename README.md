# Cybersecurity_dataset_analysis_2025_uss

Scripts, prompts, and analysis pipeline for our Systematization of Knowledge (SoK) paper on cybersecurity research domains and dataset usage trends (2015–2024) using large language models (LLMs).

---

##  Repository Structure

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

### `results/`
- **`raw/`** – Raw outputs from prompting (JSONL and CSV formats).  
- **`analysis/`** – Cleaned CSVs containing processed dataset trends, metadata, and results.  

---

##  Setup

### Option A — Conda
```bash
conda env create -f environment.yml
conda activate cyber-sok
jupyter lab
