# AI Quick Reference

A comprehensive, searchable quick reference guide and architectural knowledge base covering modern **Artificial Intelligence, Large Language Models (LLMs), Autonomous AI Agents, Model Context Protocol (MCP), RAG Systems, and Production ML Infrastructure**.

🌐 **Live Documentation Site:** [https://patrikbego.github.io/ai-quick-ref/](https://patrikbego.github.io/ai-quick-ref/)

---

## Overview

This repository hosts a curated collection of real-world systems engineering breakdowns, visual architecture diagrams, and technical summaries spanning 8 core domains of modern AI engineering.

All visual diagrams are persisted locally under `assets/images/` to ensure persistent, high-resolution rendering without external broken image links.

---

## Topic Guides

| # | Guide | Focus Area | Highlights |
|:--|:---|:---|:---|
| **01** | [**AI Agents & Multi-Agent Architectures**](docs/01-ai-agents-multi-agent.md) | Autonomous agents, loops, coordination & memory | Multi-agent control loops, memory hierarchies, A2A/ACP communication protocols, agentic payment settlement |
| **02** | [**Model Context Protocol (MCP) & Tools**](docs/02-mcp-and-tool-use.md) | Standardized tool integration & context routing | Model Context Protocol specifications, MCP vs APIs, MCP vs Skills, enterprise tool gateways (Pinterest, Figma) |
| **03** | [**LLM Architecture, Training & Inference**](docs/03-llm-architecture-inference.md) | Model internals, optimization & hardware acceleration | Attention mechanisms (RoPE), KV-cache paging & compression, speculative decoding, LoRA/QLoRA, TPU/GPU systolic arrays |
| **04** | [**RAG, Vector Search & Retrieval**](docs/04-rag-and-vector-search.md) | Enterprise data grounding & knowledge retrieval | GraphRAG, Agentic RAG, multi-tenant vector partitioning, distributed SQL vector indexing (CockroachDB), hybrid search |
| **05** | [**AI Evaluations, Safety & Robustness**](docs/05-ai-evals-safety-robustness.md) | Benchmarking, alignment, security & guardrails | LLM-as-a-judge, sycophancy, lost-in-the-middle context limits, prompt injection threat models, automated evaluation flywheels |
| **06** | [**Industry Case Studies & Implementations**](docs/06-industry-case-studies.md) | Production architectures from tier-1 engineering teams | Real-world deployments across OpenAI, Netflix, Stripe, DoorDash, Grab, Microsoft, Meta, LinkedIn, Uber, and more |
| **07** | [**Developer AI Tools & Coding Agents**](docs/07-developer-tools-coding-agents.md) | Developer tooling, CLI agents & workflows | Claude Code, Cursor coding agent architecture, GitHub/Vercel/Replit platforms, AI-native software engineering practices |
| **08** | [**Foundational Roadmaps & Core Concepts**](docs/08-foundations-and-roadmaps.md) | Ecosystem landscapes, taxonomies & learning paths | Generative AI tech stacks, open-source AI frameworks, top GitHub machine learning repositories, system design interview frameworks |

---

## Architecture & Technology Stack

- **Site Engine:** Native GitHub Pages with [Jekyll](https://jekyllrb.com/)
- **Theme:** [Just the Docs](https://just-the-docs.com/) (`remote_theme: just-the-docs/just-the-docs`)
- **Search:** Built-in client-side full-text search powered by Lunr.js
- **Visual Assets:** 690+ local high-resolution architecture diagrams and infographics
- **Color Scheme:** Dark mode enabled by default

---

## Repository Structure

```text
ai-quick-ref/
├── _config.yml                               # Jekyll & theme configuration
├── index.md                                  # Homepage with quick links and directory table
├── docs/
│   ├── 01-ai-agents-multi-agent.md           # AI Agents & Multi-Agent Architectures
│   ├── 02-mcp-and-tool-use.md                # Model Context Protocol (MCP) & Tools
│   ├── 03-llm-architecture-inference.md      # LLM Architecture, Training & Inference
│   ├── 04-rag-and-vector-search.md           # RAG, Vector Search & Retrieval
│   ├── 05-ai-evals-safety-robustness.md      # AI Evaluations, Safety & Robustness
│   ├── 06-industry-case-studies.md           # Industry Case Studies & Implementations
│   ├── 07-developer-tools-coding-agents.md   # Developer AI Tools & Coding Agents
│   └── 08-foundations-and-roadmaps.md        # Foundational Roadmaps & Core Concepts
└── assets/
    └── images/                               # Locally hosted diagram assets
        ├── agents/
        ├── mcp/
        ├── llm/
        ├── rag/
        ├── evals/
        ├── case-studies/
        ├── dev-tools/
        └── foundations/
```

---

## Local Development

To run the documentation site locally with live reloading:

### Prerequisites
- Ruby (>= 3.0)
- Bundler

### Installation & Run

1. Clone the repository:
   ```bash
   git clone https://github.com/patrikbego/ai-quick-ref.git
   cd ai-quick-ref
   ```

2. Run with Jekyll:
   ```bash
   bundle exec jekyll serve
   ```

3. Open your browser at `http://localhost:4000/ai-quick-ref/`.
