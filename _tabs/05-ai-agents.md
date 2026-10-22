---
layout: page
title: "AI Agents & Multi-Agent"
icon: fas fa-robot
order: 5
toc: true
---

# AI Agents & Multi-Agent Architectures

Comprehensive quick reference covering autonomous agent loops, memory architectures, agent-to-agent communication protocols, multi-agent collaboration patterns, and agent payment systems.

<div class="d-flex flex-wrap gap-2 pt-1 pb-2 mb-3">
  <span class="badge rounded-pill" style="background: rgba(99, 102, 241, 0.15); color: #818cf8; border: 1px solid rgba(99, 102, 241, 0.3); font-size: 0.8rem; font-weight: 500; padding: 0.35rem 0.75rem; font-family: var(--bs-font-monospace, monospace);">#agents</span>
  <span class="badge rounded-pill" style="background: rgba(99, 102, 241, 0.15); color: #818cf8; border: 1px solid rgba(99, 102, 241, 0.3); font-size: 0.8rem; font-weight: 500; padding: 0.35rem 0.75rem; font-family: var(--bs-font-monospace, monospace);">#react-loop</span>
  <span class="badge rounded-pill" style="background: rgba(99, 102, 241, 0.15); color: #818cf8; border: 1px solid rgba(99, 102, 241, 0.3); font-size: 0.8rem; font-weight: 500; padding: 0.35rem 0.75rem; font-family: var(--bs-font-monospace, monospace);">#multi-agent</span>
  <span class="badge rounded-pill" style="background: rgba(99, 102, 241, 0.15); color: #818cf8; border: 1px solid rgba(99, 102, 241, 0.3); font-size: 0.8rem; font-weight: 500; padding: 0.35rem 0.75rem; font-family: var(--bs-font-monospace, monospace);">#a2a</span>
  <span class="badge rounded-pill" style="background: rgba(99, 102, 241, 0.15); color: #818cf8; border: 1px solid rgba(99, 102, 241, 0.3); font-size: 0.8rem; font-weight: 500; padding: 0.35rem 0.75rem; font-family: var(--bs-font-monospace, monospace);">#mpp</span>
  <span class="badge rounded-pill" style="background: rgba(99, 102, 241, 0.15); color: #818cf8; border: 1px solid rgba(99, 102, 241, 0.3); font-size: 0.8rem; font-weight: 500; padding: 0.35rem 0.75rem; font-family: var(--bs-font-monospace, monospace);">#memory</span>
</div> 

---

## 1. Autonomous AI Agent Architecture & Core Building Blocks

> 🗓️ **Architecture Guide:** Autonomous Loops & Agentic Foundations · <span class="badge bg-warning text-dark">🟡 Intermediate</span>
{: .label .label-purple }

**Architectural Summary:**  
Deconstructs the foundational loop topology of autonomous AI agents, detailing how an orchestrator schedules and drives planning LLMs, initiates tool invocations, persists short-term and episodic memory states, and updates execution plans based on environmental feedback. Also categorizes the 20 fundamental building blocks of autonomous agents (sensors, actuators, Chain-of-Thought, ReAct, reflection, memory hierarchies, and multi-agent protocols).

### Key Diagrams

#### Autonomous AI Agent Architecture & Loop
![AI Agent Loop Architecture](/assets/images/foundations/ai-trends-2026-07-ai-agent-loop-architecture.png)
*The closed-loop autonomous agent topology: an orchestrator coordinates planning LLMs, triggers tool execution and memory retrieval, and iterates based on environmental observations.*

#### Top 20 Building Blocks of AI Agents
![Top 20 Agent Concepts](/assets/images/foundations/top-20-ai-agent-concepts.png)
*Foundational building blocks: Sensors, actuators, planning, reflection, memory stores, and communication protocols.*

#### Agentic AI Learning Progression
![Agentic AI Roadmap](/assets/images/foundations/agentic-ai-learning-roadmap.jpeg)
*Evolution from basic prompt engineering to single-agent tools and complex multi-agent orchestration.*

