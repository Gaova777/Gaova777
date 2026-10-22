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
- **Reading the customer's history is worth 30 points of F1, and a year of drift erases all of it.** On 24M card
  transactions, a transformer over the last ten purchases reached F1 0.89 against 0.59 for a per-transaction XGBoost.
  Trained on the past and tested on the next years, every model fell below 0.08: fraud comes in new campaigns.
- **An LLM agent couldn't plan a port, and was the best part of the system anyway.** With Reflexion, a 4B model
  improved on HumanEval (83.5% to 88.4%), yet produced 0 executable berth plans in 30 scenarios that an exact
  solver optimized in under half a second. As the operator's interface it understood 93% of requests in English
  and Spanish, and letting code do the arithmetic removed its addition mistakes.
- **"Written for a 5-year-old" is a claim you can measure.** Asked for a children's story at a given age, a 4B model
  landed at the right Spanish reading level (Fernández-Huerta plus sentence length) 42% of the time; measuring each
  story and having it rewrite the sentences that missed brought that to 71%. Along the way I reproduced the three
  claims of Adversarial Diffusion Distillation (SDXL-Turbo) on one RTX 4060.
- **A detector is only as good as the country it was trained in.** RT-DETR beat YOLO on road damage in every
  country I tested (0.57 vs 0.50 mAP50 in Japan) and ran at 95 FPS after TensorRT; trained on Japan alone, YOLO
  fell from 0.49 to 0.07 in India, and on a country no model had seen, all of them dropped to 0.08–0.16.
- **A time-series foundation model lost to the calendar.** Chronos reproduced its paper to the third decimal, but on
  daily Colombian rain it scored worse than "what usually falls this week of the year". Feeding its forecasts into a
  landslide risk model still ranked days better than that baseline, because most of the signal was the rain that
  had already fallen.
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
diffusers · Docker · Jenkins · Terraform · MLflow · DVC · Langfuse · React · Next.js · Angular · AWS

### Talk to me about

Why your model's validation score won't survive production · graph ML for fraud · getting an LLM to say "I don't know"
· Colombian biodiversity and data

gaova777@utp.edu.co
