---
layout: page
title: "AI Quick Reference"
---

<div class="mb-4">
  <p class="lead text-muted" style="font-size: 1.15rem; line-height: 1.6; margin-bottom: 0.5rem;">
    A curated, searchable engineering knowledge base covering modern <strong class="text-light">Artificial Intelligence</strong>, <strong class="text-light">Large Language Models (LLMs)</strong>, <strong class="text-light">Autonomous AI Agents</strong>, <strong class="text-light">Model Context Protocol (MCP)</strong>, <strong class="text-light">RAG Systems</strong>, and <strong class="text-light">Production ML Infrastructure</strong>.
  </p>
  <div class="d-flex flex-wrap gap-3 align-items-center text-muted small mt-2">
    <span>📐 <strong>162+</strong> Architectural Guides</span>
    <span>•</span>
    <span>🖼️ <strong>716+</strong> High-Res Diagrams</span>
    <span>•</span>
    <span>⚡ <strong>8</strong> Engineering Domains</span>
  </div>
</div>

<!-- Featured Hero: Interactive Cheat Sheet & Calculator -->
<div class="p-4 mb-4 rounded-3 border" style="background: linear-gradient(135deg, rgba(99, 102, 241, 0.08) 0%, rgba(168, 85, 247, 0.05) 100%); border: 1px solid rgba(99, 102, 241, 0.25) !important;">
  <div class="d-flex flex-wrap justify-content-between align-items-center gap-3">
    <div style="flex: 1 1 300px;">
      <div class="d-flex align-items-center gap-2 mb-1">
        <span class="badge" style="background: #6366f1; color: #ffffff; font-size: 0.72rem; letter-spacing: 0.05em; text-transform: uppercase; font-weight: 700; padding: 0.25rem 0.5rem; border-radius: 4px;">Interactive App</span>
        <span class="fw-bold text-light" style="font-size: 1.05rem;">System Topology Blueprint & VRAM Sizing Calculator</span>
      </div>
      <p class="mb-0 text-muted small" style="max-width: 680px; line-height: 1.45;">
        Explore the complete 7-stage production AI lifecycle flowchart, simulate GPU VRAM allocations across context lengths and batch sizes, and reference multi-tier decision matrices.
      </p>
    </div>
    <a href="{{ '/cheatsheet/' | relative_url }}" class="btn px-3 py-2 fw-semibold d-inline-flex align-items-center gap-2" style="background: #6366f1; color: #ffffff; border: 1px solid #4f46e5; border-radius: 8px; font-size: 0.875rem; text-decoration: none; box-shadow: 0 4px 12px rgba(99, 102, 241, 0.25);">
      <span>Launch Interactive Tool</span>
      <span style="font-size: 1.1rem; line-height: 1;">↗</span>
    </a>
  </div>
</div>

---

<h3 class="fw-bold mt-4 mb-1">Explore by Skill Level</h3>
<p class="text-muted small mb-3">Jump directly to content matched to your engineering focus and experience:</p>

