# AI-Learning-Hub-2026

> **One-line positioning**: A textbook-style, systematic AI learning hub that spans from **common-sense literacy for practitioners across fields** to **hands-on geek / frontier practice**. Organized by a four-layer × three-dimension matrix, with frontier/geek content explicitly tagged "optional / experimental" so the structure keeps absorbing additions instead of being filled all at once. Helping you build **common-sense foundations, advanced knowledge, frontier progress, and future outlook** of AI, understand "what AI can/cannot do, how, and why", and follow its evolution.

---

## What this repo is / is not

- ✅ **Is**: a structured, progressive learning resource and explanation collection, led by a study plan that reorganizes quality resources from across the web into our framework.
- ❌ **Is not**: yet another link-dumping "bookmarks" folder, nor an engineering manual teaching you to train LLMs from scratch.

Online material is **abundant but fragmented**; systematic, textbook-grade introductory resources are scarce, and a study plan **tailored to building AI common sense for practitioners across fields** is rarer still. This repo fills that gap.

---

## Audience & prerequisites

- **Default main-track audience**: **practitioners across fields** — from biomedicine, statistics, engineering, humanities, etc., with some basic programming (e.g., Python/R) and logical thinking, but **not working in AI R&D** — the goal is to build AI common sense, architectural intuition, and a judgment framework without diving into engineering.
- **Extended audience**: hands-on geeks / practitioners — the sections tagged "frontier / geek · optional" in the Frontier layer (e.g., local inference engines, personal-AI discussion) are for this group, to explore as needed.
- **No requirement**: deep math or ML background — we add math **just-in-time**, not as a systematic re-study; the "optional"-tagged parts are not required either.

---

## Core principles

1. **System > fragments**: organized by a "layer × dimension" matrix, not by hype.
2. **Anchor the evolution**: take **DeepSeek R1 (2025-01)** as the landmark anchor for the mass popularization and open-weight inflection point of AI in China; trace causality up and down rather than memorizing isolated terms.
3. **Cite, don't copy**: for existing excellent collections (see "Upstream acknowledgments"), we **only link and attribute**, never copy their content; our explanations and curation are original.
4. **Common sense first**: build a clear sense of "what can/cannot be done" before diving into principles; beware of hype.
5. **Layer to absorb, don't fill**: content is explicitly tiered as "common-sense main track + frontier/optional branches" (see the "frontier / geek · optional" tags in each file). A knowledge base's value lies in whether its structure can keep absorbing later additions, not in covering every discussion at once.

---

## Structure matrix (the skeleton)

Four layers (depth) × three dimensions (slices):

| Layer ＼ Dim | Programming basics | Architecture evolution | Usage expansion |
|---|---|---|---|
| **Common sense** | Minimal programming context for AI | Rule→ML→DL→Transformer→LLM (simplified) | What it can/can't do, common myths |
| **Advanced** | HF/API hands-on, prompting as programming | Transformer deep-dive, pretrain/finetune/RLHF, MoE | RAG / Agent / MCP / research application |
| **Frontier** | Local small models (Ollama/llama.cpp) + constrained-hardware inference engines | **DeepSeek R1 anchor** (MoE+RL+CoT), reasoning-model paradigm | Deep-research agents, AI coding, progress speed-reading |
| **Outlook** | AI-assisted coding as default | AGI boundaries, world models, on-device AI | AI as a "life element", ethics/alignment, staying current |

---

## Contents

- [01 · Common sense](01-commonsense.md)
- [02 · Advanced knowledge](02-advanced.md)
- [03 · Frontier progress](03-frontier.md) (incl. "Local inference engines" subsection)
- [04 · Future outlook](04-outlook.md) (incl. "Personal AI vs centralized cloud" discussion)
- [05 · Hands-on practice](05-动手实操.md) (practical track: model acquisition / environment / Agent / prompting / RAG)
- [06 · Capstone projects](06-实战项目.md) (practical track: build a personal "external brain" with dsh)
- [Resources index](resources.md) (curated by module, with attribution and verification dates)
- [Evolution timeline](timeline.md) (attributed)
- [Learning paths (LEARNING-PATHS)](LEARNING-PATHS.md) (vertical recommended order)
- [Chinese translated/proofread notes (cn-notes/)](cn-notes/)
- [中文 README](README.md)

---

## Chinese translated notes (dual-track)

For **selected key English materials**, we use a dual-track system:
- **Original track (kept in place)**: English original links still point to the original author/upstream repo — not copied or altered.
- **Translated/proofread track (ours)**: under `cn-notes/`, we place **translated/adapted Chinese versions**, proofread for Chinese readers, with **clear attribution and copyright notice**.

---

## How to use

- **Systematic study (concept track)**: follow 01→02→03→04 to build complete cognition.
- **Hands-on first (practice track)**: start from 05 for tools, then 06 for a real project; go back to 01–04 for the "why".
- **On-demand**: with programming background, jump to 02; for a rough overview, read only 01 and 04.
- **Light hands-on**: throughout, "concept + tool experience" using ready-made APIs / Hugging Face / local small models; **no model training**; deep code dives marked 【optional】.
- **Spot the branches**: sections tagged "frontier / geek · optional" (e.g., the local inference engines in 03, the personal-AI discussion in 04) are extensions of the main track, not required reading — take them according to interest and hands-on ability.

---

## Upstream acknowledgments

We don't reinvent wheels. These excellent collections are **upstream entry points**, linked with attribution; their content is maintained by original authors, we don't copy:
- **Datawhale Chinese series**: happy-llm, llm-universe, llm-cookbook.
- **XiaomingX/awesome-llm**: evolution timeline + authoritative benchmarks.
- **ifLabX/Awesome-LLM-Learning**, **Hannibal046/Awesome-LLM**.
- **josephmisiti/awesome-machine-learning**.
- **llmbook-zh (Zhao Xin et al., 《大语言模型》)**.

---

## Content stance (facts / opinions)

- Our original explanations strive for accuracy and carry **verification dates**; technical parameters follow each project's official README / community benchmarks.
- Content marked as "discussion / opinion" (e.g., 04 §4.4 "Personal AI vs centralized cloud" and the attributed discussion paragraph) represents the authors' analysis and judgment, **not factual assertions or trend predictions** — discussion and contributions welcome.
- We don't aim to "cover everything" — a knowledge base's value lies in whether its structure can keep absorbing additions. Solidify the most valuable 20%, leave the rest to time and contributors.

---

## License

- Original content (explanations, curation, matrix framework): **CC BY 4.0**.
- Linked third-party resources retain their original licenses; attribution is noted.

---

## Contributing

Issues / PRs welcome: add quality resources, fix errors, propose better structure. Follow the "attribute, don't copy" principle.