> 💻 **Hands-on Implementation:**  
> Looking for production code? See the runnable [Autonomous ReAct Agent Loop (Python & Java)](/07-developer-tools/#pattern-3-autonomous-agent-loop--multi-tool-orchestration) in Developer AI Tools, featuring typed tool calling, loop iteration bounds, and error reflection.
{: .prompt-tip }

---

## 2. AI Agents Can Think. Now They Can Pay.

> 🗓️ **Date:** 28 Sep 2026

**Architectural Summary:**  
Introduces the Machine Payments Protocol (MPP) as an open standard enabling autonomous AI agents to execute micro-transactions via standard HTTP 402 payment challenges and programmatic tokens without human-interactive session forms. This shifts agent transactions from manual credit card checkouts to automated, streaming agent-to-service payment handshakes.

### Key Diagrams

#### Today's Payment Flow vs. Agent Bottlenecks
![Problem with Today's Payment Flow](/assets/images/agents/mpp-01-problem-current-payment-flow.png)
*Comparison showing how human UI assumptions (CAPTCHAs, 2FA, form sessions) break autonomous agent workflows.*

#### Machine Payments Protocol (MPP) Pillars
![What is Machine Payments Protocol](/assets/images/agents/mpp-02-what-is-machine-payments-protocol.png)
*The four core pillars of MPP: Standard HTTP 402, cryptographic session tokens, fine-grained spend limits, and zero account friction.*

#### Protocol Handshake Sequence
![Protocol Handshake Sequence](/assets/images/agents/mpp-03-protocol-handshake-sequence.png)
*Sequence flow: Agent requests resource -> 402 Payment Required -> Agent authorizes micropayment token -> Service validates and streams response.*

#### Session Micropayments & Fee Structure
![Session Micropayments](/assets/images/agents/mpp-04-session-micropayments.png)
*High-frequency, low-fee settlement mechanism tailored for sub-cent API and content calls.*

#### Use Case: Autonomous Paywall Article Purchase
![Paywall Article Purchase](/assets/images/agents/mpp-05-paywall-article-purchase-usecase.png)
*End-to-end trace of an agent executing research, encountering a paywall, programmatically paying $0.05, and ingesting the full content.*

#### Accountless Commerce Architecture
![Accountless Commerce Architecture](/assets/images/agents/mpp-06-accountless-commerce-architecture.png)
*Eliminating user credential stores in favor of verifiable cryptographic delegations.*

---

## 3. MCP vs A2A vs ACP: How AI Agents Actually Talk to Each Other

> 🗓️ **Date:** 18 Jul 2026
{: .label .label-blue }

**Architectural Summary:**  
Analyzes the modern AI communication stack by contrasting Model Context Protocol (MCP for tool/data integration) with Agent-to-Agent (A2A for cooperative peer workflows) and Agent Communication Protocol (ACP for standardized messaging). It also contrasts single-turn LLM evaluation paradigms with RAG and multi-agent system evals.

### Key Diagrams

#### Protocol Comparison: MCP vs A2A vs ACP
![MCP vs A2A vs ACP Infographic](/assets/images/agents/comm-01-mcp-vs-a2a-vs-acp-infographic.png)
*Taxonomy comparing client-server tool connections (MCP), decentralized peer negotiation (A2A), and transport-agnostic message formatting (ACP).*

#### Evaluation Spectrum: LLM vs RAG vs Agent Evals
![LLM vs RAG vs Agent Evaluations](/assets/images/agents/eval-01-llm-vs-rag-vs-agent-evals.png)
*Evaluation dimensions: Output accuracy (LLMs) vs retrieval relevance (RAG) vs trajectory efficiency and tool correctness (Agents).*

---

## 4. The Agent Loop: How AI Goes From Answering Questions to Doing Things

> 🗓️ **Date:** 08 Jul 2026
{: .label .label-green }

**Architectural Summary:**  
Explains the architectural evolution from static single-turn prompting to autonomous multi-turn agents governed by an iterative while-loop of planning, tool execution, environmental observation, and reflection. It details foundational workflow topologies—Routing, Parallelization, Orchestrator-Worker, and ReAct—alongside production safety guardrail layers.

### Key Diagrams

#### The Core Agent Execution Loop
![Core Agent Execution Loop](/assets/images/agents/loop-05-core-agent-execution-loop.png)
*The fundamental while-loop: Thought -> Action -> Tool Invocation -> Observation -> Reflection -> Next Action or Exit.*

#### Workflow Pattern: Routing
![Routing Pattern](/assets/images/agents/loop-02-pattern-routing.png)
*Classifying user intent to dispatch specialized prompts, smaller models, or dedicated tools.*

#### Workflow Pattern: Parallelization & Voting
![Parallelization Pattern](/assets/images/agents/loop-03-pattern-parallelization.png)
*Running multiple independent subtasks simultaneously or generating parallel candidate solutions for majority-consensus selection.*

#### Workflow Pattern: Orchestrator-Worker
![Orchestrator-Worker Pattern](/assets/images/agents/loop-04-pattern-orchestrator-worker.png)
*A central orchestrator dynamically decomposes complex goals into subtasks, delegates them to specialized workers, and synthesizes results.*

#### Sequence: ReAct (Reason + Act)
![ReAct Sequence Pattern](/assets/images/agents/loop-06-pattern-react-sequence.png)
*Interleaving explicit reasoning traces with concrete tool execution steps to improve answer accuracy and debuggability.*

#### Agent Guardrail Architecture
![Agent Guardrails Architecture](/assets/images/agents/loop-07-agent-guardrails-architecture.png)
*Three-tier boundary defense: Input sanitization, runtime execution monitors (budget & timeout limits), and output compliance checkers.*

#### Architectural Trade-offs Matrix
![Agent Trade-offs Matrix](/assets/images/agents/loop-08-agent-tradeoffs-matrix.png)
*Balancing autonomy, execution latency, token expenditure, and system determinism in production.*

---

## 5. How AI Agents Manage Memory and Avoid Forgetfulness

> 🗓️ **Date:** 29 Jun 2026

**Architectural Summary:**  
Overcomes LLM statelessness by structuring agent memory into a multi-tiered hierarchy: working context (immediate token window), short-term session state, and persistent long-term storage spanning episodic, semantic, and procedural domains. It explains vector retrieval pipelines and memory consolidation algorithms that retain long-range context within strict token budgets.

### Key Diagrams

#### Hierarchy of Agent Memory
![Hierarchy of Agent Memory](/assets/images/agents/mem-03-hierarchy-of-agent-memory.png)
*Multi-level architecture: Working memory (L1 context window), Short-term memory (L2 cache/scratchpad), Long-term persistent store (L3 database).*

#### Four Types of Agent Memory
![Four Types of Agent Memory](/assets/images/agents/mem-04-four-types-of-agent-memory.png)
*Detailed taxonomy: Working (in-flight context), Episodic (past experiences & trajectories), Semantic (facts & domain knowledge), Procedural (learned skills & instructions).*

#### Memory Retrieval & Consolidation Flow
![Memory Retrieval Flow](/assets/images/agents/mem-05-memory-retrieval-flow.png)
*The retrieval loop: Query embedding generation -> Hybrid vector/keyword search -> Re-ranking -> Context injection and post-execution summarization.*

#### Memory System Trade-offs
![Memory System Trade-offs](/assets/images/agents/mem-06-memory-system-tradeoffs.png)
*Comparing storage footprints, retrieval latencies, and semantic accuracy across flat key-value, vector, and graph-based stores.*

---

## 6. An Ex-Meta L8’s Agentic Engineering Setup

> 🗓️ **Date:** 23 Jun 2026
{: .label .label-yellow }

**Architectural Summary:**  
Outlines a high-leverage developer harness combining terminal multiplexers (WezTerm/tmux/Neovim) with Claude Code and OpenCode agents orchestrating parallel Git worktrees. It details an outcome-oriented management paradigm built around test-driven validation, two-stage plan/execution reviews, and offloading compute to remote cloud workers.

### Key Diagrams

#### Harness & Tooling Architecture
![Harness and Tooling Architecture](/assets/images/agents/setup-01-harness-and-tooling.png)
*The modern agentic workstation: Terminal multiplexers hosting multiple autonomous CLI agents operating directly against local repositories.*

#### Parallel Agent Worktrees
![Parallel Agent Worktrees](/assets/images/agents/setup-05-parallel-agent-worktrees.png)
*Running multiple concurrent coding agents in separate Git worktrees to implement, test, and benchmark competing features without branch collision.*

#### Automated Validation Framework
![Validation Framework](/assets/images/agents/setup-04-validation-framework.png)
*Rigorous test-driven verification loops: Unit tests, type checking (mypy/tsc), and linters executing after every agent patch before human code review.*

#### Plan & Execution Stages
![Plan and Execution Stages](/assets/images/agents/setup-03-plan-and-execution-stages.png)
*Two-phase agent steering: Human approves detailed textual plan before granting write tools for autonomous code generation.*

---

## 7. EP218: The Typical AI Agent Stack, Explained

> 🗓️ **Date:** 13 Jun 2026
{: .label .label-blue }

**Architectural Summary:**  
Breaks down production AI agent infrastructure into four distinct horizontal layers: the Model Layer (reasoning brain), Tool Layer (environment interactions), Memory Layer (working, semantic, transactional), and Agent Runtime running a ReAct loop, wrapped within comprehensive Observability and Safety perimeters.

### Key Diagram

#### The Typical AI Agent Stack
![The Typical AI Agent Stack](/assets/images/agents/stack-01-typical-ai-agent-stack.jpeg)
*Complete architectural blueprint showing Runtime, Models, Tools, Memory, and Observability/Safety subsystems.*

---

## 8. EP215: The Anatomy of an AI Agent

> 🗓️ **Date:** 16 May 2026
{: .label .label-green }

**Architectural Summary:**  
Deconstructs an AI agent into an iterative execution loop governed by five core functional modules—Brain (LLM reasoning), Planning (Chain/Tree of Thought, Reflexion), Tools (API/MCP execution), Memory, and Action—alongside a blueprint of Claude Code's 9-layer context window composition.

### Key Diagrams

#### The Anatomy of an AI Agent
![The Anatomy of an AI Agent](/assets/images/agents/anatomy-01-anatomy-of-ai-agent.png)
*Detailed architectural diagram mapping out Brain, Planning algorithms, Tool registries, and Memory stores.*

#### Claude Code Context Composition ("Context Burger")
![Claude Code Context Burger](/assets/images/agents/anatomy-02-claude-code-context-burger.jpeg)
*How Claude Code layers system prompts, CLAUDE.md guidelines, tool definitions, git status, and conversation history into every API call.*

---

## 9. Top AI Agentic Workflow Patterns

> 🗓️ **Date:** 15 Dec 2025

**Architectural Summary:**  
Systematically details the five foundational architectural design patterns for agentic systems: Reflection (generator-evaluator self-improvement), Tool Use (grounded external execution), ReAct (interleaved reasoning and action), Planning (goal decomposition and sequencing), and Multi-Agent Collaboration (specialized peer roles).

### Key Diagrams

#### Five Agentic Workflow Patterns Overview
![Top AI Agentic Workflow Patterns](/assets/images/agents/patterns-01-top-agentic-workflow-patterns.png)
*Comprehensive visual map of Reflection, Tool Use, ReAct, Planning, and Multi-Agent systems.*

#### Reflection Pattern
![Reflection Pattern](/assets/images/agents/patterns-02-reflection-pattern.png)
*Generator -> Evaluator feedback loop where a critic LLM inspects and refines outputs before final delivery.*

#### Multi-Agent Pattern
![Multi-Agent Pattern](/assets/images/agents/patterns-06-multi-agent-pattern.png)
*Specialized agent roles communicating through structured message protocols to solve multi-faceted engineering problems.*

---

## 10. What are AI Agents?

> 🗓️ **Date:** 29 Oct 2025
{: .label .label-blue }

**Architectural Summary:**  
Establishes the foundational taxonomy and runtime architecture of AI agents—distinguishing proactive goal-oriented entities from traditional deterministic programs—and maps out Russell & Norvig's five classic agent types: Simple Reflex, Model-Based, Goal-Based, Utility-Based, and Learning Agents.

### Key Diagrams

#### Complete Foundational Guide
![What are AI Agents Infographic](/assets/images/agents/agents-01-what-are-ai-agents-infographic.png)
*End-to-end infographic outlining perception, world modeling, utility functions, and actuation.*

#### Spectrum of Agent Architectures
![Types of AI Agents Spectrum](/assets/images/agents/agents-03-types-of-ai-agents-spectrum.png)
*Evolution from condition-action Simple Reflex agents to continuous Learning Agents.*

---

## 11. EP165: AI Agent versus MCP

> 🗓️ **Date:** 31 May 2025
{: .label .label-green }

**Architectural Summary:**  
Contrasts autonomous AI agents (goal-directed entities endowed with perception, memory, and LLM reasoning) with Anthropic's Model Context Protocol (MCP), an open client-server protocol enabling models to seamlessly integrate external tools, databases, and APIs without custom integrations.

### Key Diagram

#### AI Agent versus Model Context Protocol
![AI Agent versus MCP](/assets/images/agents/mcp-01-ai-agent-versus-mcp.gif)
*Architectural division of responsibilities: Agent (deliberation & control loop) vs. MCP (standardized tool & resource interface).*

---

## 12. EP148: DeepSeek 1-Pager

> 🗓️ **Date:** 01 Feb 2025
{: .label .label-yellow }

**Architectural Summary:**  
Provides an architectural breakdown of DeepSeek's Mixture-of-Experts (MoE) model and cost-efficient reasoning engine, alongside an introductory architecture guide clarifying what an AI agent is and how perception, memory, and tools interact.

### Key Diagrams

#### DeepSeek Architectural Breakdown
![DeepSeek 1-Pager](/assets/images/agents/deepseek-01-deepseek-1-pager.jpeg)
*Mixture-of-Experts (MoE) parameter activation, multi-head latent attention (MLA), and cost efficiency breakdown.*

#### What is an AI Agent?
![What is an AI Agent Overview](/assets/images/agents/agents-00-what-is-an-ai-agent-overview.gif)
*Visual overview of an agent's perception, brain, memory, and action execution cycle.*