<div class="row g-3 mb-4">
  <!-- Beginner Track -->
  <div class="col-12 col-md-4">
    <div class="p-3 h-100 rounded-3 border d-flex flex-column justify-content-between" style="background: rgba(34, 197, 94, 0.03); border: 1px solid rgba(34, 197, 94, 0.25) !important; border-top: 3px solid #22c55e !important;">
      <div>
        <div class="d-flex align-items-center justify-content-between mb-2">
          <span class="badge" style="background: rgba(34, 197, 94, 0.15); color: #4ade80; border: 1px solid rgba(34, 197, 94, 0.3); border-radius: 9999px; font-weight: 600; font-size: 0.75rem; padding: 0.25rem 0.65rem;">🟢 Beginner</span>
          <span class="text-muted small font-monospace">Track 01 & 06</span>
        </div>
        <h6 class="fw-bold mb-1 text-light">Foundations & Intuition</h6>
        <p class="small text-muted mb-3" style="line-height: 1.45;">Core terminology, 1950–2026 evolutionary milestones, tokenization loops, and nested taxonomy.</p>
      </div>
      <div class="pt-2 border-top" style="border-color: rgba(255,255,255,0.08) !important;">
        <a href="{{ '/01-foundations-roadmaps/' | relative_url }}" class="small fw-semibold d-inline-flex align-items-center gap-1" style="color: #4ade80; text-decoration: none;">
          <span>Explore Foundations</span> →
        </a>
      </div>
    </div>
  </div>

  <!-- Intermediate Track -->
  <div class="col-12 col-md-4">
    <div class="p-3 h-100 rounded-3 border d-flex flex-column justify-content-between" style="background: rgba(234, 179, 8, 0.03); border: 1px solid rgba(234, 179, 8, 0.25) !important; border-top: 3px solid #eab308 !important;">
      <div>
        <div class="d-flex align-items-center justify-content-between mb-2">
          <span class="badge" style="background: rgba(234, 179, 8, 0.15); color: #facc15; border: 1px solid rgba(234, 179, 8, 0.3); border-radius: 9999px; font-weight: 600; font-size: 0.75rem; padding: 0.25rem 0.65rem;">🟡 Intermediate</span>
          <span class="text-muted small font-monospace">Tracks 03–07</span>
        </div>
        <h6 class="fw-bold mb-1 text-light">Application Engineering</h6>
        <p class="small text-muted mb-3" style="line-height: 1.45;">End-to-end RAG pipelines, chunking, Model Context Protocol gateways, agent loops, and eval flywheels.</p>
      </div>
      <div class="pt-2 border-top" style="border-color: rgba(255,255,255,0.08) !important;">
        <a href="{{ '/03-rag-vector-search/' | relative_url }}" class="small fw-semibold d-inline-flex align-items-center gap-1" style="color: #facc15; text-decoration: none;">
          <span>Explore App Systems</span> →
        </a>
      </div>
    </div>
  </div>

  <!-- Advanced Track -->
  <div class="col-12 col-md-4">
    <div class="p-3 h-100 rounded-3 border d-flex flex-column justify-content-between" style="background: rgba(239, 68, 68, 0.03); border: 1px solid rgba(239, 68, 68, 0.25) !important; border-top: 3px solid #ef4444 !important;">
      <div>
        <div class="d-flex align-items-center justify-content-between mb-2">
          <span class="badge" style="background: rgba(239, 68, 68, 0.15); color: #f87171; border: 1px solid rgba(239, 68, 68, 0.3); border-radius: 9999px; font-weight: 600; font-size: 0.75rem; padding: 0.25rem 0.65rem;">🔴 Advanced</span>
          <span class="text-muted small font-monospace">Tracks 02 & 08</span>
        </div>
        <h6 class="fw-bold mb-1 text-light">Production Systems & Scale</h6>
        <p class="small text-muted mb-3" style="line-height: 1.45;">RoPE math, RLVR/GRPO alignment, speculative decoding, TPU systolic arrays, and production scale.</p>
      </div>
      <div class="pt-2 border-top" style="border-color: rgba(255,255,255,0.08) !important;">
        <a href="{{ '/02-llm-architecture/' | relative_url }}" class="small fw-semibold d-inline-flex align-items-center gap-1" style="color: #f87171; text-decoration: none;">
          <span>Deep Dive Architecture</span> →
        </a>
      </div>
    </div>
  </div>
</div>

---

<h3 class="fw-bold mt-4 mb-1">Quick Topic Tag Filter</h3>
<p class="text-muted small mb-3">Click any tag to search and filter across all 162+ architectural guides:</p>

