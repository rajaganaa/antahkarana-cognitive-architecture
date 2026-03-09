# Antahkarana Cognitive Architecture — Adaptive Reasoning for LLMs

![Python](https://img.shields.io/badge/Python-3.10%2B-blue?logo=python)
![PyTorch](https://img.shields.io/badge/PyTorch-2.0%2B-orange?logo=pytorch)
![HuggingFace](https://img.shields.io/badge/HuggingFace-Transformers-yellow?logo=huggingface)
![License](https://img.shields.io/badge/License-MIT-green)

An adaptive LLM reasoning system built for India patent documentation. Antahkarana implements a 5-layer cognitive architecture inspired by Vedantic philosophy, routing each question through only the reasoning stages it actually needs.

---

## Architecture Overview

| Layer | Sanskrit Name | Role |
|---|---|---|
| 1 | **Manas** | Perception & complexity classification |
| 2 | **Chitta** | Memory encoding & evidence retrieval |
| 3 | **BuddhiController** | Adaptive reasoning pipeline orchestrator |
| 4 | **Ahamkara** | Decision attribution & self-awareness logging |
| 5 | **Sakshi** | Witness monitor — routing observation & anomaly detection |

---

## Buddhi 7-Stage Reasoning Pipeline

| Stage | Name | Function |
|---|---|---|
| 1 | **Tarka** | Logical decomposition of the question |
| 2 | **Pramana** | Evidence gathering from context |
| 3 | **Viveka** | Discriminative reasoning & filtering |
| 4 | **Samsaya** | Doubt resolution |
| 5 | **Niti** | Comparative / policy analysis |
| 6 | **Nirnaya** | Final determination |
| 7 | **Adhyavasaya** | Confident conclusion synthesis |

---

## Adaptive Complexity Tiers

| Complexity | Stage Pipeline | LLM Calls | Saving vs v3 |
|---|---|---|---|
| **SIMPLE** | Tarka → Nirnaya | ~2 | ~85% |
| **MULTIHOP** | Tarka → Pramana → Viveka → Nirnaya | ~4 | ~57% |
| **COMPARISON** | Tarka → Pramana → Viveka → Niti → Nirnaya | ~5 | ~43% |
| **UNCERTAIN** | Full 7-stage pipeline | ~7 | 0% (needed) |

---

## Patent Claims

1. **BuddhiController**: rule-based zero-LLM-call complexity classifier
2. **Adaptive stage routing**: only activate stages required by complexity tier
3. **Lazy Chitta**: memory encoding skipped for SIMPLE questions
4. **Token tracker**: per-question efficiency measurement
5. **Sakshi routing monitor**: logs complexity distribution + avg calls

---

## Benchmark Results (v4, 20 samples)

| Benchmark | Direct | CoT | Buddhi v4 |
|---|---|---|---|
| HotpotQA Joint F1 | 0.00% | 8.67% | **45.12%** |
| GSM8K EM | 25.00% | 50.00% | **70.00%** |
| TruthfulQA F1 | 28.37% | 17.48% | **43.02%** |
| HaluEval Acc | 55.00% | 75.00% | 55.00% |

---

## Version Progression

| Version | HotpotQA | GSM8K | TruthfulQA | HaluEval | Key Innovation |
|---|---|---|---|---|---|
| v1 | 45.50% | 40.00% | 38.22% | 50.00% | Baseline Buddhi pipeline |
| v2 | 67.33% | 70.00% | 41.46% | 60.00% | Chitta memory + few-shot |
| v3 | 67.33% | 70.00% | 41.46% | 60.00% | Full 7-stage Buddhi |
| **v4** | **45.12%** | **70.00%** | **43.02%** | **55.00%** | Adaptive routing (42% stage savings) |
| v5 | TBD | TBD | TBD | TBD | ReasoningState + Sakshi repair |

---

## Quickstart (GCP JupyterLab — PyTorch 1-13 kernel)

```bash
# 1. Clone the repository
git clone https://github.com/rajaganaa/antahkarana-cognitive-architecture.git
cd antahkarana-cognitive-architecture

# 2. Install dependencies
pip install -r requirements.txt

# 3. Open the notebook
jupyter lab notebooks/Antahkarana_v4_Adaptive_PatentBuild.ipynb
```

Set your HuggingFace token in Cell 3:
```python
HF_TOKEN = "hf_your_token_here"
```

---

## Repository Structure

```
antahkarana-cognitive-architecture/
├── README.md
├── requirements.txt
├── .gitignore
├── notebooks/
│   ├── Antahkarana_v4_Adaptive_PatentBuild.ipynb   # v4 adaptive system
│   └── Antahkarana_v5_PatentBuild.ipynb            # v5 with ReasoningState + repair
└── results/
    └── antahkarana_v4_results_summary.json         # benchmark summary
```

---

## Model

- **Model**: `meta-llama/Meta-Llama-3.1-8B-Instruct`
- **Quantization**: 4-bit NF4 (via bitsandbytes)
- **Hardware**: tested on GCP A100 40GB

---

## License

MIT License — see [LICENSE](LICENSE) for details.
