# The Liberatory Assistant: A De-Colonial Palestinian Navigator 🇵🇸

This repository contains the complete pipeline for fine-tuning a **Gemma-2b-it** model into a domain-specific assistant specialized in Palestinian history, international legal resistance (ICJ), and global solidarity frameworks (BDS).

## 1\. Project Manifesto: Why Palestine?

The selection of the Palestinian struggle for this project is rooted in the far-left principle of **Information as Liberation**. In a global landscape where narratives are often dominated by hegemonic corporate interests, the preservation and neural "calibration" of de-colonial information is a critical act of resistance.

We believe that:

- **Information is a Tool:** True liberation for all marginalized groups requires access to authentic, systemic analysis.
- **Counter-Hegemonic AI:** Large Language Models (LLMs) are often "colonized" by Western-centric training data. Fine-tuning is a technical reclamation, forcing the model to prioritize the material reality of the oppressed over the "passive neutrality" of the oppressor.
- **Neural Solidarity:** By embedding Palestinian narratives into a neural network, we create a tool that moves beyond dictionary definitions to provide structural critiques of occupation, apartheid, and the struggle for sovereignty.

## 2\. The Dataset: Palestine Dataset

The model is trained on a curated corpus focused on authentic Palestinian history, narratives, and reporting.

### Primary Data Sources

- **decolonizepalestine.com** - Educational content and historical documentation.
- **electronicintifada.net** - News and systemic analysis.
- **palianswers.com** - Rebuttals to Zionist claims.
- **mondoweiss.net** - On-the-ground reporting and legal critiques.
- **bdsmovement.net** - Boycott, Divestment, and Sanctions (BDS) movement frameworks.
- **stand-with-palestine.org** - Interviews and specialized articles.

### Purpose

This dataset aims to preserve and provide access to information about Palestine by collecting content from sources that represent Palestinian perspectives, ensuring that AI models can understand and articulate de-colonial material realities.

## 3\. Repository Workflow & Notebook Environments

This project uses a **Hybrid Infrastructure** to balance accessibility with high-performance computing requirements.

### 📓 Notebook 1: Data Engineering & Preprocessing

- **Filename:** Preprocessing_Pipeline.ipynb
- **Environment:** Google Colab (CPU/T4 GPU).
- **Role:** Transforms raw mlibre/palestine data into a structured Instruction-Response format.
- **Logic:** Cleans web-scraping noise, handles "Answer" formatting, and performs a **Context Window Audit** using the Gemma tokenizer to ensure all sequences are under 1024 tokens for VRAM efficiency.

### 📓 Notebook 2: Ideological Calibration (Fine-Tuning)

- **Filename:** Final_training_pipeline.ipynb
- **Environment:** **Modal Cloud (NVIDIA A10G GPU)**.
- **Role:** The core Supervised Fine-Tuning (SFT) phase.
- **Logic:** Implements **PEFT (LoRA)** with a Rank ($r$) of 32 and **4-bit NF4 Quantization**. This notebook triggers a remote cloud container, mounts a **Modal Volume** for persistent storage, and trains the model for 3 epochs.

### 📓 Notebook 3: Evaluative Praxis

- **Filename:** Evalution_script.ipynb
- **Environment:** Modal Cloud (A10G).
- **Role:** Quantitative and Qualitative auditing.
- **Logic:** Compares the "Base" Gemma model against the "Fine-Tuned" assistant. It calculates **Perplexity (PPL)** and **ROUGE-L** scores while documenting the model's ability to pivot from neutral definitions to structural analysis.

### 📓 Notebook 4: The Digital Press (User Interface)

- **Filename:** Interactive_Interface.ipynb
- **Environment:** Google Colab (CPU or T4 GPU).
- **Role:** Deployment of the **Gradio** web interface.
- **Logic:** Loads the saved adapters from the training phase. It uses a custom monochrome, constructivist theme and implements a **repetition penalty** to ensure high-quality dialectical responses.

## 4\. Setup & Execution Guide

### Step 1: Dataset Upload

1.  Download the raw dataset ZIP file.
2.  Upload the ZIP to the root directory of your Google Colab environment (/content).
3.  Run the **Preprocessing Pipeline** to extract and generate train_dataset.jsonl and test_dataset.jsonl.

### Step 2: Modal & Hugging Face Secrets

1.  Ensure your HF_TOKEN (with 'Read' access for Gemma) is saved in your Colab Secrets.
2.  In your Modal Dashboard, create a secret named huggingface-secret containing your HF_TOKEN.
3.  Initialize Modal in Colab using !modal setup.

### Step 3: Running the Pipeline

- **Training:** Execute the cells in Final_training_pipeline.ipynb. This will request the A10G GPU and save weights to revolutionary-model-storage.
- **Evaluation:** Run Evalution_script.ipynb to generate the comparative performance report.
- **Deployment:** Launch Interactive_Interface.ipynb and click the generated .gradio.live link to interact with the assistant.

## 5\. Performance Summary

- **Quantitative Gain:** Achieved a **69.5% reduction in Perplexity**, proving the model successfully internalized the specialized vocabulary.
- **Non-Destructive Training:** Qualitative testing confirms the model retains general world knowledge (e.g., cooking recipes) while applying an ideological filter to domain-relevant queries.
- **Neural Integrity:** Framing hallucinations as "Neural Interference" (clashes between base parameters and adapters) rather than simple errors.

## ⚖️ License

The code in this repository is provided under the **Unlicense**. Content from source websites remains under their respective original licenses.

**Contact:** [Hirwa Armstrong Brian](Armstronghirwa5@gmail.com)