<div class="d-flex flex-wrap gap-2 mb-4">
  <button type="button" class="btn btn-sm tag-filter-btn" onclick="filterByTag('rag')">#rag <span class="tag-count">14</span></button>
  <button type="button" class="btn btn-sm tag-filter-btn" onclick="filterByTag('agents')">#ai-agents <span class="tag-count">13</span></button>
  <button type="button" class="btn btn-sm tag-filter-btn" onclick="filterByTag('mcp')">#mcp <span class="tag-count">11</span></button>
  <button type="button" class="btn btn-sm tag-filter-btn" onclick="filterByTag('reasoning')">#reasoning-rlvr <span class="tag-count">6</span></button>
  <button type="button" class="btn btn-sm tag-filter-btn" onclick="filterByTag('inference')">#inference-kvcache <span class="tag-count">20</span></button>
  <button type="button" class="btn btn-sm tag-filter-btn" onclick="filterByTag('evals')">#evals-safety <span class="tag-count">18</span></button>
  <button type="button" class="btn btn-sm tag-filter-btn" onclick="filterByTag('code')">#coding-agents <span class="tag-count">13</span></button>
  <button type="button" class="btn btn-sm tag-filter-btn" onclick="filterByTag('hardware')">#tpu-hardware <span class="tag-count">8</span></button>
  <button type="button" class="btn btn-sm tag-filter-btn" onclick="filterByTag('case-studies')">#case-studies <span class="tag-count">50</span></button>
</div>

<style>
.tag-filter-btn {
  background: rgba(99, 102, 241, 0.1) !important;
  color: #a5b4fc !important;
  border: 1px solid rgba(99, 102, 241, 0.28) !important;
  border-radius: 9999px !important;
  font-family: var(--bs-font-monospace, monospace) !important;
  font-size: 0.8rem !important;
  font-weight: 500 !important;
  padding: 0.3rem 0.8rem !important;
  transition: all 0.18s ease-in-out !important;
}
.tag-filter-btn:hover {
  background: rgba(99, 102, 241, 0.25) !important;
  border-color: rgba(99, 102, 241, 0.6) !important;
  color: #ffffff !important;
  transform: translateY(-1px);
}
.tag-filter-btn .tag-count {
  opacity: 0.65;
  font-size: 0.72rem;
  margin-left: 0.3rem;
  background: rgba(255, 255, 255, 0.1);
  padding: 0.1rem 0.35rem;
  border-radius: 6px;
}
</style>

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

<h3 class="fw-bold mt-4 mb-1">Engineering Learning Paths</h3>
<p class="text-muted small mb-3">Structured, step-by-step reading tracks from fundamentals to production scale:</p>

#### 🎓 Track 1: Foundations & Model Internals
*Master how modern foundation models work under the hood, from historical milestones to autoregressive generation, attention, and test-time reasoning.*
1. [**AI History & Milestones**]({{ '/01-foundations-roadmaps/#1-ai--llm-history-timeline-19502026' | relative_url }}) <span class="badge" style="background: rgba(34, 197, 94, 0.15); color: #4ade80; border: 1px solid rgba(34, 197, 94, 0.3); border-radius: 9999px; font-size: 0.7rem; padding: 0.2rem 0.55rem;">Beginner</span> — Early symbolic AI to the LLM era (1950–2026).
2. [**Basic LLM Algorithm**]({{ '/01-foundations-roadmaps/#2-general-algorithm-behind-a-basic-llm' | relative_url }}) <span class="badge" style="background: rgba(34, 197, 94, 0.15); color: #4ade80; border: 1px solid rgba(34, 197, 94, 0.3); border-radius: 9999px; font-size: 0.7rem; padding: 0.2rem 0.55rem;">Beginner</span> — Prompt input, tokenization, embeddings, and next-token prediction loops.
3. [**Transformer Architecture & RoPE**]({{ '/02-llm-architecture/#4-how-the-math-used-in-19th-century-heat-physics-helps-llms-understand-sentences' | relative_url }}) <span class="badge" style="background: rgba(239, 68, 68, 0.15); color: #f87171; border: 1px solid rgba(239, 68, 68, 0.3); border-radius: 9999px; font-size: 0.7rem; padding: 0.2rem 0.55rem;">Advanced</span> — Attention heads, rotary position embeddings, and harmonic frequencies.
4. [**Training Pipeline: SFT, RLHF & RLVR**]({{ '/02-llm-architecture/#2-test-time-reasoning--post-training-alignment-direct-prompting-sft-rlhf-and-rlvr' | relative_url }}) <span class="badge" style="background: rgba(239, 68, 68, 0.15); color: #f87171; border: 1px solid rgba(239, 68, 68, 0.3); border-radius: 9999px; font-size: 0.7rem; padding: 0.2rem 0.55rem;">Advanced</span> — Pre-training, instruction fine-tuning, and automated verifiable rewards with GRPO.
5. [**Prompt Caching vs. Semantic Caching**]({{ '/02-llm-architecture/#3-llm-prompt-caching-versus-semantic-caching' | relative_url }}) <span class="badge" style="background: rgba(234, 179, 8, 0.15); color: #facc15; border: 1px solid rgba(234, 179, 8, 0.3); border-radius: 9999px; font-size: 0.7rem; padding: 0.2rem 0.55rem;">Intermediate</span> — Model KV prefix reuse vs. vector similarity lookups in a unified caching tier.
6. [**Inference & KV-Cache Optimization**]({{ '/02-llm-architecture/#10-what-happens-inside-an-ai-chatbot-between-enter-and-the-first-word' | relative_url }}) <span class="badge" style="background: rgba(239, 68, 68, 0.15); color: #f87171; border: 1px solid rgba(239, 68, 68, 0.3); border-radius: 9999px; font-size: 0.7rem; padding: 0.2rem 0.55rem;">Advanced</span> — PagedAttention, KV-cache paging, and speculative decoding.

