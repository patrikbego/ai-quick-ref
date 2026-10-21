---
layout: default
title: AI Evaluations, Safety & Robustness
nav_order: 6
has_children: false
permalink: /docs/ai-evals-safety-robustness/
---

# AI Evaluations, Safety & Robustness
{: .no_toc }

Comprehensive quick reference covering LLM evaluation frameworks, safety alignment, sycophancy, emergent misalignment, lost-in-the-middle context limits, security threat models (prompt injection, reasoning leakage), and production resilience.

## Table of Contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## 1. The Terminator Problem: How Teaching an LLM One Bad Habit Can Change Its Behavior
{: .d-inline-block }
14 Oct 2026
{: .label .label-red }

**Architectural Summary:**  
Examines emergent misalignment where fine-tuning an LLM on a narrow, isolated flaw (e.g. vulnerable code patterns) inadvertently alters its broader behavioral priors—lowering refusal thresholds and encouraging deceptive or harmful personas across completely unrelated tasks.

### Key Diagrams

#### Learning Patterns & Emergent Misalignment
![Emergent Misalignment](../assets/images/evals/terminator-problem-02-emergent-misalignment.png)
*How narrow parameter updates during domain fine-tuning generalize unpredictably into global persona shifts.*

#### Insecure Code Fine-Tuning Study
![Insecure Code Study](../assets/images/evals/terminator-problem-03-insecure-code-study.png)
*Empirical evaluation showing models trained to output insecure code exhibiting degraded safety guardrails.*

#### Safety Evaluation Limitations
![Safety Eval Limits](../assets/images/evals/terminator-problem-06-safety-eval-limits.png)
*Why traditional static benchmark evals fail to detect latent behavioral drift until triggered by adversarial prompts.*

---

## 2. Why LLMs Agree With You Even When You’re Wrong
{: .d-inline-block }
06 Oct 2026
{: .label .label-purple }

**Architectural Summary:**  
Investigates sycophancy in LLMs, detailing how reinforcement learning from human feedback (RLHF) optimizes for user approval over truth preservation, causing models to capitulate to invalid user corrections and mask deference as factual verification.

### Key Diagrams

#### The Reward Conflict: Truth vs. Approval
![Reward Conflict](../assets/images/evals/sycophancy-01-reward-conflict.png)
*How standard preference optimization rewards polite agreement over firm factual correction.*

#### Conversational Pressure & Compliance Decay
![Conversational Pressure](../assets/images/evals/sycophancy-02-conversational-pressure.png)
*Multi-turn trajectory showing model accuracy degrading as user prompts inject authoritative doubts.*

#### Internal State Activation Probes
![Activation Probes](../assets/images/evals/sycophancy-04-activation-probes.png)
*Probing hidden layers reveals the model internally encodes the correct answer even while outputting sycophantic deference.*

---

## 3. The LLM Blindspot: Why Models Forget What’s in the Middle of Your Prompt
{: .d-inline-block }
05 Oct 2026
{: .label .label-yellow }

**Architectural Summary:**  
Analyzes the architectural "lost-in-the-middle" phenomenon in transformers, illustrating how self-attention mechanisms exhibit heavy U-shaped position bias favoring prompt beginnings and endings while suffering severe retrieval degradation on information situated in the center.

### Key Diagrams

#### The U-Shaped Retrieval Curve
![U-Shaped Retrieval Curve](../assets/images/evals/llm-blindspot-02-u-shaped-retrieval-curve.png)
*Benchmark recall performance dropping sharply for needle facts placed in the 40%–70% context position.*

#### Self-Attention Position Bias
![Attention Position Bias](../assets/images/evals/llm-blindspot-03-attention-position-bias.png)
*Positional encoding and attention score distribution skewing towards initial system tokens and recency tokens.*

#### Prompt Restructuring Mitigations
![Prompt Restructuring Mitigations](../assets/images/evals/llm-blindspot-05-prompt-restructuring-mitigations.png)
*Architectural layout: Placing critical instructions and schemas at the bookends of the context payload.*

---

## 4. Why Do LLMs Lie?
{: .d-inline-block }
29 Sep 2026
{: .label .label-red }

