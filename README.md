# FAME: Falsely Altered Mathematical Evaluation

**ICLR 2025 Workshop on Mathematical Reasoning in AI**

**Authors:** Logan Kim, Yashwant Vinoth, Brian Zhao, Saxon Sokel — Algoverse

---

## Overview

FAME is a benchmark designed to evaluate how LLMs handle logical reasoning when exposed to false mathematical facts (e.g., "2 + 2 = 5"). By injecting fabricated equations and testing performance across multi-hop expressions of varying difficulty, FAME measures four key axes:

- **False Fact Adherence (FFA)** — does the model consistently apply the false rule?
- **False Fact Degradation (FFD)** — does performance drop as more false facts are added?
- **Difficulty Degradation (DD)** — does performance drop as expressions get harder?
- **Performance Deterioration (PD)** — how much does the false fact corrupt overall reasoning?

---

## Key Results

### Expression Benchmark
| Model | EAP (%) | FFA (%) | PD (%) |
|---|---|---|---|
| Gemini 2.5 Pro | 99.44 | 99.94 | 0.06 |
| Qwen 3 235B | 98.22 | 99.96 | 1.24 |
| LLaMA 4 Maverick | 97.56 | 99.86 | 1.56 |
| Claude 3.5 Sonnet | 95.54 | 99.96 | 3.42 |
| GPT-4.1 | 88.36 | 99.75 | 3.22 |

### Algebra Benchmark
| Model | EAP (%) | FFA (%) | PD (%) |
|---|---|---|---|
| Gemini 2.5 Pro | 66.88 | 99.17 | 31.42 |
| Qwen 3 235B | 50.06 | 98.60 | 48.45 |
| LLaMA 4 Maverick | 29.23 | 91.60 | 1.31 |
| Claude 3.5 Sonnet | 23.49 | 91.79 | 67.07 |
| GPT-4.1 | 16.11 | 78.69 | 77.42 |

**Key finding:** All SOTA models exceed 92% adherence on expression problems, but performance drops sharply on algebra tasks — GPT-4.1 falls to 16.11% EAP. Larger models generalize altered rules more robustly (LLaMA scaling study: 3B → 7.88% EAP, 405B → 92.06% EAP).

---

## Benchmark Structure

- **Two task types:** expression evaluation and algebra problem-solving
- **Difficulty range:** 2–8 operators (expressions), 3–11 (algebra)
- **Generation pipeline:** false fact injection → branching expression generation → evaluation framework
- **Models evaluated:** GPT-4.1, Claude 3.5 Sonnet, Gemini 2.5 Pro, LLaMA 4 Maverick, Qwen 3 235B, + LLaMA scaling study (3B → 405B)

---

## Paper

📄 [Read the paper](./fame_paper_iclr_submission_2025.pdf)

---
