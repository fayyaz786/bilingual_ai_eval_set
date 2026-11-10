# Bilingual AI Evaluation Set (Arabic and English)

A small, hand built evaluation set showing where language models make mistakes in **Arabic**, and how I catch and correct them.

**Author:** Fayyaz Shahid, AI Trainer and LLM Response Evaluator  
**Contact:** [Upwork](https://www.upwork.com/freelancers/~01b0b9c69d62c91200) · [LinkedIn](https://www.linkedin.com/in/fayyazshahid) · [fayyazshahid.com](https://fayyazshahid.com)

---

## Why Arabic evaluation matters

Arabic is spoken by over 400 million people, but models still make errors that an English only reviewer would never notice: wrong gender agreement, dialect where formal Arabic was requested, and translations that flip the meaning of a sentence. These errors can be embarrassing, costly or unsafe. This set documents six of the most common types.

## The cases

| ID | Error type | Severity |
|---|---|---|
| AR01 | Idiom translation | Major |
| AR02 | Gender agreement | Major |
| AR03 | Number error (million vs billion) | Critical |
| AR04 | Dropped negation (safety) | Critical |
| AR05 | Register (dialect instead of formal Arabic) | Major |
| AR06 | Factual hallucination in Arabic | Critical |

Full cases with the flawed response, the explanation and the corrected answer: **[CASES.md](CASES.md)**

## Files

| File | Contents |
|---|---|
| [CASES.md](CASES.md) | Readable version of every case |
| [cases.jsonl](cases.jsonl) | The same cases as JSON Lines, one case per line, ready to load into an evaluation pipeline |

Each JSON record has these fields: `id`, `category`, `severity`, `task`, `source_en`, `flawed_response`, `error`, `corrected`.

## Severity scale

| Severity | Meaning |
|---|---|
| **Critical** | Changes the meaning, a number or a fact, or creates a safety risk |
| **Major** | Breaks grammar, register or a clear instruction, but the meaning survives |
| **Minor** | Style or wording that a native reader would notice but not misunderstand |

## What this shows

* Reviewing Arabic output for meaning, not just fluency
* Catching critical number and negation errors in translation
* Checking gender agreement and formal register (Modern Standard Arabic vs dialect)
* Fact checking Arabic answers about Saudi Arabia

> **Note:** the flawed responses were written to reproduce error patterns commonly seen in model output. They are demonstration examples, not copies of a specific model's output.

## Load the data in Python

```python
import json

with open("cases.jsonl", encoding="utf-8") as f:
    cases = [json.loads(line) for line in f]

critical = [c["id"] for c in cases if c["severity"] == "Critical"]
print(critical)  # ['AR03', 'AR04', 'AR06']
```

## License

MIT
