# Evaluating LLMs as a Bridge Between Cyber Threats and Business Risk for Executive Decision-Making

**Evaluating Whether a Locally Deployed Large Language Model Can Reliably Translate Technical Cyber Threat Intelligence into Executive-Appropriate Business Risk Summaries**

---

## Overview

This repository accompanies a graduate research project examining whether a locally deployed large language model (LLM) — **Gemma3:27b via Ollama** — can produce executive-quality business risk summaries from technical cyber threat intelligence (CTI) reports, without relying on cloud-based AI services or exposing sensitive intelligence data to external systems.

The research applies five systematically progressive prompt strategies (S0–S4) across a corpus of 20 real-world CTI source reports, scoring all generated outputs against a four-dimension rubric designed to assess executive communication quality and analytic tradecraft.

---

## Research Question

> *To what extent can AI-powered natural language processing reduce the time required to translate technical cyber threat intelligence into business risk assessments that enable informed executive decision-making?*

---

## Repository Contents

```
.
├── reports/
│   └── [1000 randomized LLM-generated outputs ready for blind scoring]
├── CTI_Tracker_All_Reports.xlsx             # Scoring workbook (1,000 records across S0–S4)
├── source_report_index.xlsx                 # Index of 20 CTI source reports (4 threat categories)
└── README.md
```

> **Note:** Raw CTI source reports are not redistributed in this repository due to vendor copyright. The source report index documents title, vendor, publication date, and threat category for each of the 20 reports used.

---

## Methodology

### Local LLM Environment

| Component | Detail |
|---|---|
| Model | Gemma3:27b |
| Runtime | Ollama (custom Modelfile) |
| Context Window | 32,768 tokens (`num_ctx`) |
| Interface | AnythingLLM (RAG / Query Mode) |
| Embeddings | nomic-embed-text-v1 |

### Prompt Strategies

| ID | Strategy | Description |
|---|---|---|
| S0 | Baseline | No structural guidance; minimal prompt |
| S1 | Role Framing | Explicit analyst persona and audience framing |
| S2 | Structured Output | Defined section headers and output constraints |
| S3 | Writing Principles | One-shot approach adapted into embedded writing principles after RAG pipeline could not reliably distinguish the exemplar document from the source report under analysis |
| S4 | Chain-of-Thought | Stepwise reasoning instruction before output generation |

Each strategy was applied to all 20 source reports, producing **200 total outputs** (1,000 scored records across the CTI tracker workbook).

### CTI Corpus — Threat Categories

| Category | Reports |
|---|---|
| Ransomware | 5 |
| Supply Chain Attack | 5 |
| Business Email Compromise (BEC) | 5 |
| Zero-Day / Edge Device Exploitation | 5 |

### Evaluation Rubric

Outputs are scored on a **1.0–5.0 composite scale** using blind scoring. The pass threshold is **≥ 3.5 / 5.0**, established as an independent quality benchmark for executive communication and analytic tradecraft.

| Dimension | Weight |
|---|---|
| Actionability | 35% |
| Analytical Rigor | 30% |
| Language Appropriateness | 20% |
| Structural Compliance | 15% |

> The benchmark is threshold-based, not comparative to a human control group. This design decision reflects the practical absence of a validated corpus of authentic executive CTI summaries from non-enterprise security vendors.

---



## Intended Audience

This work is intended for:

- **CTI practitioners** evaluating LLM-assisted workflow automation
- **Security leaders** assessing the feasibility of privacy-preserving AI for threat communication
- **Researchers** exploring prompt engineering for domain-specific, non-technical output generation
- **Graduate students** developing methodology for evaluating generative AI output quality

---

## Limitations & Scope

- Results are specific to **Gemma3:27b** and may not generalize to other local or cloud-hosted models.
- The 20-report corpus, while representative across four threat categories, is not exhaustive.
- Scoring reflects a single evaluator's blind assessment; inter-rater reliability analysis is not included in this iteration.
- The research does not cover real-time or streaming inference pipelines.

---

## License

All written research, rubrics, methodology, and data in this repository are licensed under [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/). You are free to use, share, and adapt this material as long as appropriate credit is given.

See `LICENSE-CONTENT.md` at the repository root for the full license text.

CTI source reports are not included in this repository due to vendor copyright. Refer to the source report index for title, vendor, and publication details.

---

## Contact

For questions related to this research, please open an issue in this repository.
