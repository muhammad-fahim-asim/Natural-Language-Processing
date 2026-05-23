# Natural Language Processing for Legal Agreement Mining

## Project Overview

This repository contains a collection of NLP experiments and pipelines for extracting structured information from OCR-processed legal agreements. It focuses on:

- temporal information extraction using **HeidelTime** and optional **TreeTagger** POS tagging (Task 6)
- clause and obligation extraction for agreement renewal and evaluation provisions (Tasks 8 and 11)
- handling noisy OCR text and state-level document collections

## Key Components

- `tasks_6.ipynb`
  - A pipeline for temporal expression extraction from legal agreements
  - Uses **HeidelTime Standalone** and compares results with/without TreeTagger
  - Produces dataset-level timing, memory profiling, and validity outputs

- `tasks_8_11.ipynb`
  - A hybrid extraction pipeline for agreement renewal and evaluation obligations
  - Uses rule-based retrieval, context expansion, and neural verification with MNLI-style models
  - Saves structured outputs and evidence for downstream analysis

- `OCR_output/`
  - OCR-derived legal agreement text organized by US state
  - Includes `.txt` and `.json` inputs used by the notebooks

- `heideltime-standalone/`
  - Heidelberg Time standalone Java package and configuration files
  - Required for the temporal extraction pipeline in `tasks_6.ipynb`

- `TreeTagger/`
  - Optional POS tagger used by the Task 6 pipeline
  - Contains executables and model files for Windows

- `tables/`
  - Generated output tables, CSV results, and profiling summaries

## Usage

1. Open the notebook for the task you want to run:
   - `tasks_6.ipynb` for temporal extraction (Task 6)
   - `tasks_8_11.ipynb` for clause extraction (Tasks 8 and 11)

2. Configure required paths and dependencies inside the notebook.
   - Task 6 requires a Java runtime and the HeidelTime standalone JAR
   - Task 6 can optionally use TreeTagger for POS tagging
   - Task 8/11 requires Python NLP packages and transformer models

3. Run the notebook cells to process OCR data and generate structured outputs.

## Recommended Setup

- Python 3.8+ for notebook execution
- Java 17+ for `heideltime-standalone`
- Sufficient memory for model inference and dataset processing