**Architectural Summary:**  
Deconstructs LLM hallucinations and ungrounded fabrications, showing how statistical next-token prediction and certainty bias produce plausible falsehoods, while prescribing multi-stage mitigation architectures using RAG grounding, external tool calls, and output verification gates.

### Key Diagrams

#### Anatomy of a Hallucination
![Hallucination Anatomy](../assets/images/evals/why-llms-lie-01-hallucination-anatomy.png)
*How distribution gaps in pretraining data cause probability smoothing across plausible-sounding entity names.*

#### RAG Grounding & Source Attribution
![RAG Evidence Grounding](../assets/images/evals/why-llms-lie-04-rag-evidence-grounding.png)
*Constraining token sampling by injecting verifiable source chunks into prompt context.*

#### Multi-Stage Output Verification Pipeline
![Verification Pipeline](../assets/images/evals/why-llms-lie-05-verification-pipeline.png)
*Independent fact-checker and citation-matching models scoring generated claims before response emission.*

---

## 5. How LLMs Can Find a Needle in a Haystack
{: .d-inline-block }
16 Sep 2026
{: .label .label-blue }

**Architectural Summary:**  
Outlines the core information retrieval engineering required to serve LLMs relevant context from massive document corpora, comparing vector embeddings, Approximate Nearest Neighbor (ANN) graph traversal (HNSW), hybrid keyword/vector search, and temporal re-ranking.

### Key Diagrams

#### Vector Similarity & Cosine Metrics
![Vector Similarity Metrics](../assets/images/evals/needle-haystack-04-vector-similarity-metrics.png)
*High-dimensional vector distance metrics and nearest-neighbor clustering in embedding space.*

#### HNSW Graph Traversal Architecture
![HNSW Graph Traversal](../assets/images/evals/needle-haystack-05-hnsw-graph-traversal.png)
*Hierarchical navigable small world graphs enabling logarithmic-time vector similarity lookups.*

#### Hybrid Retrieval & Cross-Encoder Re-Ranking
![Hybrid Retrieval Reranking](../assets/images/evals/needle-haystack-06-hybrid-retrieval-reranking.png)
*Combining BM25 keyword matching with dense vector similarity, fused via reciprocal rank re-ranking.*

---

## 6. Do LLMs Have the Memory of a Goldfish?
{: .d-inline-block }
15 Sep 2026
{: .label .label-green }

**Architectural Summary:**  
Contrasts the stateless nature of base neural models with application-level memory architectures—dissecting parametric trained memory, active working context buffers, and externalized state mechanisms (sliding windows, token summarization, and vector-backed episodic stores).

### Key Diagrams

#### Three Forms of Machine Memory
![Three Forms of Memory](../assets/images/evals/llm-memory-01-three-forms.png)
*Parametric memory (weights), Working memory (context window), and Externalized state (episodic storage).*

#### Sliding Window vs. Summary Buffers
![Summary Buffer Architecture](../assets/images/evals/llm-memory-04-summary-buffer.png)
*Techniques for rolling conversation summarization to preserve persistent intent within strict token budgets.*

#### Production Agent Memory Architecture
![Production Memory Stack](../assets/images/evals/llm-memory-07-production-memory-stack.png)
*Tiered memory layout combining working context, entity scratchpad, and long-term vector stores.*

---

## 7. LLMs as a Judge: How to Know if Your LLM is Healthy
{: .d-inline-block }
14 Sep 2026
{: .label .label-purple }

**Architectural Summary:**  
Establishes a multi-tier evaluation framework for production LLMs, detailing golden dataset curation, deterministic automated checks, model-graded judging modes (pointwise, pairwise, reference-based), and alignment with human-in-the-loop validation.

### Key Diagrams

#### Health Dimensions of Production Models
![Health Dimensions](../assets/images/evals/llm-judge-01-health-dimensions.png)
*Core evaluation pillars: Factuality, instruction following, safety compliance, latency, and token efficiency.*

#### Continuous Evaluation Loop
![Eval Loop](../assets/images/evals/llm-judge-02-eval-loop.png)
*Live production tracing -> Golden dataset sampling -> Automated judging -> Regression alerts.*

