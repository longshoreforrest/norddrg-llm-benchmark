# NordDRG‑AI Benchmark for Large‑Language Models

**Transparent, reproducible evaluation of Diagnosis‑Related Group (DRG) reasoning in modern LLMs**

---

## 🚀 Overview

This repository packages everything you need to reproduce the experiments described in our accompanying paper — *from raw NordDRG rule tables to a ready‑made prompt/answer set and evaluation scripts*.

The goal is to provide an open benchmark that tests whether large‑language models can correctly reason over the complex classification logic used for hospital funding across the Nordic countries.

---

## 📂 Repository layout

```text
├── NordDRG_Combined2024PL/                       # Grouper specification: Combined 2024 price‑list
│   ├── 2023‑06‑14_Combined2024PL_xls.xlsx
│   ├── 2023‑06‑14_ICD+_NCSP+_Combined2024PL_xls.xlsx
│   ├── DRG_Names‑FIN‑Grouper‑All‑Names.xlsx
│   ├── DRG_Names‑FIN‑Grouper‑EN.xlsx
│   ├── DRG_Names‑FIN‑Grouper‑FI‑EN.xlsx
│   ├── DRG_Names‑FIN‑Grouper‑FI.xlsx
│   ├── How to read NordDRG definition tables 2021‑12‑20.pdf
│   └── How to write technical changes for NordDRG – 2021‑12‑21.pdf
├── NordDRG Benchmark Questions – 2025‑06‑10.xlsx  # Questions + gold answers
├── norddrg‑benchmark_2025‑06‑10.pdf               # Pre‑print of the paper
└── (scripts, notebooks, etc.)
```

### Notes

* **Grouper specification versions** – Each top‑level folder such as `NordDRG_Combined2024PL` contains the master definition tables for a specific NordDRG release. Keep future releases in their own folders so multiple versions can coexist.
* **Benchmark Q\&A sheet** – `NordDRG Benchmark Questions – 2025‑06‑10.xlsx` contains *both* the 12 natural‑language prompts *and* the expert‑validated gold answers, consolidated into one file.

---

## 📊 Evaluation metric

The official score is *macro‑averaged accuracy* across all 12 DRG assignment tasks. A response is considered **correct** if it matches the gold DRG code exactly (case‑insensitive). See `scoring.py` for details.

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

Issues and pull requests are welcome! Please open an issue first if you plan major changes (e.g., new question sets, alternative metrics). For guidelines, see `CONTRIBUTING.md`.

---

## ⚖️ License

The NordDRG tables are redistributed under the terms of the NordDRG Consortium license (non‑commercial research use only).

---

*Happy benchmarking!*
