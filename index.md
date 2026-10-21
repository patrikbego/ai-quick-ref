---
layout: page
title: "AI Quick Reference"
---

A curated, searchable engineering knowledge base covering modern **Artificial Intelligence, Large Language Models (LLMs), Autonomous AI Agents, Model Context Protocol (MCP), RAG Systems, and Production ML Infrastructure**.

---

## 🗺️ Engineering Learning Paths

Choose a structured learning track or explore the complete topic guides below:

### 🎓 1. Learn AI (Foundations & Model Internals)
*Master how modern foundation models work under the hood, from historical milestones to autoregressive generation, attention, and test-time reasoning.*
1. [**AI History & Milestones**]({{ '/01-foundations-roadmaps/#1-ai--llm-history-timeline-19502026' | relative_url }}) — Early symbolic AI to the LLM era (1950–2026).
2. [**Basic LLM Algorithm**]({{ '/01-foundations-roadmaps/#2-general-algorithm-behind-a-basic-llm' | relative_url }}) — Prompt input, tokenization, embeddings, and next-token prediction loops.
3. [**Transformer Architecture & RoPE**]({{ '/02-llm-architecture/#2-how-the-math-used-in-19th-century-heat-physics-helps-llms-understand-sentences' | relative_url }}) — Attention heads, rotary position embeddings, and harmonic frequencies.
4. [**Training Pipeline: SFT, RLHF & RLVR**]({{ '/02-llm-architecture/#1-test-time-reasoning--post-training-alignment-direct-prompting-sft-rlhf-and-rlvr' | relative_url }}) — Pre-training, instruction fine-tuning, and automated verifiable rewards with GRPO.
5. [**Inference & KV-Cache Optimization**]({{ '/02-llm-architecture/#8-what-happens-inside-an-ai-chatbot-between-enter-and-the-first-word' | relative_url }}) — PagedAttention, KV-cache paging, and speculative decoding.

### 🛠️ 2. Build AI (Applications, Tool Use & Agents)
*Bridge standalone models into production systems with external data grounding, standardized tool protocols, and autonomous agent loops.*
1. [**The End-to-End RAG Stack**]({{ '/03-rag-vector-search/#1-the-end-to-end-rag-application-stack' | relative_url }}) — Chunking, embeddings, hybrid vector search, and GraphRAG.
2. [**Model Context Protocol (MCP)**]({{ '/04-mcp-and-tools/' | relative_url }}) — Standardized context routing, tool gateways, and MCP vs APIs.
3. [**Autonomous Agent Loops & Memory**]({{ '/05-ai-agents/#1-autonomous-ai-agent-architecture--core-building-blocks' | relative_url }}) — Orchestrator topologies, planning, working/episodic memory, and A2A communication.
4. [**Developer AI Tools & Coding Agents**]({{ '/07-developer-tools/' | relative_url }}) — Claude Code CLI, Cursor architectures, and AI-driven CI/CD.
5. [**Hands-on Production Architectures (Python & Java)**]({{ '/07-developer-tools/#1-hands-on-production-architectures-python--java-implementation-guide' | relative_url }}) — Runnable code patterns: Hybrid RAG with RRF, FastMCP servers, Spring AI clients, ReAct agent loops, and schema guardrails.

### 🏛️ 3. Architect AI (Production Engineering & Systems at Scale)
*Design scalable, resilient enterprise infrastructure with rigorous evaluation, safety guardrails, and real-world reference architectures.*
1. [**AI Evaluations & Benchmarking**]({{ '/06-ai-evals-safety/' | relative_url }}) — LLM-as-a-judge, automated evaluation flywheels, and regression tests.
2. [**Safety & Threat Models**]({{ '/06-ai-evals-safety/' | relative_url }}) — Sycophancy mitigation, prompt injection defense, and context boundary limits.
3. [**Distributed Serving & Hardware**]({{ '/02-llm-architecture/#11-ep222-what-is-googles-tpu' | relative_url }}) — Quantization (LoRA/QLoRA), vLLM/SGLang serving, and TPU systolic arrays.
4. [**Production System Design & Case Studies**]({{ '/08-industry-case-studies/' | relative_url }}) — 7-step system design framework and production architectures across OpenAI, Netflix, Stripe, and Meta.

---

## 📚 Topic Guides

Explore the 8 comprehensive architectural guides using the sidebar navigation on the left, or jump directly from the directory below:

| # | Topic Guide | Key Architectural Focus |
|:---|:---|:---|
| **01** | [**Foundational Roadmaps & Concepts**]({{ '/01-foundations-roadmaps/' | relative_url }}) | AI ecosystem landscapes, generative AI tech stacks, open-source AI frameworks, learning roadmaps |
| **02** | [**LLM Architecture & Inference**]({{ '/02-llm-architecture/' | relative_url }}) | Positional RoPE, LoRA/QLoRA, KV-cache optimization, speculative decoding, TPU systolic arrays |
| **03** | [**RAG & Vector Search**]({{ '/03-rag-vector-search/' | relative_url }}) | GraphRAG, Agentic RAG, CockroachDB distributed vector indexing, Airtable hybrid search |
| **04** | [**Model Context Protocol & Tools**]({{ '/04-mcp-and-tools/' | relative_url }}) | Anthropic MCP protocol, tool gateways, Pinterest & Figma MCP ecosystems, MCP vs Skills |
| **05** | [**AI Agents & Multi-Agent**]({{ '/05-ai-agents/' | relative_url }}) | Agent loops, memory tiers, Stripe agent payments (MPP), A2A/ACP communication protocols |
| **06** | [**AI Evals & Safety**]({{ '/06-ai-evals-safety/' | relative_url }}) | LLM-as-a-judge, sycophancy, lost-in-the-middle context limits, prompt injection threat models |
| **07** | [**Developer AI Tools & Code Examples**]({{ '/07-developer-tools/' | relative_url }}) | Production Python & Java code (RAG, MCP, Agents), Claude Code CLI, Cursor coding agents, dev platforms |
| **08** | [**Industry Case Studies**]({{ '/08-industry-case-studies/' | relative_url }}) | Production architectures across OpenAI, Netflix, Stripe, DoorDash, Grab, Microsoft, Meta, LinkedIn |

---

## ⚡ Site Features

- **Interactive Floating Table of Contents:** On the right-hand side of every guide, tracking your scroll position in real time.
- **Sidebar Navigation:** Click between all 8 domains with icons and active highlights.
- **Instant Full-Text Search:** Press the search box or hit `/` to search across all topics and summaries.
- **Dark Mode Support:** Toggle between dark, light, or system themes at the bottom of the sidebar.
- **690+ High-Resolution Diagrams:** Persisted locally to ensure fast, reliable rendering without broken external links.