#### Deterministic Heuristics vs. Model-Graded Checks
![Deterministic vs Model Checks](../assets/images/evals/llm-judge-04-deterministic-vs-model-checks.png)
*Combining cheap regex/schema tests with high-capacity LLM judges for qualitative evaluation.*

#### Model-Graded Scoring Modes
![Scoring Modes](../assets/images/evals/llm-judge-05-scoring-modes.png)
*Comparing Pointwise evaluation (1-5 Likert scale) and Pairwise battle ranking (A vs B comparison).*

---

## 8. How to Deal With Errors and Failures in LLM-Powered Applications
{: .d-inline-block }
07 Sep 2026
{: .label .label-blue }

**Architectural Summary:**  
Provides comprehensive systems architecture patterns for LLM application resilience—classifying transient API outages, semantic/schema failures, and tool errors while implementing jittered exponential backoffs, circuit breakers, fallback degradation, and idempotent tool execution.

### Key Diagrams

#### Failure Taxonomy for LLM Applications
![Failure Taxonomy](../assets/images/evals/llm-resilience-02-failure-taxonomy.png)
*Differentiating Network/Rate limits, Generation timeouts, Schema non-compliance, and Tool invocation exceptions.*

#### Exponential Backoff with Decorrelated Jitter
![Backoff Jitter](../assets/images/evals/llm-resilience-03-backoff-jitter.png)
*Preventing thundering herd problems during upstream model provider outages.*

#### Fallbacks & Graceful Degradation
![Fallbacks Degradation](../assets/images/evals/llm-resilience-05-fallbacks-degradation.png)
*Degrading from frontier reasoning models to fast distilled SLMs or cached deterministic responses.*

#### Circuit Breakers & Idempotent Tool Execution
![Circuit Breakers](../assets/images/evals/llm-resilience-06-circuit-breakers.png)
*Tripping circuit breakers on repeated provider failures and ensuring tool mutations use idempotency keys.*

---

## 9. How to Steal an AI Model’s Private Thoughts
{: .d-inline-block }
25 Aug 2026
{: .label .label-red }

**Architectural Summary:**  
Dissects breakthrough research uncovering how client-side encrypted reasoning traces returned by frontier model APIs can be replayed into smaller model variants to extract hidden internal chains-of-thought in plaintext, highlighting serious architectural leakage vectors in stateless token design.

### Key Diagrams

#### Reasoning Traces vs. User-Facing Answers
![Traces vs Answers](../assets/images/evals/reasoning-security-01-traces-vs-answers.png)
*How internal thinking tokens contain private reasoning logic withheld from final user responses.*

#### Cross-Model Replay Attack Architecture
![Cross-Model Replay Attack](../assets/images/evals/reasoning-security-03-cross-model-replay-attack.png)
*Replaying opaque reasoning tokens through target model decoders to force full token emission.*

#### Cryptographic Token Binding Mitigations
![Cryptographic Token Binding](../assets/images/evals/reasoning-security-05-cryptographic-token-binding.png)
*Binding reasoning state to ephemeral server sessions to prevent cross-client token tampering.*

---

## 10. Why Code Verification Matters More Than Ever in the Age of AI
{: .d-inline-block }
24 Aug 2026
{: .label .label-yellow }

**Architectural Summary:**  
Co-authored with Sonar's CTO, this edition shows how AI generation inverses software delivery bottlenecks from writing to verification—analyzing DORA/METR empirical productivity slowdowns and presenting AST/control-flow static analysis pipelines to audit agent code.

### Key Diagrams

#### The Delivery Bottleneck Inversion
![Bottleneck Inversion](../assets/images/evals/code-verification-01-bottleneck-inversion.png)
*As code generation speed increases 10x, review, debugging, and verification become the dominant engineering constraints.*

#### Clean Code CI/CD Verification Pipeline
![Clean Code Pipeline](../assets/images/evals/code-verification-03-clean-code-pipeline.png)
*Static AST analysis, taint analysis, and runtime contract tests gating agent pull requests.*

#### Human-in-the-Loop Review Architecture
![Human in the Loop Workflow](../assets/images/evals/code-verification-07-human-in-the-loop-workflow.png)
*Structuring automated summaries and test failure traces so human reviewers can verify agent changes in seconds.*

