# NordDRG‑AI Benchmark for Large‑Language Models

**Transparent, reproducible evaluation of Diagnosis‑Related Group (DRG) reasoning in modern LLMs**

---

## 🚀 Overview

This repository packages everything needed to reproduce the experiments described in our accompanying paper — *from raw NordDRG rule tables to a ready‑made prompt/answer set and evaluation scripts*.

The benchmark tests whether large‑language models can correctly reason over the complex classification logic used for hospital funding in the Nordic countries. It includes full DRG logic tables, governance manuals, and a set of 14 case-based tasks targeting code lookup, cross-table inference, and qualitative audits.

All artefacts are described in detail in the [arXiv paper (2025)](https://arxiv.org/abs/xxx).

---

## 📂 Repository layout

```text
├── NordDRG_Combined2024PL/                         # Grouper specification: Combined 2024 price-list
│   ├── 2023-06-14_Combined2024PL_xls.xlsx           # Core logic and classification rules
│   ├── 2023-06-14_ICD+_NCSP+_Combined2024PL_xls.xlsx# ICD+NCSP links used in DRG assignments
│   ├── DRG_Names-FIN-Grouper-All-Names.xlsx         # All Finnish DRG names (multi-version)
│   ├── DRG_Names-FIN-Grouper-EN.xlsx                # English DRG names (subset)
│   ├── DRG_Names-FIN-Grouper-FI-EN.xlsx             # Bilingual Finnish–English names
│   ├── DRG_Names-FIN-Grouper-FI.xlsx                # Finnish-only DRG names
│   ├── How to read NordDRG definition tables 2021-12-20.pdf  # Governance guide
│   └── How to write technical changes for NordDRG – 2021-12-21.pdf # Change request instructions
├── NordDRG Benchmark Questions – 2025-06-11.xlsx     # Prompts + gold-standard answers (IDs 1–14)
├── norddrg-benchmark-arxiv_2025-06-11.pdf            # Preprint: benchmark description and results
└── (scripts, notebooks, evaluation code to be added)
```

### Notes

* **Grouper specification versions** — Each folder like `NordDRG_Combined2024PL` corresponds to a specific DRG version. New versions (e.g. 2025, 2026) should be added in their own directories to preserve reproducibility across releases.
* **Benchmark Q\&A file** — `NordDRG Benchmark Questions – 2025-06-11.xlsx` includes 14 prompts (IDs 1–14) spanning both quantitative and qualitative tasks, plus the gold-standard answer key in one consolidated Excel file.
* **PDF Manuals** — The two PDF documents explain how to read NordDRG definition tables and how to format technical change proposals, enabling evaluation of governance-aware model outputs.

---

## 📊 Evaluation metric

The official score is **macro-averaged accuracy** across the 9 quantitative DRG assignment tasks (IDs 1–9). A response is considered **correct** if it matches the gold DRG codes exactly (case-insensitive, unordered). Tasks 10–14 are evaluated qualitatively based on explanation quality and guideline adherence.

---

## 🧪 Demonstration summary

A demonstration included in the preprint evaluates five proprietary LLMs (GPT-4o, o3, o4-mini-high, Gemini Pro, Gemini Flash) against the benchmark. Results confirm that the NordDRG benchmark captures cross-model variance invisible to general NLP leaderboards, especially on multilingual and governance-based tasks.

---

## 📝 Citation

If you use this benchmark, please cite:

```bibtex
@misc{norddrg-ai-benchmark2025,
  title        = {The NordDRG AI Benchmark for Large Language Models},
  author       = {Pitkäranta, Tapio},
  howpublished = {arXiv preprint arXiv:xxx},
  year         = {2025}
}
```

---

## 🤝 Contributing

Contributions are welcome! Please open an issue before making major changes such as:

* Adding new question sets
* Supporting additional DRG versions
* Proposing alternative evaluation metrics

---

## ⚖️ License

All NordDRG tables are redistributed under the terms of the **NordDRG Consortium license** (*non-commercial research use only*). See individual files for license headers where applicable.

---

*Happy benchmarking!*
