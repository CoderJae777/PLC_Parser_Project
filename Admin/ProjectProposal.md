## Project Proposal (Group 7): LaTeX-to-Markdown Converter

### Team Members

- Goh Yi Shen, 1006852
- Joshua Chua Tze Ern, 1006627
- Chew Ming Hui, 1006892

---

### 1) Topic and Problem Statement

LaTeX is widely used for academic and technical publication workflows, while Markdown is preferred for fast drafting (notes, READMEs, documentation).

However, converting LaTeX into Markdown manually is time-consuming and error-prone, especially for complex structures (tables, equations, nested lists) and malformed input.

Our project proposes a C-based LaTeX-to-Markdown converter that parses a restricted LaTeX subset and emits structured Markdown output with robust diagnostics for invalid syntax.

---

### 2) Expected Inputs and Outputs

#### Input files

- **Primary text input:** `.tex` LaTeX file

#### Output files

- **Primary text output:** `.md` Markdown file
- **Diagnostics report text output:** `.report.txt` (line/column, error code, recovery action)

---

### 3) Deliverables

1. C codebase (`.c` / `.h`)
2. Custom lexer + parser with explicit state-machine logic
3. LaTeX-to-Markdown emitter
4. Error handling + recovery system
5. CLI executable and Makefile
6. README with build/run instructions

---

### 4) Related Work and Differentiation

OpenAI’s [Prism](https://openai.com/prism/) is a **LaTeX-native scientific writing workspace** that integrates GPT-5.2 for drafting, revising, collaboration, and publication preparation inside a cloud editor. It is designed to support the LaTeX authoring workflow rather than perform deterministic format conversion between markup languages. :contentReference[oaicite:0]{index=0}

Our project targets a different problem: **reliable, parser-driven document conversion** between LaTeX and Markdown for portability and documentation reuse. Specifically, we focus on a constrained, formally defined subset and provide:

- deterministic conversion behavior (same input + options => same output),
- custom lexer/parser implementation in ANSI C,
- explicit state-machine design,
- robust diagnostics and recovery for malformed input,
- CLI-based batch processing suitable for local/CI workflows.

In short, Prism improves writing _within_ a LaTeX workspace, while our tool addresses **structured cross-format translation** and parser robustness—an engineering gap Prism does not primarily aim to solve
