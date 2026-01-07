# PsychEval: A Multi-Session and Multi-Therapy Benchmark for High-Realism AI Psychological Counselor

[**PsychEval**](https://arxiv.org/html/2601.01802v1) is a comprehensive benchmark designed to evaluate Large Language Models (LLMs) in the context of psychological counseling. Unlike existing benchmarks that focus on single-turn interactions or single-session assessments, PsychEval emphasizes **longitudinal, multi-session counseling** processes and **multi-therapy** capabilities.


## 🌟 Key Features

* **Multi-Session Continuity:** Contains full counseling cycles spanning **6-10 sessions** per case, divided into three distinct stages:
    1.  **Case Conceptualization:** Information gathering and relationship building.
    2.  **Core Intervention:** Intervention and working through problems.
    3.  **Consolidation:** Consolidation and termination.
![Unified Workflow](https://github.com/ECNU-ICALK/PsychEval/blob/main/figures/unified_counseling_flow.png)
<!-- *Figure 1: Overview of the unified counseling workflow.* -->
* **Multi-Therapy Coverage:** Supports evaluation across different therapeutic approaches (e.g., CBT, SFBT) along with a integrated therapy, requiring the AI to adapt its strategies.
* **High Realism & Granularity:**
    * Annotated with extensive professional skills.
    * Includes **677 meta-skills** and **4577 atomic skills**.
    * Focuses on memory continuity, dynamic goal tracking, and longitudinal planning.
* **Reliable Evaluation:** Introduces a multi-agent evaluation framework involving a **Client Simulator** (for realistic role-play) and a **Supervisor Agent** (for professional scoring).

## 📂 Dataset Construction

The dataset simulates a complete counseling lifecycle. Each case is structured to reflect the progression of real-world therapy.

![Case Extraction](https://github.com/ECNU-ICALK/PsychEval/blob/main/figures/case_extraction.png)
<!-- *Figure 2: Overview of the Case Extraction.* -->

![Dialogue Construction](https://github.com/ECNU-ICALK/PsychEval/blob/main/figures/dialogue_construction.png)
<!-- *Figure 3: Overview of the dialogue construction pipeline.* -->


## 📊 Data Distribution
![Statistical Information](https://github.com/ECNU-ICALK/PsychEval/blob/main/figures/statistical_information.png)
<!-- *Table 1: Statistical Information of **PsychEval**.* -->

![Key Feaure Comparison](https://github.com/ECNU-ICALK/PsychEval/blob/main/figures/feature_compare.png)
<!-- *Table 2: Comparison with existing benchmarks on key characteristics.* -->

![Statistical Information Comparison](https://github.com/ECNU-ICALK/PsychEval/blob/main/figures/statistical_information_compare.png)
<!-- *Table 3: Comparison with existing benchmarks in terms of statistical information.* -->


## Evaluation Framework

We establish a holistic assessment system utilizing 18 therapy-specific and shared metrics (e.g., WAI for alliance, CTRS for CBT competency, and SCL-90 for symptom reduction). Our results show that PsychEval achieves unprecedented clinical fidelity, nearly doubling the scores of prior models in technical adherence (e.g., CTRS: 9.19).

![Quality](https://github.com/ECNU-ICALK/PsychEval/blob/main/figures/quality.png)
<!-- *Table 3: Data quality of our benchmark in terms of counselor-level and client-level metrics.* -->


##  Running the Evaluation
1. Main Evaluation Script

To execute the multi-dimensional evaluation, use the following command:
```python
python3 -m eval.manager.evaluation_mutil
```

2. Configuring Metrics

You can easily customize the evaluation metrics by modifying the method_cls list in the configuration file. Simply update the list with the desired metric classes to toggle specific evaluations.

3. Baseline Reproduction & Data Conversion
To reproduce results from other papers (e.g., Simpsydial), you must first convert the data format to ensure compatibility.

   Step 1: Format Conversion Run the dedicated conversion script:
   ```python
   python3 manager/Simpsydial/convert_simpsydial.py
   ```
   Step 2: Run Evaluation After conversion, proceed with the main evaluation script mentioned in step 1.



## 📝 Citation

If you use PsychEval in your research, please cite our paper:

```bibtex
@inproceedings{pan2026psycheval,
      title={PsychEval: A Multi-Session and Multi-Therapy Benchmark for High-Realism AI Psychological Counselor}, 
      author={Qianjun Pan and Junyi Wang and Jie Zhou and Yutao Yang and Junsong Li and Kaiyin Xu and Yougen Zhou and Yihan Li and Jingyuan Zhao and Qin Chen and Ningning Zhou and Kai Chen and Liang He},
      year={2026},
      eprint={2601.01802},
      archivePrefix={arXiv},
      primaryClass={cs.AI},
      url={https://arxiv.org/abs/2601.01802}, 
}

```


  