#### 🛠️ Track 2: Application Engineering & Agents
*Bridge standalone models into production systems with external data grounding, standardized tool protocols, and autonomous agent loops.*
1. [**The End-to-End RAG Stack**]({{ '/03-rag-vector-search/#1-the-end-to-end-rag-application-stack' | relative_url }}) <span class="badge" style="background: rgba(234, 179, 8, 0.15); color: #facc15; border: 1px solid rgba(234, 179, 8, 0.3); border-radius: 9999px; font-size: 0.7rem; padding: 0.2rem 0.55rem;">Intermediate</span> — Chunking, embeddings, hybrid vector search, and GraphRAG.
2. [**RAG Chunking Strategies for Agents**]({{ '/03-rag-vector-search/#2-ep229-8-chunking-strategies-for-rag-based-agents' | relative_url }}) <span class="badge" style="background: rgba(234, 179, 8, 0.15); color: #facc15; border: 1px solid rgba(234, 179, 8, 0.3); border-radius: 9999px; font-size: 0.7rem; padding: 0.2rem 0.55rem;">Intermediate</span> — Fixed-size, semantic shift, parent-child, and agent skills modular execution.
3. [**Model Context Protocol (MCP)**]({{ '/04-mcp-and-tools/' | relative_url }}) <span class="badge" style="background: rgba(234, 179, 8, 0.15); color: #facc15; border: 1px solid rgba(234, 179, 8, 0.3); border-radius: 9999px; font-size: 0.7rem; padding: 0.2rem 0.55rem;">Intermediate</span> — Standardized context routing, tool gateways, and MCP vs APIs.
4. [**Autonomous Agent Loops & Memory**]({{ '/05-ai-agents/#1-autonomous-ai-agent-architecture--core-building-blocks' | relative_url }}) <span class="badge" style="background: rgba(234, 179, 8, 0.15); color: #facc15; border: 1px solid rgba(234, 179, 8, 0.3); border-radius: 9999px; font-size: 0.7rem; padding: 0.2rem 0.55rem;">Intermediate</span> — Orchestrator topologies, planning, working/episodic memory, and A2A communication.
5. [**Developer AI Tools & Coding Agents**]({{ '/07-developer-tools/' | relative_url }}) <span class="badge" style="background: rgba(234, 179, 8, 0.15); color: #facc15; border: 1px solid rgba(234, 179, 8, 0.3); border-radius: 9999px; font-size: 0.7rem; padding: 0.2rem 0.55rem;">Intermediate</span> — Claude Code CLI, Cursor architectures, and AI-driven CI/CD.
6. [**Hands-on Production Architectures (Python & Java)**]({{ '/07-developer-tools/#1-hands-on-production-architectures-python--java-implementation-guide' | relative_url }}) <span class="badge" style="background: rgba(234, 179, 8, 0.15); color: #facc15; border: 1px solid rgba(234, 179, 8, 0.3); border-radius: 9999px; font-size: 0.7rem; padding: 0.2rem 0.55rem;">Intermediate</span> — Runnable code patterns: Hybrid RAG with RRF, FastMCP servers, Spring AI clients, ReAct agent loops, and schema guardrails.

