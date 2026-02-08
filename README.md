# 🧠 Duotronics M-1

> *"Every expert was once a beginner."*

**The learning variant:** Start stupid. Get smarter. Reduce API costs over time.

---

## What This Is

**M-1** is the first learning implementation of the Duotronics dual-hemisphere philosophy.

Unlike the [proof-of-concept](https://github.com/DevCabin/duotronics) which uses two cloud APIs, M-1 uses:

**Hemisphere 1 (Logic):** Local model on your GPU (starts "dumb")  
**Hemisphere 2 (Teacher):** Cloud API (smart, but expensive)

The magic: Every time the API refines a local response, it **teaches** the local model by storing the interaction in a vector database. Over time, the local model handles more queries independently, and API usage decreases.

---

## The Goal

Build a system that:
1. ✅ Starts accessible (modest GPU requirements)
2. ✅ Gets smarter with use (learns your domains)
3. ✅ Reduces API costs over time (70%+ local handling after 500 interactions)
4. ✅ Stays private (all learning data local)

---

## How It Works

```
[Your Question]
       ↓
[Check Vector Memory] — Do we have context for this?
       ↓
[Local Hemisphere] — Attempt answer with base knowledge + memory
       ↓
[Confidence Check] — Am I confident in this answer?
       ↓
   YES → Return answer (no API call)
       ↓
   NO → [API Hemisphere] — Refine + generate teaching feedback
       ↓
[Store in Vector DB] — Save corrected response + reasoning
       ↓
[Return final answer]
```

As the vector DB grows, more queries route locally. API usage trends toward zero for common domains.

---

## Status

🚧 **In Development** — M-1 is not ready yet.

Current progress:
- [x] Architecture design
- [x] Success criteria defined
- [ ] Basic orchestrator (local → API pipeline)
- [ ] Vector DB integration (ChromaDB)
- [ ] Confidence scoring
- [ ] RAG retrieval
- [ ] Web UI

---

## Requirements (When Ready)

### Hardware

| Component | Minimum | Recommended |
|-----------|---------|-------------|
| GPU VRAM | 12GB | 24GB |
| System RAM | 16GB | 32GB |
| Storage | 50GB | 100GB+ |

See the [equipment guide](https://github.com/DevCabin/duotronics/blob/main/EQUIPMENT.md) for budget build recommendations.

### Software
- Ollama or LM Studio
- Python 3.10+
- One API key (OpenAI or Anthropic) for the Teacher hemisphere

---

## Why "M-1"?

In Star Trek, Dr. Daystrom built increasingly sophisticated computer systems: M-1, M-2, M-3... up to the legendary M-5.

We're starting at the beginning. M-1 is the foundation — simple, functional, with room to grow.

Future versions:
- **M-2:** Improved confidence scoring, fine-tuning support
- **M-3:** Multi-domain specialization
- **M-4:** Personality systems, advanced RAG
- **M-5:** The dream — fully autonomous learning with minimal oversight

But first, we build M-1.

---

## Philosophy

1. **Start stupid.** A 7B local model won't beat GPT-4 on day one. That's okay.
2. **Learn genuinely.** Not by changing model weights (complex), but by building contextual memory (achievable).
3. **Privacy first.** All learning data stays on your machine.
4. **Measure progress.** Track API usage, local handling rate, confidence calibration.

---

## Related Projects

🔬 **[Duotronics](https://github.com/DevCabin/duotronics)** — Proof of concept (dual API)  
🧠 **Duotronics M-1** (this repo) — Learning system (local + API)

---

## Contributing

We're building in the open. Watch this space.

---

## License

MIT — Experiment freely.

---

*Built with 🧠 by [DevCabin](https://devcabin.com)*
