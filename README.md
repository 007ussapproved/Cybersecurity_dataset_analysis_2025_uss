# Cybersecurity_dataset_analysis_2025_uss
Scripts, prompts, and analysis pipeline for our Systematization of Knowledge (SoK) paper on cybersecurity research domains and dataset usage trends (2015–2024) using large language models (LLMs).
Repository Structure

## scripts

main_prompting.py – [to be described: main prompting workflow for metadata extraction]
runner.py – [to be described: includes paper–dataset instances extraction and unique dataset analysis]
ua_ca_custom.py – [to be described: UA (used by authors) and CA (created by authors) analysis, plus custom-created dataset study]

##/results

### raw/ – Raw outputs from prompting (JSONL and CSV formats)
### analysis/ – Cleaned CSVs containing processed dataset trends, metadata, and results

## /data

## Dependencies



## Usage
### Run Prompting
python scripts/main_prompting.py

### Run Paper–Dataset and Unique Dataset Extraction
python scripts/runner.py

### Run UA/CA and Custom Dataset Analysis
python scripts/ua_ca_custom.py

## Data and Results

1). Raw outputs are stored in /results/raw/ in both JSONL and CSV formats.
2). Processed analysis files are stored in /results/analysis/ in CSV format.
3). Outputs include paper–dataset instances, unique datasets, UA/CA breakdowns, and details of custom-created datasets.