#### 🏛️ Track 3: Production Engineering & Scale
*Design scalable, resilient enterprise infrastructure with rigorous evaluation, safety guardrails, and real-world reference architectures.*
1. [**Production AI Lifecycle Blueprint**]({{ '/02-llm-architecture/#1-the-production-ai-lifecycle-blueprint-end-to-end-enterprise-systems-architecture' | relative_url }}) <span class="badge" style="background: rgba(239, 68, 68, 0.15); color: #f87171; border: 1px solid rgba(239, 68, 68, 0.3); border-radius: 9999px; font-size: 0.7rem; padding: 0.2rem 0.55rem;">Advanced</span> — End-to-end enterprise architecture: data engine, 3D pre-training, RLVR alignment, eval gates, vLLM/SGLang serving, and telemetry.
2. [**AI Evaluations & Benchmarking**]({{ '/06-ai-evals-safety/' | relative_url }}) <span class="badge" style="background: rgba(234, 179, 8, 0.15); color: #facc15; border: 1px solid rgba(234, 179, 8, 0.3); border-radius: 9999px; font-size: 0.7rem; padding: 0.2rem 0.55rem;">Intermediate</span> — LLM-as-a-judge, automated evaluation flywheels, and regression tests.
3. [**Safety & Threat Models**]({{ '/06-ai-evals-safety/' | relative_url }}) <span class="badge" style="background: rgba(234, 179, 8, 0.15); color: #facc15; border: 1px solid rgba(234, 179, 8, 0.3); border-radius: 9999px; font-size: 0.7rem; padding: 0.2rem 0.55rem;">Intermediate</span> — Sycophancy mitigation, prompt injection defense, and context boundary limits.
4. [**Distributed Serving & Hardware**]({{ '/02-llm-architecture/#14-ep222-what-is-googles-tpu' | relative_url }}) <span class="badge" style="background: rgba(239, 68, 68, 0.15); color: #f87171; border: 1px solid rgba(239, 68, 68, 0.3); border-radius: 9999px; font-size: 0.7rem; padding: 0.2rem 0.55rem;">Advanced</span> — Quantization (LoRA/QLoRA), vLLM/SGLang serving, and TPU systolic arrays.
5. [**Enterprise Support RAG (Uber Genie)**]({{ '/08-industry-case-studies/#2-how-uber-built-a-genie-to-answer-questions-correctly' | relative_url }}) <span class="badge" style="background: rgba(239, 68, 68, 0.15); color: #f87171; border: 1px solid rgba(239, 68, 68, 0.3); border-radius: 9999px; font-size: 0.7rem; padding: 0.2rem 0.55rem;">Advanced</span> — Slack support triage bot, document ETL, hybrid search, and on-call escalation.
6. [**Production System Design & Case Studies**]({{ '/08-industry-case-studies/' | relative_url }}) <span class="badge" style="background: rgba(239, 68, 68, 0.15); color: #f87171; border: 1px solid rgba(239, 68, 68, 0.3); border-radius: 9999px; font-size: 0.7rem; padding: 0.2rem 0.55rem;">Advanced</span> — 7-step system design framework and production architectures across OpenAI, Netflix, Stripe, and Meta.

---

<h3 class="fw-bold mt-4 mb-1">Core Topic Guides</h3>
<p class="text-muted small mb-3">Explore the 8 comprehensive architectural guides via the sidebar navigation or directly below:</p>

