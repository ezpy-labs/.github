# ezpy
 
**Tools and research for understanding machine learning at every stage — from raw data, to training from scratch, to distributed learning, to figuring out why a trained model fails.**

---
 
## What we're building
 
Most ML tooling focuses on getting a model trained and deployed. ezpy focuses on the parts that get skipped: is your data actually clean before you train on it, do you understand what the core algorithms are doing under the hood, can your models be trained collaboratively without exposing private data, can a computer read handwriting the way it reads printed text, and — after training — where exactly does the model break, and why.
 
## Repositories
 
| Repo | Description |
|---|---|
| [`dataset-doctor`](https://github.com/ezpy/dataset-doctor) | Detects data leakage, duplicates, label noise, class imbalance, missing values, and distribution shifts before model training. |
| [`ml-from-scratch`](https://github.com/ezpy/ml-from-scratch) | Educational implementations of core machine-learning algorithms without high-level ML frameworks. |
| [`federated-research-lab`](https://github.com/ezpy/federated-research-lab) | Experimental platform for federated learning, decentralized training, aggregation strategies, privacy, and malicious-client detection. |
| [`polyglot-ink`](https://github.com/ezpy/polyglot-ink) | Handwritten source-code and natural-language recognition across multiple programming and human languages. |
| [`model-autopsy`](https://github.com/ezpy/model-autopsy) | Analyzes where and why trained models fail, including confidence errors, subgroup weaknesses, and robustness problems. |
 
## How the repos fit together
 
```text
Before training                 During training                After training
────────────────                 ───────────────                ──────────────
dataset-doctor        ──────▶    ml-from-scratch /       ──────▶ model-autopsy
(catch leakage,                  federated-research-lab           (find where and
 duplicates, imbalance             (train with a clear              why the model
 before you train)                 understanding of the             fails, by
                                    algorithm, or across             confidence,
                                    decentralized clients)           subgroup, or
                                                                      robustness)
 
polyglot-ink is a standalone application area — handwriting and cross-language
recognition — that draws on the same fundamentals as the rest of the org.
```
 
- **`dataset-doctor`** runs first — a model trained on leaky, duplicated, or imbalanced data is hard to trust no matter how it's built afterward.
- **`ml-from-scratch`** and **`federated-research-lab`** cover two different ways of training: understanding core algorithms without framework abstractions, versus training collaboratively across multiple clients without centralizing their data.
- **`model-autopsy`** closes the loop — once a model is trained, it digs into confidence errors, weak subgroups, and robustness gaps to explain failures rather than just reporting an accuracy number.
- **`polyglot-ink`** is its own applied project — recognizing handwritten code and natural language across multiple languages, useful for scenarios like grading handwritten exam solutions.
## Getting started
 
- Cleaning up a dataset before training? Start with [`dataset-doctor`](https://github.com/ezpy/dataset-doctor).
- Want to understand how core ML algorithms actually work? [`ml-from-scratch`](https://github.com/ezpy/ml-from-scratch) builds them without relying on high-level frameworks.
- Interested in distributed/privacy-preserving training? [`federated-research-lab`](https://github.com/ezpy/federated-research-lab) is the research-heavy end of the org — expect experimental code and potential paper-track work.
- Trying to figure out why a trained model underperforms in production or on certain inputs? [`model-autopsy`](https://github.com/ezpy/model-autopsy) is built for that.
## Contributing
 
We welcome contributions across all repositories — new data-quality checks, additional from-scratch algorithm implementations, federated-learning experiments, and failure-analysis techniques. See each repository's `CONTRIBUTING.md` for specifics, or the shared guidelines in this organization's [`.github`](https://github.com/ezpy/.github) repo.
