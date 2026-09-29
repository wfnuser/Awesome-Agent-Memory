# Awesome Agent Memory [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

A curated collection of papers, projects, frameworks, and benchmarks on **memory systems for AI agents** — covering how agents encode, store, retrieve, evolve, and forget information across interactions.

> Memory is increasingly recognized as the bottleneck of agentic intelligence. While model capabilities continue to scale, the ability to *persistently learn from experience, adapt over time, and act with coherence across long horizons* depends fundamentally on how memory is designed. This repository tracks the frontier of this fast-moving field.

## Why Agent Memory?

Foundation model-based agents are being deployed in high-stakes settings — from software engineering and scientific discovery to autonomous web interaction and financial trading. Their effectiveness hinges not only on reasoning ability, but on **memory**: how they retain context across sessions, consolidate experiences into reusable knowledge, and selectively forget what is no longer relevant.

Agent Memory differs from LLM Memory (static, parametric retention of training data) and traditional RAG (retrieve-then-read over a fixed corpus). It is **online, interaction-driven, and under the agent's active control**, spanning three forms of storage:

- **Token-level memory**: External text/vector stores with retrieval pipelines
- **Parametric memory**: Knowledge encoded in model weights, updated via continual learning or experience distillation
- **Latent memory**: KV caches, learned memory tokens, and hidden state representations

And serving three functional roles:

- **Factual memory**: What the agent knows (facts, user preferences, world knowledge)
- **Experiential memory**: What the agent has done (episodes, trajectories, outcomes)
- **Working memory**: What the agent is currently attending to (task state, active context)

---

## Table of Contents

