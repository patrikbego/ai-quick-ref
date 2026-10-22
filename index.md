---
layout: page
title: "AI Quick Reference"
---

A curated, searchable engineering knowledge base covering modern **Artificial Intelligence, Large Language Models (LLMs), Autonomous AI Agents, Model Context Protocol (MCP), RAG Systems, and Production ML Infrastructure**.

---

## 🎯 Explore by Skill Level

Jump directly to content matched to your engineering focus:

| Level | Target Scope | Key Guides & Focus Areas |
|:---:|:---|:---|
| <span class="badge bg-success">🟢 Beginner</span> | Core terminology, evolutionary milestones, and high-level intuition | [01 Foundations & Roadmaps]({{ '/01-foundations-roadmaps/' | relative_url }}), [Prompt Engineering]({{ '/06-ai-evals-safety/#16-a-guide-to-effective-prompt-engineering' | relative_url }}), [Nested Taxonomy]({{ '/01-foundations-roadmaps/#4-nested-taxonomy-ai-vs-machine-learning-vs-deep-learning-vs-generative-ai' | relative_url }}) |
| <span class="badge bg-warning text-dark">🟡 Intermediate</span> | Application engineering, RAG pipelines, MCP tool gateways, and agent loops | [03 RAG & Vector Search]({{ '/03-rag-vector-search/' | relative_url }}), [04 Model Context Protocol]({{ '/04-mcp-and-tools/' | relative_url }}), [05 AI Agents]({{ '/05-ai-agents/' | relative_url }}), [06 Evals & Safety]({{ '/06-ai-evals-safety/' | relative_url }}), [07 Dev Tools & Code]({{ '/07-developer-tools/' | relative_url }}) |
| <span class="badge bg-danger">🔴 Advanced</span> | Low-level transformer mechanics, mathematical alignment (RLVR/GRPO), and distributed serving | [02 LLM Architecture & Inference]({{ '/02-llm-architecture/' | relative_url }}), [08 Industry Case Studies]({{ '/08-industry-case-studies/' | relative_url }}), [Production AI Lifecycle]({{ '/02-llm-architecture/#1-the-production-ai-lifecycle-blueprint-end-to-end-enterprise-systems-architecture' | relative_url }}), [TPU Hardware]({{ '/02-llm-architecture/#14-ep222-what-is-googles-tpu' | relative_url }}), [Speculative Decoding]({{ '/02-llm-architecture/#11-how-to-make-llms-3x-faster' | relative_url }}) |

<div class="my-3 p-3 bg-light rounded border d-flex flex-wrap align-items-center justify-content-between gap-2">
  <div>
    <strong>⚡ Interactive Cheat Sheet & VRAM Sizing Calculator:</strong>
    <span class="text-muted d-block small">Interactive 7-stage lifecycle flowchart, GPU VRAM sizing simulator, and multi-tier decision matrices.</span>
  </div>
  <a href="{{ '/cheatsheet/' | relative_url }}" class="btn btn-sm btn-primary">Launch Interactive Cheat Sheet ↗</a>
</div>

---

## 🏷️ Quick Topic Tag Filter

Click any tag to search and filter across all 159+ architectural guides:

<div class="d-flex flex-wrap gap-2 mb-4">
  <button type="button" class="btn btn-sm btn-outline-primary" onclick="filterByTag('rag')">🏷️ #RAG (13)</button>
  <button type="button" class="btn btn-sm btn-outline-success" onclick="filterByTag('agents')">🤖 #AI-Agents (12)</button>
  <button type="button" class="btn btn-sm btn-outline-info text-dark" onclick="filterByTag('mcp')">🔌 #MCP (11)</button>
  <button type="button" class="btn btn-sm btn-outline-danger" onclick="filterByTag('reasoning')">🧠 #Reasoning & RLVR (6)</button>
  <button type="button" class="btn btn-sm btn-outline-warning text-dark" onclick="filterByTag('inference')">⚡ #Inference & KV-Cache (19)</button>
  <button type="button" class="btn btn-sm btn-outline-secondary" onclick="filterByTag('evals')">🛡️ #Evals & Safety (18)</button>
  <button type="button" class="btn btn-sm btn-outline-dark" onclick="filterByTag('code')">💻 #Coding-Agents (13)</button>
  <button type="button" class="btn btn-sm btn-outline-danger" onclick="filterByTag('hardware')">⚙️ #TPU & Hardware (8)</button>
  <button type="button" class="btn btn-sm btn-outline-success" onclick="filterByTag('case-studies')">🏛️ #Case-Studies (50)</button>
</div>

