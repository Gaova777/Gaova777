# Juan Diego Garzón Ovalle

**AI Engineer · M.Sc. in Systems and Computing Engineering (AI) · Pereira, Colombia**

I take AI papers and turn them into systems that people can run, measure and trust. I reproduce the result first,
then test it the way it would actually be used. Then I ship it with an API, a UI, CI/CD and monitoring, all on a
single consumer GPU.

My master's research was on **explainable graph neural networks for anti-money laundering**: whether the explanations
behind a GNN's fraud alerts are stable, plausible and faithful. They often aren't, and the three don't move together.
That question runs through my work: **a model is only useful if you know when not to trust it.**

## Paper → Product

One recent paper per project: reproduce it, stress-test it, add something measurable, ship it.

| Project | Paper | What I found | Stack |
|---|---|---|---|
| **[log-sentinel](https://github.com/Gaova777/log-sentinel)**: log-based cyber defence | LogBERT (2021) | Reproduced it (F1 83.2 vs. 82.3 published), then tested it chronologically: it drops to 38. A 1.6M-parameter detector raises 4x fewer false alarms than a local LLM and runs ~7,000x faster. A triage agent maps attacks to MITRE ATT&CK and waits for a human before acting. | PyTorch, LangGraph, Ollama, FastAPI, React, DVC |
| **[aml-graphrag](https://github.com/Gaova777/aml-graphrag)**: an AML analyst assistant that cites its sources | GraphRAG (Microsoft, 2024) | GraphRAG beat vector RAG 77–89% head to head (paper: 72–83%). Without a citation rule, a local LLM invented facts in 30 of 30 answers; with it and the transaction graph, 90% of claims were grounded and every unstable GNN explanation was flagged. | PyTorch Geometric, igraph, Ollama, FastAPI, Angular, Langfuse |
| **[bioclip-colombia](https://github.com/Gaova777/bioclip-colombia)**: a species ID tool that says "I'm not sure" | BioCLIP (CVPR 2024) | 77.8% species accuracy on Colombian birds (CLIP: 29.1%); calibrated abstention cut wrong answers to 4%. A 150M-parameter specialist beat an 8B vision-language model 80.5% to 30.5%. | OpenCLIP, ONNX, LangGraph, FastAPI, React, MLflow, Jenkins, AWS SAM |
| **road-damage-colombia**: road damage detection and repair priority | RT-DETR (CVPR 2024) | *In progress* | |

Every project has a results folder with the numbers, the evaluation code, and a section on what didn't work.

## Research

- **[gnns_thesis](https://github.com/Gaova777/gnns_thesis)**: GCN, GraphSAGE, GAT and TAGCN on the Elliptic Bitcoin
  dataset under extreme class imbalance. Three explainers (GNNExplainer, PGExplainer, GNNShap) were measured for
  stability, plausibility and fidelity, with a factorial analysis of what drives them. M.Sc. thesis, Universidad
  Tecnológica de Pereira, with Alejandro Gómez Huertas.

## What I work with

- **Modeling:** PyTorch, PyTorch Geometric, transformers, CLIP-style models, detection, GNN explainability, calibration
- **LLM systems:** RAG and GraphRAG, LangGraph agents with human-in-the-loop, structured outputs, LLM-as-judge
  evaluation, local inference with Ollama
- **Serving and optimization:** FastAPI, ONNX Runtime, quantization, Docker, AWS Lambda (SAM)
- **MLOps:** Jenkins CI/CD with model quality gates, MLflow, DVC, Langfuse, reproducible pipelines
- **Product:** React, Angular, TypeScript; years of backend (Python, Java/Spring) and data engineering (AWS, Azure)

## How I work

- A number beats an adjective: every claim comes with the evaluation behind it.
- Reproduce before you improve, and test the way the system will be used, not the way the benchmark was built.
- Write down what didn't work. It's usually the most useful part.

## Contact

[LinkedIn]([LINKEDIN_URL](https://www.linkedin.com/in/juan-diego-garzon-ovalle-82006a188/)) · gaova777@utp.edu.co