- [Awesome Agent Memory ](#awesome-agent-memory-)
  - [Why Agent Memory?](#why-agent-memory)
  - [Table of Contents](#table-of-contents)
  - [Surveys](#surveys)
  - [Papers](#papers)
    - [Memory Architecture \& Mechanism](#memory-architecture--mechanism)
    - [RL-based Memory Management](#rl-based-memory-management)
    - [Long-term Conversational Memory](#long-term-conversational-memory)
    - [Memory for Multi-Agent Systems](#memory-for-multi-agent-systems)
    - [Benchmarks \& Evaluation](#benchmarks--evaluation)
  - [Open-Source Projects \& Frameworks](#open-source-projects--frameworks)
  - [Workshops \& Community](#workshops--community)
  - [Contributing](#contributing)
  - [Citation](#citation)
  - [Star History](#star-history)

---

## Surveys

| Date    | Title                                   | Links                                                                                                      | Highlight                                                  |
| ------- | --------------------------------------- | ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------- |
| 2025.12 | Memory in the Age of AI Agents          | [paper](https://arxiv.org/abs/2512.13564) · [repo](https://github.com/Shichun-Liu/Agent-Memory-Paper-List) | Forms/Functions/Dynamics taxonomy; 47 authors, 1.3k+ stars |
| 2025.11 | A Survey on LLM-based Autonomous Agents | [paper](https://arxiv.org/abs/2308.11432)                                                                  | Broad agent survey with memory as a core module            |

---

## Papers

### Memory Architecture & Mechanism

> *How should agent memory be structured, organized, and accessed?*

| Date    | Title                                                           | Venue     | Links                                                                                       | Key Idea                                                                  |
| ------- | --------------------------------------------------------------- | --------- | ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| 2025.02 | A-MEM: Agentic Memory for LLM Agents                            | ICLR 2026 | [paper](https://arxiv.org/abs/2502.12110) · [code](https://github.com/agentic-memory/A-MEM) | Zettelkasten-inspired dynamic memory with autonomous indexing and linking |
| 2026.01 | MAGMA: Multi-Graph based Agentic Memory Architecture            | arXiv     | [paper](https://arxiv.org/abs/2601.03236)                                                   | Multi-graph structure for heterogeneous memory types                      |
| 2026.01 | EverMemOS: Self-Organizing Memory Operating System              | arXiv     | [paper](https://arxiv.org/abs/2601.02163)                                                   | Memory OS abstraction for structured long-horizon reasoning               |
| 2025.12 | Memoria: Scalable Agentic Memory Framework                      | arXiv     | [paper](https://arxiv.org/abs/2512.12686)                                                   | Production-grade personalized conversational memory                       |
| 2025.04 | Mem0: Production-Ready AI Agents with Scalable Long-Term Memory | arXiv     | [paper](https://arxiv.org/abs/2504.19413) · [code](https://github.com/mem0ai/mem0)          | Practical long-term memory layer for production agents                    |

### RL-based Memory Management

> *Training agents to actively decide what to remember, update, and forget.*

| Date    | Title                                                                      | Venue              | Links                                                                              | Key Idea                                                                    |
| ------- | -------------------------------------------------------------------------- | ------------------ | ---------------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| 2025.07 | MemAgent: Reshaping Long-Context LLM with Multi-Conv RL-based Memory Agent | ICLR 2026 **Oral** | [paper](https://arxiv.org/abs/2507.02259)                                          | DAPO-extended RL for memory; 8K→3.5M extrapolation with <10% loss           |
| 2025.06 | MEM1: Learning to Synergize Memory and Reasoning                           | ICLR 2026          | [paper](https://arxiv.org/abs/2506.15841) · [code](https://github.com/MIT-MI/MEM1) | End-to-end RL for constant-context agents; 3.5× perf, 3.7× memory reduction |
| 2026.01 | Mem-α: Learning Memory Construction via RL                                 | ICLR 2026          | [paper](https://arxiv.org/abs/2509.25911)                                          | RL for complex multi-component memory; generalizes 20K→400K+ tokens         |
| 2025.08 | Memory-R1: Enhancing LLM Agents to Manage Memories via RL                  | arXiv              | [paper](https://arxiv.org/abs/2508.19828)                                          | RL-driven memory CRUD operations                                            |
| 2025.11 | MemSearcher: Training LLMs to Reason, Search and Manage Memory via E2E RL  | arXiv              | [paper](https://arxiv.org/abs/2511.02805)                                          | Unified search + memory management with RL                                  |

### Long-term Conversational Memory

> *Enabling agents to maintain coherent, personalized interactions over time.*

| Date    | Title                                                                         | Venue | Links                                     | Key Idea                                                  |
| ------- | ----------------------------------------------------------------------------- | ----- | ----------------------------------------- | --------------------------------------------------------- |
| 2025.11 | A Simple Yet Strong Baseline for Long-Term Conversational Memory              | arXiv | [paper](https://arxiv.org/abs/2511.17208) | Retrieval-based baseline that outperforms complex systems |
| 2025.12 | Hindsight is 20/20: Building Agent Memory that Retains, Recalls, and Reflects | arXiv | [paper](https://arxiv.org/abs/2512.12818) | Reflection-augmented memory for conversational agents     |
| 2025.10 | Pre-Storage Reasoning for Episodic Memory                                     | arXiv | [paper](https://arxiv.org/abs/2509.10852) | Shifting inference burden to memory write time            |

### Memory for Multi-Agent Systems

> *How multiple agents share, coordinate, and collectively manage memory.*

| Date    | Title                                                          | Venue | Links                                     | Key Idea                                           |
| ------- | -------------------------------------------------------------- | ----- | ----------------------------------------- | -------------------------------------------------- |
| 2025.12 | MemVerse: Multimodal Memory for Lifelong Learning Agents       | arXiv | [paper](https://arxiv.org/abs/2512.03627) | Multimodal memory across agent lifetimes           |
| 2025.10 | LEGOMem: Modular Procedural Memory for Multi-agent LLM Systems | arXiv | [paper](https://arxiv.org/abs/2510.04851) | Modular, composable memory for workflow automation |
| 2025.11 | RCR-Router: Role-Aware Context Routing for Multi-Agent Systems | arXiv | [paper](https://arxiv.org/abs/2508.04903) | Structured memory routing across agent roles       |

### Benchmarks & Evaluation

> *How do we measure whether memory actually works?*

| Date    | Title                                                                                     | Venue              | Links                                                                                               | Key Idea                                                                                           |
| ------- | ----------------------------------------------------------------------------------------- | ------------------ | --------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| 2026.09 | EmbodiedMemory-Bench: Benchmarking Embodied Memory for Long-Horizon Embodied Tasks | arXiv | [paper](https://arxiv.org/abs/2609.28236) · [code](https://github.com/ZJU-OmniAI/Embodied-Omni/tree/main/embodied_memory) | Tests memory through later embodied actions across visual recall, changing state, interaction outcomes, and experience generalization |
| 2025.07 | MemoryAgentBench: Evaluating Memory in LLM Agents via Incremental Multi-Turn Interactions | ICLR 2026          | [paper](https://arxiv.org/abs/2507.05257) · [code](https://github.com/HUST-AI-HYZ/MemoryAgentBench) | 4 core competencies: retrieval, test-time learning, long-range understanding, selective forgetting |
| 2025.03 | LongMemEval: Evaluating Very Long-Term Conversational Memory                              | arXiv              | [paper](https://arxiv.org/abs/2410.10813)                                                           | Long-term memory benchmark for chat assistants                                                     |
| 2025.11 | HaluMem: Evaluating Hallucinations in Memory Systems                                      | arXiv              | [paper](https://arxiv.org/abs/2511.03506)                                                           | Memory hallucination detection and evaluation                                                      |
| 2026.03 | MobileMem: Long-Horizon Memory in Real-World Mobile Environments                          | ICLR 2026 Workshop | [paper](https://openreview.net/forum?id=w5I11HrMgJ)                                                 | Memory from real mobile usage trajectories, beyond dialogue-only                                   |

---

## Open-Source Projects & Frameworks

> *Tools and systems you can actually use to build memory-augmented agents.*

| Project              | Description                                                                                                                                            | Stars               | Links                                                                                   |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------- | --------------------------------------------------------------------------------------- |
| **Mem0**             | Production-ready long-term memory layer for AI agents and assistants. Supports user/session/agent-level memory with auto-extraction and retrieval.     | 25k+                | [GitHub](https://github.com/mem0ai/mem0) · [Docs](https://docs.mem0.ai)                 |
| **MemGPT / Letta**   | OS-inspired memory management for LLMs — virtual context management with hierarchical memory tiers (main context, archival, recall).                   | 12k+                | [GitHub](https://github.com/cpacker/MemGPT) · [Paper](https://arxiv.org/abs/2310.08560) |
| **LangChain Memory** | Memory modules for LangChain agents — buffer, summary, entity, knowledge graph, and conversation memory. Widely used in production.                    | (part of LangChain) | [Docs](https://python.langchain.com/docs/modules/memory/)                               |
| **LlamaIndex**       | Data framework for LLM applications with sophisticated retrieval and memory capabilities, including composable indices and chat memory.                | 38k+                | [GitHub](https://github.com/run-llama/llama_index)                                      |
| **Zep**              | Long-term memory service for AI assistants — auto-summarization, entity extraction, temporal awareness, and semantic search over conversation history. | 2k+                 | [GitHub](https://github.com/getzep/zep)                                                 |
| **MemEngine**        | Unified and modular library specifically designed for developing advanced memory systems for LLM-based agents.                                         | —                   | [Paper](https://arxiv.org/abs/2505.02941)                                               |
| **Cognee**           | Memory management for AI agents and applications — deterministic memory with knowledge graphs and vector retrieval.                                    | 2k+                 | [GitHub](https://github.com/topoteretes/cognee)                                         |
| **MEM1**             | MIT's RL-based memory agent framework. Trains agents to consolidate memory as part of reasoning.                                                       | —                   | [GitHub](https://github.com/MIT-MI/MEM1)                                                |

---

## Workshops & Community

| Event                                           | Venue              | Date     | Links                                                                                                                |
| ----------------------------------------------- | ------------------ | -------- | -------------------------------------------------------------------------------------------------------------------- |
| MemAgents: Memory for LLM-Based Agentic Systems | ICLR 2026 Workshop | Apr 2026 | [Website](https://sites.google.com/view/memagent-iclr26/) · [OpenReview](https://openreview.net/forum?id=U51WxL382H) |
| Lifelong Agents: Learning, Aligning, Evolving   | ICLR 2026 Workshop | Apr 2026 | [Website](https://lifelongagent.github.io/)                                                                          |
| New Frontiers in Associative Memories           | ICLR 2025 Workshop | —        | —                                                                                                                    |
| L2M2: Learning and Memorization in LLMs         | ACL 2025 Workshop  | —        | —                                                                                                                    |

---

## Contributing

We welcome contributions from the community! To add a paper or project:

1. Fork this repo
2. Add your entry to the appropriate section following the existing table format
3. Include: title, date, venue (if applicable), links (paper + code), and a one-line description of the key idea
4. Submit a pull request

Please ensure:
- Papers are sorted by date (newest first) within each section
- One-line descriptions focus on *what's new*, not just the topic
- Project entries include working links and a brief, honest description

---

## Citation

If you find this resource useful, please consider giving it a ⭐ and citing:

```bibtex
@misc{awesome-agent-memory,
  title={Awesome Agent Memory: A Curated List of Papers and Projects on Memory Systems for AI Agents},
  author={wfnuser},
  year={2026},
  url={https://github.com/wfnuser/awesome-agent-memory}
}
```

---

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=wfnuser/awesome-agent-memory&type=Date)](https://star-history.com/#wfnuser/awesome-agent-memory&Date)

---

*This repo is actively maintained. Last updated: March 2026.*