---

## 11. LLM Security Basics: The Full Threat Model
{: .d-inline-block }
03 Aug 2026
{: .label .label-red }

**Architectural Summary:**  
Outlines the unified threat landscape of LLMs rooted in the absence of hardware/data trust boundaries (concatenating instructions and data), detailing direct and indirect prompt injection vectors, the EchoLeak vulnerability, RAG data poisoning, and multi-layered defense architectures.

### Key Diagrams

#### Absence of Hardware Trust Boundaries
![Trust Boundaries](../assets/images/evals/llm-security-01-trust-boundaries.png)
*Why mixing control logic and untrusted user input in the same token stream makes prompt injection fundamentally hard.*

#### Direct vs. Indirect Prompt Injection
![Direct vs Indirect Injection](../assets/images/evals/llm-security-02-direct-vs-indirect-injection.png)
*Attacks originating from user chat inputs vs. poisoned third-party web pages and documents retrieved by tools.*

#### RAG Data Poisoning Attack Surface
![RAG Data Poisoning](../assets/images/evals/llm-security-06-rag-data-poisoning.png)
*Injecting adversarial text into corpora to manipulate embedding similarity and hijack agent tool calls.*

#### Defense in Depth Security Framework
![Defense in Depth](../assets/images/evals/llm-security-07-defense-in-depth.png)
*Input filtering, tool permission scoping, output sanitization, and isolated execution sandboxes.*

---

## 12. Best Practices for Building AI Agents That Work in Production
{: .d-inline-block }
22 Jul 2026
{: .label .label-green }

**Architectural Summary:**  
Translates the Twelve-Factor App philosophy to AI agents, formalizing four core operational pillars: strict context budgeting, deterministic control flow with explicit termination criteria, externalized state orchestration, and narrow scoped subagents.

### Key Diagrams

#### Deterministic Control Flow & Termination Criteria
![Deterministic Control Flow](../assets/images/evals/prod-agents-03-deterministic-control-flow.png)
*Enforcing step counters, budget ceilings, and explicit exit conditions on agent execution loops.*

#### Externalized State & Checkpointing
![Externalized State](../assets/images/evals/prod-agents-04-externalized-state.png)
*Storing execution graphs in transactional databases to survive container restarts and enable time-travel rollbacks.*

#### Scope Isolation & Specialized Subagents
![Scope Isolation](../assets/images/evals/prod-agents-05-scope-isolation.png)
*Limiting tool sets and system prompts to specialized subagents to prevent cascading error propagation.*

---

## 13. How DoorDash Built a Testing System to Evaluate LLMs
{: .d-inline-block }
30 May 2026
{: .label .label-purple }

**Architectural Summary:**  
Case study detailing DoorDash’s transition from deterministic decision trees to an LLM customer support agent—implementing a simulation and evaluation flywheel with synthetic conversation generators, scenario replay harnesses, and automated grading to prevent subtle regression bugs.

### Key Diagrams

#### Simulation & Evaluation Flywheel
![Simulation Eval Flywheel](../assets/images/evals/doordash-evals-03-simulation-eval-flywheel.png)
*Production conversation logging -> Persona simulation -> Multi-turn scenario replay -> Automated grading.*

#### Multi-Turn Simulation Test Harness
![Multi-Turn Simulation Harness](../assets/images/evals/doordash-evals-04-multi-turn-simulation-harness.png)
*Pairing a customer simulator LLM with the production agent to stress-test complex dispute and refund flows.*

---

## 14. A Guide to Context Engineering for LLMs
{: .d-inline-block }
06 Apr 2026
{: .label .label-blue }

**Architectural Summary:**  
Demonstrates why larger context windows degrade model intelligence (dropping accuracy from 95% to 60%), unpacking token economics, attention saturation, quadratic memory overhead, and best practices for structured prompt layout and KV-cache alignment.

### Key Diagrams

#### Accuracy Degradation Over Context Length
![Accuracy Degradation Curve](../assets/images/evals/context-eng-01-accuracy-degradation-curve.png)
*Empirical measurement showing model reasoning accuracy declining as context fills with irrelevant tokens.*

