# VerilogBenchmark-Dataset

### Benchmark Datasets for “Benchmarking Open-Source Static Analysis Tools for Verilog”

---

## 📘 Overview

**VerilogBenchmark-Dataset** provides two curated benchmark datasets for evaluating open-source **Verilog static analysis tools**, including **Verilator**, **Verible**, **svlint**, **Icarus Verilog**, and **Yosys**.  
These datasets are constructed to measure the precision, recall, F1-score and other related metrics of tools based on both *standardized rule violations* and *open-source defects*.

This repository supports the study:  
> *“Benchmarking Open-Source Static Analysis Tools for Verilog”*  
and aims to foster reproducible experiments, fair tool comparisons, and benchmark-driven improvement of Verilog analyzers.

---
```
## 📁 Directory Structure
VerilogBenchmark-Dataset/
├── Standard_Dataset/ # Dataset based on formal design rules
│ ├── positive/ # 77 positive (compliant) Verilog modules
│ ├── negative/ # 77 negative (violation) Verilog modules
│ └── mapping_table.csv # Rule-to-category mapping table (8 unified defect types)
│
├── OpenSource_Dataset/ # Dataset collected from GitHub projects
│ ├── simple/ # 30 simple-level real defects
│ ├── medium/ # 30 medium-level defects
│ ├── complex/ # 30 complex multi-module or race-condition defects
│ └── labels_summary_mapped.csv # CSV summary mapping each file to its unified defect category
│
└── README.md # This documentation file

```
---
🧩 Unified Defect Categories

All benchmarks are classified into **8 unified defect categories** to enable cross-tool comparison:

| ID | Defect Category | Description |
|----|-----------------|--------------|
| 1  | Syntax Structure | Misuse of keywords, illegal declarations, or unmatched blocks |
| 2  | Signal Usage | Undefined, unconnected, or wrongly assigned signals |
| 3  | Bit-width Mismatch | Inconsistent widths in expressions or assignments |
| 4  | Sensitivity List Errors | incomplete, redundant, or inconsistent sensitivity in an always block |
| 5  | Race Conditions | Multi-driver conflicts or non-deterministic signal updates |
| 6  | Module Port Faults | Port direction/type mismatches or repeated instantiation |
| 7  | Logic Synthesis Anomalies | Constructs causing synthesis-time behavior differences |
| 8  | Reserved Word Misuse | Use of keywords or prohibited identifiers as names |

---

## ⚙️ Usage

### Clone the Repository
```bash
git clone https://github.com/colagaga/VerilogBenchmark-Dataset.git
cd VerilogBenchmark-Dataset
```
---

Explore Dataset

Standard_Dataset/ → Use for rule-based evaluation

OpenSource_Dataset/ → Use for real-world verification robustness testing

Each defect case is a standalone Verilog file and can be tested with different analysis tools using shell scripts or Python automation.
```
## 🧪 Evaluation Metrics
Metrics/
├── Detection Performance Metrics
│ ├── Precision
│ ├── Recall
│ └── F1-Score
│
├── Efficiency And Compatibility Metrics
│ ├── Runtime
│ ├── Supported operating systems
│ 
└── Rule Distribution Metrics

```

## 🧰 Related Tools

| Tool | Description | Repository |
|------|--------------|-------------|
| **Verible** | Style and syntax checker | [chipsalliance/verible](https://github.com/chipsalliance/verible) |
| **Verilator** | SystemVerilog linter / simulator | [verilator/verilator](https://www.veripool.org/wiki/verilator) |
| **svlint** | Lightweight SystemVerilog linter | [dalance/svlint](https://github.com/dalance/svlint) |
| **Icarus Verilog** | Simulation and synthesis tool | [steveicarus/iverilog](http://iverilog.icarus.com/) |
| **Yosys** | Open synthesis suite | [YosysHQ/yosys](https://github.com/YosysHQ/yosys) |

📈 How to Use for Benchmarking

Run each tool on Standard_Dataset/negative and OpenSource_Dataset/ files.

Parse logs to extract rule IDs and reported messages.

Compare each detection result against the provided CSV labels.

Compute precision, recall, F1 and other metrics for each tool.


📜 Citation

If you use this dataset in your research, please cite it as:

@misc{VerilogBenchmarkDataset2025,
  author = {Zhu, Yixian},
  title = {VerilogBenchmark-Dataset: Benchmark Datasets for Benchmarking Open-Source Static Analysis Tools for Verilog},
  year = {2025},
  howpublished = {\url{https://github.com/colagaga/VerilogBenchmark-Dataset}},
  note = {Accessed: Oct. 2025}
}

📄 License

Released under the MIT License.
Free for research, education, and non-commercial use with proper citation.

🤝 Acknowledgment

This dataset references:

Guidelines for HDL Program Design and Verification


Maintainer:
📧 Zhu Yixian (colagaga)
🌐 GitHub Repository