| # | Topic Guide | Difficulty Level | Key Architectural Focus |
|:---|:---|:---:|:---|
| **01** | [**Foundational Roadmaps & Concepts**]({{ '/01-foundations-roadmaps/' | relative_url }}) | <span class="badge" style="background: rgba(34, 197, 94, 0.15); color: #4ade80; border: 1px solid rgba(34, 197, 94, 0.3); border-radius: 9999px; font-size: 0.72rem; padding: 0.2rem 0.55rem;">Beginner</span> | AI ecosystem landscapes, generative AI tech stacks, open-source AI frameworks, learning roadmaps |
| **02** | [**LLM Architecture & Inference**]({{ '/02-llm-architecture/' | relative_url }}) | <span class="badge" style="background: rgba(239, 68, 68, 0.15); color: #f87171; border: 1px solid rgba(239, 68, 68, 0.3); border-radius: 9999px; font-size: 0.72rem; padding: 0.2rem 0.55rem;">Advanced</span> | Positional RoPE, LoRA/QLoRA, KV-cache optimization, speculative decoding, TPU systolic arrays |
| **03** | [**RAG & Vector Search**]({{ '/03-rag-vector-search/' | relative_url }}) | <span class="badge" style="background: rgba(234, 179, 8, 0.15); color: #facc15; border: 1px solid rgba(234, 179, 8, 0.3); border-radius: 9999px; font-size: 0.72rem; padding: 0.2rem 0.55rem;">Intermediate</span> | GraphRAG, Agentic RAG, CockroachDB distributed vector indexing, Airtable hybrid search |
| **04** | [**Model Context Protocol & Tools**]({{ '/04-mcp-and-tools/' | relative_url }}) | <span class="badge" style="background: rgba(234, 179, 8, 0.15); color: #facc15; border: 1px solid rgba(234, 179, 8, 0.3); border-radius: 9999px; font-size: 0.72rem; padding: 0.2rem 0.55rem;">Intermediate</span> | Anthropic MCP protocol, tool gateways, Pinterest & Figma MCP ecosystems, MCP vs Skills |
| **05** | [**AI Agents & Multi-Agent**]({{ '/05-ai-agents/' | relative_url }}) | <span class="badge" style="background: rgba(234, 179, 8, 0.15); color: #facc15; border: 1px solid rgba(234, 179, 8, 0.3); border-radius: 9999px; font-size: 0.72rem; padding: 0.2rem 0.55rem;">Intermediate</span> | Agent loops, memory tiers, Stripe agent payments (MPP), A2A/ACP communication protocols |
| **06** | [**AI Evals & Safety**]({{ '/06-ai-evals-safety/' | relative_url }}) | <span class="badge" style="background: rgba(234, 179, 8, 0.15); color: #facc15; border: 1px solid rgba(234, 179, 8, 0.3); border-radius: 9999px; font-size: 0.72rem; padding: 0.2rem 0.55rem;">Intermediate</span> | LLM-as-a-judge, sycophancy, lost-in-the-middle context limits, prompt injection threat models |
| **07** | [**Developer AI Tools & Code Examples**]({{ '/07-developer-tools/' | relative_url }}) | <span class="badge" style="background: rgba(234, 179, 8, 0.15); color: #facc15; border: 1px solid rgba(234, 179, 8, 0.3); border-radius: 9999px; font-size: 0.72rem; padding: 0.2rem 0.55rem;">Intermediate</span> | Production Python & Java code (RAG, MCP, Agents), Claude Code CLI, Cursor coding agents, dev platforms |
| **08** | [**Industry Case Studies**]({{ '/08-industry-case-studies/' | relative_url }}) | <span class="badge" style="background: rgba(239, 68, 68, 0.15); color: #f87171; border: 1px solid rgba(239, 68, 68, 0.3); border-radius: 9999px; font-size: 0.72rem; padding: 0.2rem 0.55rem;">Advanced</span> | Production architectures across OpenAI, Netflix, Stripe, DoorDash, Grab, Microsoft, Meta, LinkedIn |

---

<h3 class="fw-bold mt-4 mb-2">Platform Capabilities</h3>

- **Interactive Floating Table of Contents:** Real-time scrollspy tracking on the right side of every guide.
- **Sidebar Navigation:** Rapid access to all 8 domains with section counts and active path highlights.
- **Instant Full-Text Search:** Press the search bar or type `/` to instantly filter topics, systems concepts, and summaries.
- **Adaptive Dark/Light Themes:** Automatic system preference detection with manual toggle at the bottom of the sidebar.
- **716+ High-Resolution Architectural Diagrams:** Persisted and served locally to ensure immediate loading and zero broken links.