<script>
function filterByTag(tag) {
  var searchInput = document.getElementById('search-input');
  var searchTrigger = document.getElementById('search-trigger');
  if (searchInput) {
    if (searchTrigger) searchTrigger.click();
    searchInput.focus();
    searchInput.value = tag;
    searchInput.dispatchEvent(new Event('input', { bubbles: true }));
  }
}
</script>

---

## 🗺️ Engineering Learning Paths

Choose a structured learning track or explore the complete topic guides below:

### 🎓 1. Learn AI (Foundations & Model Internals)
*Master how modern foundation models work under the hood, from historical milestones to autoregressive generation, attention, and test-time reasoning.*
1. [**AI History & Milestones**]({{ '/01-foundations-roadmaps/#1-ai--llm-history-timeline-19502026' | relative_url }}) <span class="badge bg-success">🟢 Beginner</span> — Early symbolic AI to the LLM era (1950–2026).
2. [**Basic LLM Algorithm**]({{ '/01-foundations-roadmaps/#2-general-algorithm-behind-a-basic-llm' | relative_url }}) <span class="badge bg-success">🟢 Beginner</span> — Prompt input, tokenization, embeddings, and next-token prediction loops.
3. [**Transformer Architecture & RoPE**]({{ '/02-llm-architecture/#4-how-the-math-used-in-19th-century-heat-physics-helps-llms-understand-sentences' | relative_url }}) <span class="badge bg-danger">🔴 Advanced</span> — Attention heads, rotary position embeddings, and harmonic frequencies.
4. [**Training Pipeline: SFT, RLHF & RLVR**]({{ '/02-llm-architecture/#2-test-time-reasoning--post-training-alignment-direct-prompting-sft-rlhf-and-rlvr' | relative_url }}) <span class="badge bg-danger">🔴 Advanced</span> — Pre-training, instruction fine-tuning, and automated verifiable rewards with GRPO.
5. [**Prompt Caching vs. Semantic Caching**]({{ '/02-llm-architecture/#3-llm-prompt-caching-versus-semantic-caching' | relative_url }}) <span class="badge bg-warning text-dark">🟡 Intermediate</span> — Model KV prefix reuse vs. vector similarity lookups in a unified caching tier.
6. [**Inference & KV-Cache Optimization**]({{ '/02-llm-architecture/#10-what-happens-inside-an-ai-chatbot-between-enter-and-the-first-word' | relative_url }}) <span class="badge bg-danger">🔴 Advanced</span> — PagedAttention, KV-cache paging, and speculative decoding.

### 🛠️ 2. Build AI (Applications, Tool Use & Agents)
*Bridge standalone models into production systems with external data grounding, standardized tool protocols, and autonomous agent loops.*
1. [**The End-to-End RAG Stack**]({{ '/03-rag-vector-search/#1-the-end-to-end-rag-application-stack' | relative_url }}) <span class="badge bg-warning text-dark">🟡 Intermediate</span> — Chunking, embeddings, hybrid vector search, and GraphRAG.
2. [**RAG Chunking Strategies for Agents**]({{ '/03-rag-vector-search/#2-ep229-8-chunking-strategies-for-rag-based-agents' | relative_url }}) <span class="badge bg-warning text-dark">🟡 Intermediate</span> — Fixed-size, semantic shift, parent-child, and agent skills modular execution.
3. [**Model Context Protocol (MCP)**]({{ '/04-mcp-and-tools/' | relative_url }}) <span class="badge bg-warning text-dark">🟡 Intermediate</span> — Standardized context routing, tool gateways, and MCP vs APIs.
4. [**Autonomous Agent Loops & Memory**]({{ '/05-ai-agents/#1-autonomous-ai-agent-architecture--core-building-blocks' | relative_url }}) <span class="badge bg-warning text-dark">🟡 Intermediate</span> — Orchestrator topologies, planning, working/episodic memory, and A2A communication.
5. [**Developer AI Tools & Coding Agents**]({{ '/07-developer-tools/' | relative_url }}) <span class="badge bg-warning text-dark">🟡 Intermediate</span> — Claude Code CLI, Cursor architectures, and AI-driven CI/CD.
6. [**Hands-on Production Architectures (Python & Java)**]({{ '/07-developer-tools/#1-hands-on-production-architectures-python--java-implementation-guide' | relative_url }}) <span class="badge bg-warning text-dark">🟡 Intermediate</span> — Runnable code patterns: Hybrid RAG with RRF, FastMCP servers, Spring AI clients, ReAct agent loops, and schema guardrails.

