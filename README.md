# From Hierarchical Silence to Democratic AI: The CITRUS Framework 

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/)

This repository contains the official implementation of the **CITRUS framework** and the resulting **HSDA Requirement Matrix** as presented in the paper: *"From Hierarchical Silence to Democratic AI: A Dual-Track Semantic Retrieval Protocol and Functional Design Matrix for Participative Conversational Agents."*

## 📌 Overview
Traditional Systematic Literature Reviews (SLRs) often fall into a **"Lexical Trap,"** where deterministic keyword searches fail to bridge the terminological silos between Management Science and Computer Science. 

**CITRUS** (Cluster-based Interactive Truncation for Retrieval Using Semantics) provides a high-recall, human-in-the-loop solution by augmenting the PRISMA flow with semantic vector-space discovery. In our study, this methodology achieved a **2033% Recall Gain** ($n=122$) over traditional lexical searches.

---

## 🛠 Search Strategy & Protocols (The Recipe)

To comply with **Scopus and ScienceDirect Terms of Use**, we do not redistribute the raw exploratory metadata ($n=27,326$). However, we provide the exact "recipe" below for full replication.

### Track 1: Lexical Precision Baseline

**Scopus Query:**

`TITLE-ABS-KEY ( ( "Generative AI" OR "GenAI" OR "Large Language Model*" OR "LLM*" OR "ChatGPT" OR "Foundation Model*" OR "chatbot*" OR "conversational agent*" OR "conversational AI" OR "virtual assistant*" OR "dialog* system*" OR "virtual agent*" OR "Agentic AI" OR "Autonomous Agent*" OR "Silicon Sampling" OR "Synthetic Social Agent*" OR "Synthetic Data" ) AND ( ( ( "participat*" OR "shared" OR "Employee Voice") AND ( "DSS" OR "Decision Support Syste*" OR "Decision Making" ) ) ) ) AND NOT TITLE-ABS-KEY ( patient* OR clinic* OR health* OR medic* OR "federated learning" ) AND ( LIMIT-TO ( OA , "all" ) ) AND ( LIMIT-TO ( DOCTYPE , "ar" ) ) AND ( LIMIT-TO ( LANGUAGE , "English" ))`

**ScienceDirect Query:**

`("Generative AI" OR "Conversational AI" OR "Chatbot") AND "Decision Making" AND (participative OR "Employee Voice") -patient -clinic -medical -hospital -travel -education -public -sector`

### Track 2: Semantic Discovery (High-Recall Pillars)

**Scopus C1 (GenAI + DSS):**

`TITLE-ABS-KEY ( ( "Generative AI" OR "GenAI" OR "Large Language Model*" OR "LLM*" OR "ChatGPT" OR "Foundation Model*" OR "chatbot*" OR "conversational agent*" OR "conversational AI" OR "virtual assistant*" OR "dialog* system*" OR "virtual agent*" OR "Agentic AI" OR "Autonomous Agent*" OR "Silicon Sampling" OR "Synthetic Social Agent*" OR "Synthetic Data" ) AND ( ( "DSS" OR "Decision Support Syste*" OR "Decision Making" ) ) ) AND ( LIMIT-TO ( OA , "all" ) ) AND ( LIMIT-TO ( DOCTYPE , "ar" ) ) AND ( LIMIT-TO ( LANGUAGE , "English" ) )`

**Scopus C2 (PDM + DSS):**

`TITLE-ABS-KEY ( ( ( "participat*" OR "shared" OR "employee voice" ) AND ( "DSS" OR "Decision Support Syste*" OR "Decision Making" ) ) ) AND NOT TITLE-ABS-KEY ( patient* OR clinic* OR health* OR medic* OR "federated learning" ) AND ( LIMIT-TO ( OA , "all" ) ) AND ( LIMIT-TO ( DOCTYPE , "ar" ) ) AND ( LIMIT-TO ( LANGUAGE , "English" ) ) AND PUBYEAR > 2022`

**ScienceDirect Queries (SD1-SD4):**
*   **SD1:** `("Generative AI" OR "Large Language Model" OR ChatGPT OR "Foundation Model") AND (participatory OR participative) AND ("Decision Making" OR DSS)`
*   **SD2:** `(chatbot OR "Agentic AI" OR "Autonomous Agent" OR "Silicon Sampling" OR "Synthetic Data") AND (participatory OR participative) AND ("Decision Making" OR DSS)`
*   **SD3:** `("Generative AI" OR chatbot OR "Agentic AI") AND "Employee Voice" AND ("Decision Making" OR DSS)`
*   **SD4:** `("Generative AI" OR chatbot OR LLM) AND "Shared Decision Making" AND ("Decision Making" OR DSS)`

---

## 🚀 Repository Contents & Code Usage

### 📁 Structure
*   `CITRUS_CAI_PDM.ipynb`: Main Google Colab notebook for embedding and expert calibration.
*   `hsda_df_final.csv`: The final synthesized 101 papers (The Requirement Matrix).
*   `cluster_orthogonality.csv`: Jaccard results proving thematic distinctness.

### 📝 Usage
1.  **Extract:** Use the strings above to export results from Scopus/ScienceDirect.
2.  **Embed:** Open the notebook, enter your Gemini API Key, and generate the `citrus_df`.
3.  **Negotiate:** Use the interactive Plotly UI to find the **"Semantic Knee"** and truncate your harvest.

## 📝 Citation
```bibtex
@article{suntoyo2026hsda,
  title={From Hierarchical Silence to Democratic AI: A Dual-Track Semantic Retrieval Protocol and Functional Design Matrix for Participative Conversational Agents},
  author={Suntoyo, Wisudanto C. and Sunitiyoso, Yos and Siallagan, Manahan and Hermawan, Pri},
  journal={Technology in Society},
  year={2026},
  publisher={Elsevier}
}
```