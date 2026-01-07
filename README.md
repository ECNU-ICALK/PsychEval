# PsychEval: A Multi-Session and Multi-Therapy Benchmark for High-Realism AI Psychological Counselor

[![Paper](https://img.shields.io/badge/Paper-ArXiv-b31b1b.svg)](https://arxiv.org/html/2601.01802v1) **PsychEval** is a comprehensive benchmark designed to evaluate Large Language Models (LLMs) in the context of psychological counseling. Unlike existing benchmarks that focus on single-turn interactions or single-session assessments, PsychEval emphasizes **longitudinal, multi-session counseling** processes and **multi-therapy** capabilities.

![PsychEval Framework](https://github.com/ECNU-ICALK/PsychEval/tree/main/figures/dialogue_construction.png)
*Figure 1: Overview of the PsychEval framework and data construction pipeline.*

## 🌟 Key Features

* **Multi-Session Continuity:** Contains full counseling cycles spanning **6-10 sessions** per case, divided into three distinct stages:
    1.  **Case Conceptualization:** Information gathering and relationship building.
    2.  **Core Intervention:** Intervention and working through problems.
    3.  **Consolidation:** Consolidation and termination.
* **Multi-Therapy Coverage:** Supports evaluation across different therapeutic approaches (e.g., CBT, SFBT) along with a integrated therapy, requiring the AI to adapt its strategies.
* **High Realism & Granularity:**
    * Annotated with extensive professional skills.
    * Includes **677 meta-skills** and **4577 atomic skills**.
    * Focuses on memory continuity, dynamic goal tracking, and longitudinal planning.
* **Reliable Evaluation:** Introduces a multi-agent evaluation framework involving a **Client Simulator** (for realistic role-play) and a **Supervisor Agent** (for professional scoring).

## 📂 Dataset Structure

The dataset simulates a complete counseling lifecycle. Each case is structured to reflect the progression of real-world therapy.



## Evaluation Framework

We establish a holistic assessment system utilizing 18 therapy-specific and shared metrics (e.g., WAI for alliance, CTRS for CBT competency, and SCL-90 for symptom reduction). Our results show that PsychEval achieves unprecedented clinical fidelity, nearly doubling the scores of prior models in technical adherence (e.g., CTRS: 9.19).

##  Running the Evaluation
1. Main Evaluation Script

To execute the multi-dimensional evaluation, use the following command:
```
python3 -m eval.manager.evaluation_mutil
```

2. Configuring Metrics

You can easily customize the evaluation metrics by modifying the method_cls list in the configuration file. Simply update the list with the desired metric classes to toggle specific evaluations.

3. Baseline Reproduction & Data Conversion
To reproduce results from other papers (e.g., Simpsydial), you must first convert the data format to ensure compatibility.

   Step 1: Format Conversion Run the dedicated conversion script:
      ```
   python3 manager/Simpsydial/convert_simpsydial.py
      ```
   Step 2: Run Evaluation After conversion, proceed with the main evaluation script mentioned in step 1.


  
