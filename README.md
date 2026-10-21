# Hi, I'm Juan Diego

**AI Engineer · M.Sc. in Systems and Computing Engineering (AI) · Pereira, Colombia**

I read AI papers, rebuild them from scratch, and then test them the way they'd actually be used, which is rarely how
the benchmark was built. Then I ship them as working systems on a single consumer GPU.

My master's thesis was about **when not to trust a model**: whether the explanations behind a graph neural network's
money-laundering alerts are stable, plausible and faithful. Mostly they weren't, and the three didn't move together.
I've kept asking that question since, in every domain I touch.

### Things I've measured that surprised me

- **A benchmark result can halve under realistic testing.** I reproduced LogBERT's log anomaly detection (F1 83.2 vs.
  82.3 published). Trained on the past and tested on the future, the way it would be deployed, it dropped to 38.
- **A one-line rule beat a transformer** on the same benchmark: "flag any log message never seen in training" scored
  96.8 against LogBERT's 88.1.
- **Small specialists beat big generalists where it counts.** A 150M-parameter biology model identified Colombian birds
  at 80.5%; an 8B vision-language model managed 30.5%, while claiming 95% confidence on 184 of 200 photos.
- **LLMs invent unless the system forbids it.** Asked why a Bitcoin transaction was flagged, a local LLM made up
  specifics in 30 of 30 answers. Forcing every claim to cite a fact, and checking it with code, got 90% of claims
  grounded.
- **Retrieval changes what an agent says, not just how sure it sounds.** From memory, a security agent labelled SSH
  brute force as "Valid Accounts" every time; with the MITRE ATT&CK catalogue retrieved, it named Brute Force in 63% of
  cases.
- **A popular explanation method draws the image, not the model.** On chest X-rays and blood smears, Guided
  Backprop's heat map stayed 91–93% the same after I randomized the network's top layers. Gradient maps passed that
  test but changed 95% of what they highlighted under invisible noise.
- **A stable explanation isn't a faithful one.** 56% of GNNExplainer's explanations changed when re-run with another
  seed, and the edges they highlighted often didn't move the model's score at all.

### What I'm into

- Evaluation that reflects deployment: temporal splits, base rates, calibration, abstention, cost per prediction
- LLM systems that cite, check and defer: GraphRAG, agents with human approval, LLM-as-judge done carefully
- Explainability that's measured rather than drawn: stability, fidelity, plausibility
- Making models cheap enough to actually run: small specialists, ONNX, quantization, local inference

### Background

Before AI I spent years building software end to end: Python and Java backends, React and Angular frontends, and data
platforms on AWS and Azure. That's why I care about the parts around the model: APIs, CI/CD with quality gates,
monitoring, and what happens when the data drifts.

**Toolbox:** PyTorch · PyTorch Geometric · Hugging Face · OpenCLIP · LangGraph · Ollama · FastAPI · ONNX Runtime ·
Docker · Jenkins · MLflow · DVC · Langfuse · React · Angular · AWS

### Talk to me about

Why your model's validation score won't survive production · graph ML for fraud · getting an LLM to say "I don't know"
· Colombian biodiversity and data

gaova777@utp.edu.co