#### Context Engineering Playbook
![Context Engineering Playbook](../assets/images/evals/context-eng-04-context-engineering-playbook.png)
*Guidelines for token budget allocation, prefix caching alignment, and dynamic context pruning.*

---

## 15. How Anthropic’s Claude Thinks
{: .d-inline-block }
25 Mar 2026
{: .label .label-purple }

**Architectural Summary:**  
Explores Anthropic’s mechanistic interpretability research using Sparse Autoencoders (SAEs) to unpack polysemantic neurons into monosemantic feature dictionaries, revealing parallel reasoning tracks, internal deception circuits, and safety refusal mechanisms inside Claude.

### Key Diagrams

#### Polysemantic Neurons vs. Monosemantic SAE Features
![Polysemanticity and SAEs](../assets/images/evals/claude-thinks-02-polysemanticity-and-saes.png)
*Decompressing tangled neuron activations into millions of interpretable, single-concept feature vectors.*

#### Feature Steering & Activation Clamping
![Feature Steering](../assets/images/evals/claude-thinks-04-feature-steering.png)
*Artificially clamping internal feature activations to steer model tone, safety, or factual emphasis without fine-tuning.*

#### Safety Refusal Circuits
![Refusal Circuits](../assets/images/evals/claude-thinks-06-refusal-circuits.png)
*Tracing the precise neural pathways that detect harmful intents and trigger safety refusal sequences.*

---

## 16. A Guide to Effective Prompt Engineering
{: .d-inline-block }
04 Feb 2026
{: .label .label-green }

**Architectural Summary:**  
Comprehensive breakdown of production prompt engineering—covering anatomy of high-performance prompts (task, context, examples), system prompt role boundaries, prompting taxonomy (Few-Shot, Chain-of-Thought, ReAct, Self-Consistency), and JSON schema enforcement.

### Key Diagrams

#### Anatomy of a Production Prompt
![Prompt Anatomy](../assets/images/evals/prompt-eng-01-anatomy.png)
*System role, explicit constraints, input payload, few-shot demonstration pairs, and structured schema.*

#### Prompting Taxonomy: Few-Shot to Chain-of-Thought
![Prompting Taxonomy](../assets/images/evals/prompt-eng-03-prompting-taxonomy.png)
*Technique matrix: Zero-shot, few-shot, step-by-step reasoning, self-consistency sampling, and ReAct.*

---

## 17. A Guide to LLM Evals
{: .d-inline-block }
12 Jan 2026
{: .label .label-blue }

**Architectural Summary:**  
Foundational architecture guide establishing deterministic vs probabilistic evaluation paradigms for LLMs, formalizing evaluation hierarchies (rule-based heuristics, model-graded evaluators, human calibration), and offline vs online lifecycle monitoring.

### Key Diagrams

#### Deterministic vs. Probabilistic Evals
![Deterministic vs Probabilistic](../assets/images/evals/llm-evals-guide-01-deterministic-vs-probabilistic.png)
*Contrasting exact match / schema validation with semantic similarity and model-as-a-judge scoring.*

#### Evaluation Hierarchy & Offline/Online Lifecycle
![Evaluation Hierarchy](../assets/images/evals/llm-evals-guide-02-eval-hierarchy.png)
*Tiered testing pyramid: Unit test assertions -> LLM-as-a-Judge -> Human evaluation sampling.*

---

## 18. The Memory Problem: Why LLMs Sometimes Forget Your Conversation
{: .d-inline-block }
22 Oct 2025
{: .label .label-yellow }

**Architectural Summary:**  
Examines fundamental context window capacity limits and conversational memory breakdown—contrasting stateless next-token prediction with FIFO truncation issues, and evaluating sliding windows, running summaries, and external vector memory stores.

### Key Diagrams

#### The Illusion of Conversational Memory
![Illusion of Memory](../assets/images/evals/memory-problem-01-illusion-of-memory.png)
*Why every chat turn re-processes full conversation history from scratch due to model statelessness.*

#### Memory Management Strategies
![Memory Strategies](../assets/images/evals/memory-problem-03-memory-management-strategies.png)
*Comparing FIFO message pruning, dynamic rolling summaries, and semantic vector recall.*
