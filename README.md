# Financial Statement Analysis and LLM Evaluation Project

## Overview

This project presents a systematic evaluation of large language models (LLMs) on **financial statement understanding and extraction tasks**. The study focuses on assessing how well state-of-the-art open-source models can process, interpret, and structure financial information derived from real-world corporate disclosures.

All experiments are conducted using **financial data from a publicly listed Senegalese company (SONATEL Sénégal)** on the **Bourse Régionale des Valeurs Mobilières (BRVM)**. The project emphasizes **fair model comparison**, **reproducibility**, and **financial reasoning accuracy**.

---

## Project Objectives

The main goals of this project are:

- Evaluate the ability of large language models to extract and structure financial statements.
- Compare model performance across **balance sheet**, **income statement**, and **cash flow statement** tasks.
- Assess probabilistic behavior of language models via **probability distribution divergence analysis**.
- Provide a reproducible experimental framework using standardized prompts and evaluation settings.

---

## Models Evaluated

The following open-source models were evaluated:

| Model            | Parameters | Access Method     |
|------------------|------------|-------------------|
| GPT-OSS-120B     | 120B       | Groq API          |
| LLaMA 3          | 70B        | Groq API          |
| Gemma 3          | 27B        | Google Free API   |
| Mistral          | 7B         | Local / HuggingFace |

### Model Configuration

- **Temperature**: `1.0` (uniform across all models)
- **Hyperparameters**: Default settings for all models
- **Prompts**: One prompt per financial statement type to ensure fairness

---

## Dataset Description

### Source

- **Company**: SONATEL Sénégal
- **Market**: BRVM (Bourse Régionale des Valeurs Mobilières)
- **Document**: Official annual financial report (Exercise 2024)
- **Source URL**: https://www.brvm.org/fr/rapports-societes-cotees

### Financial Statements Used

- Balance Sheet
- Income Statement
- Cash Flow Statement

The statements were:
1. Extracted from the official PDF report  
2. Structured into tabular format  
3. Converted into textual representations for model inference  

> **Note**: In real-world applications, models would process full unstructured corporate reports. This study uses simplified textual inputs due to data availability constraints.

---

## Project Structure

```text
/Financial Statement
│   20250418_-_rapport_dactivites_annuel_-_exercice_2024_-_sonatel_sn.pdf
│   balance_sheet.txt
│   income_statement.txt
│   cash_flow_statement.txt
│
/Output
│   20250418_-_rapport_dactivites_annuel_-_exercice_2024_-_sonatel_sn.pdf
│   balance_sheet.txt
│   income_statement.txt
│   cash_flow_statement.txt
│
/Prompt
│   20250418_-_rapport_dactivites_annuel_-_exercice_2024_-_sonatel_sn.pdf
│   balance_sheet.txt
│   income_statement.txt
│   cash_flow_statement.txt
│
gemma3_27B_model_experiment.ipynb
gpt_oss120b_model_experiment.ipynb
llama3_70B_model_experiment.ipynb
probability_distribution_experiment.ipynb