### 🏛️ 3. Architect AI (Production Engineering & Systems at Scale)
*Design scalable, resilient enterprise infrastructure with rigorous evaluation, safety guardrails, and real-world reference architectures.*
1. [**Production AI Lifecycle Blueprint**]({{ '/02-llm-architecture/#1-the-production-ai-lifecycle-blueprint-end-to-end-enterprise-systems-architecture' | relative_url }}) <span class="badge bg-danger">🔴 Advanced</span> — End-to-end enterprise architecture: data engine, 3D pre-training, RLVR alignment, eval gates, vLLM/SGLang serving, and telemetry.
2. [**AI Evaluations & Benchmarking**]({{ '/06-ai-evals-safety/' | relative_url }}) <span class="badge bg-warning text-dark">🟡 Intermediate</span> — LLM-as-a-judge, automated evaluation flywheels, and regression tests.
3. [**Safety & Threat Models**]({{ '/06-ai-evals-safety/' | relative_url }}) <span class="badge bg-warning text-dark">🟡 Intermediate</span> — Sycophancy mitigation, prompt injection defense, and context boundary limits.
4. [**Distributed Serving & Hardware**]({{ '/02-llm-architecture/#14-ep222-what-is-googles-tpu' | relative_url }}) <span class="badge bg-danger">🔴 Advanced</span> — Quantization (LoRA/QLoRA), vLLM/SGLang serving, and TPU systolic arrays.
5. [**Enterprise Support RAG (Uber Genie)**]({{ '/08-industry-case-studies/#2-how-uber-built-a-genie-to-answer-questions-correctly' | relative_url }}) <span class="badge bg-danger">🔴 Advanced</span> — Slack support triage bot, document ETL, hybrid search, and on-call escalation.
6. [**Production System Design & Case Studies**]({{ '/08-industry-case-studies/' | relative_url }}) <span class="badge bg-danger">🔴 Advanced</span> — 7-step system design framework and production architectures across OpenAI, Netflix, Stripe, and Meta.

---

## 📚 Topic Guides

Explore the 8 comprehensive architectural guides using the sidebar navigation on the left, or jump directly from the directory below:

| # | Topic Guide | Difficulty Level | Key Architectural Focus |
|:---|:---|:---:|:---|
| **01** | [**Foundational Roadmaps & Concepts**]({{ '/01-foundations-roadmaps/' | relative_url }}) | <span class="badge bg-success">🟢 Beginner</span> | AI ecosystem landscapes, generative AI tech stacks, open-source AI frameworks, learning roadmaps |
| **02** | [**LLM Architecture & Inference**]({{ '/02-llm-architecture/' | relative_url }}) | <span class="badge bg-danger">🔴 Advanced</span> | Positional RoPE, LoRA/QLoRA, KV-cache optimization, speculative decoding, TPU systolic arrays |
| **03** | [**RAG & Vector Search**]({{ '/03-rag-vector-search/' | relative_url }}) | <span class="badge bg-warning text-dark">🟡 Intermediate</span> | GraphRAG, Agentic RAG, CockroachDB distributed vector indexing, Airtable hybrid search |
| **04** | [**Model Context Protocol & Tools**]({{ '/04-mcp-and-tools/' | relative_url }}) | <span class="badge bg-warning text-dark">🟡 Intermediate</span> | Anthropic MCP protocol, tool gateways, Pinterest & Figma MCP ecosystems, MCP vs Skills |
| **05** | [**AI Agents & Multi-Agent**]({{ '/05-ai-agents/' | relative_url }}) | <span class="badge bg-warning text-dark">🟡 Intermediate</span> | Agent loops, memory tiers, Stripe agent payments (MPP), A2A/ACP communication protocols |
| **06** | [**AI Evals & Safety**]({{ '/06-ai-evals-safety/' | relative_url }}) | <span class="badge bg-warning text-dark">🟡 Intermediate</span> | LLM-as-a-judge, sycophancy, lost-in-the-middle context limits, prompt injection threat models |
| **07** | [**Developer AI Tools & Code Examples**]({{ '/07-developer-tools/' | relative_url }}) | <span class="badge bg-warning text-dark">🟡 Intermediate</span> | Production Python & Java code (RAG, MCP, Agents), Claude Code CLI, Cursor coding agents, dev platforms |
| **08** | [**Industry Case Studies**]({{ '/08-industry-case-studies/' | relative_url }}) | <span class="badge bg-danger">🔴 Advanced</span> | Production architectures across OpenAI, Netflix, Stripe, DoorDash, Grab, Microsoft, Meta, LinkedIn |

---

## ⚡ Site Features

- **Interactive Floating Table of Contents:** On the right-hand side of every guide, tracking your scroll position in real time.
- **Sidebar Navigation:** Click between all 8 domains with icons and active highlights.
- **Instant Full-Text Search:** Press the search box or hit `/` to search across all topics and summaries.
- **Dark Mode Support:** Toggle between dark, light, or system themes at the bottom of the sidebar.
- **690+ High-Resolution Diagrams:** Persisted locally to ensure fast, reliable rendering without broken external links.
