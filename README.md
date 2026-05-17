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

### Track 1: Deterministic Lexical Baseline (Precision-Oriented)

Track 1 establishes the precision baseline using high-fidelity Boolean strings to identify records that explicitly name the intersection of Conversational AI (CAI) and Participative Decision-Making (PDM). This track yielded **n=6 papers** as a high-fidelity anchor.

**Scopus Baseline Query (LEX1):**

```
TITLE-ABS-KEY ( ( "Generative AI" OR "GenAI" OR "Large Language Model*" OR "LLM*" OR "ChatGPT" OR "Foundation Model*" OR "chatbot*" OR "conversational agent*" OR "conversational AI" OR "virtual assistant*" OR "dialog* system*" OR "virtual agent*" OR "Agentic AI" OR "Autonomous Agent*" OR "Silicon Sampling" OR "Synthetic Social Agent*" OR "Synthetic Data" ) AND ( ( ( "participat*" OR "shared" OR "Employee Voice" ) AND ( "DSS" OR "Decision Support Syste*" OR "Decision Making" ) ) ) ) AND NOT TITLE-ABS-KEY ( patient* OR clinic* OR health* OR medic* OR edu* OR "public sector" OR travel ) AND ( LIMIT-TO ( DOCTYPE , "ar" ) )
```

**ScienceDirect Baseline Query (LEX2):**

```
("Generative AI" OR "Conversational AI" OR "Chatbot") AND "Decision Making" AND ("Participative" OR "Employee Voice") -patient -clinic -medical -hospital -travel -education -public -sector
```

### Track 2: Negotiated Semantic Discovery (Recall-Oriented)

Track 2 acknowledges that relevant CAI-PDM interactions are often described using non-overlapping terminology. This track extracted a broad corpus of **n=27,326 unique records** from Scopus and ScienceDirect.

**Scopus High-Recall Pillars:**

*   **C1 (PDM + DSS):**
    ```
    TITLE-ABS-KEY ( ( "participat*" OR "shared" OR "employee voice" ) AND ( "DSS" OR "Decision Support Syste*" OR "Decision Making" ) ) AND NOT TITLE-ABS-KEY ( patient* OR clinic* OR health* OR medic* OR "public sector" ) AND ( LIMIT-TO ( DOCTYPE , "ar" ) )
    ```

*   **C2 (PDM + DSS - Duplicate for verification):**
    ```
    TITLE-ABS-KEY ( ( "participat*" OR "shared" OR "employee voice" ) AND ( "DSS" OR "Decision Support Syste*" OR "Decision Making" ) ) AND NOT TITLE-ABS-KEY ( patient* OR clinic* OR health* OR medic* OR "public sector" ) AND ( LIMIT-TO ( DOCTYPE , "ar" ) )
    ```

**ScienceDirect High-Recall Pillars:**

*   **SD1 (GenAI + Decision Making):**
    ```
    ("Generative AI" OR "Conversational AI") AND ("Decision Making" OR DSS) -patient -clinic -medical -hospital -travel -education -public -sector
    ```

*   **SD2 (PDM + Decision Making):**
    ```
    (Participative OR "Employee Voice") AND ("Decision Making" OR "Decision Support" OR "DSS") -patient -clinic -medical -hospital -travel -education -public -sector
    ```

---

## 🚀 Repository Contents & Code Usage

### 📁 Structure
*   `CITRUS_Implementation.ipynb`: Main Google Colab notebook for embedding and expert calibration.
*   `hsda_df_final.csv`: The final synthesized 101 papers (The Requirement Matrix).
*   `cluster_orthogonality.csv`: Jaccard results proving thematic distinctness.

### 📝 Usage
1.  **Extract:** Use the strings above to export results from Scopus/ScienceDirect.
2.  **Embed:** Open the notebook, enter your Gemini API Key, and generate the `citrus_df`.
3.  **Negotiate:** Use the interactive Plotly UI to find the **"Semantic Knee"** and truncate your harvest.