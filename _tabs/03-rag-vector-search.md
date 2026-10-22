---
layout: page
title: "RAG & Vector Search"
icon: fas fa-database
order: 3
toc: true
---

# RAG, Vector Search & Retrieval

Comprehensive quick reference covering GraphRAG, Agentic RAG control loops, embedding model design, multi-tenant vector partitioning (Airtable Milvus), distributed SQL vector indexing (CockroachDB C-SPANN), and enterprise multimodal search.

<div class="d-flex flex-wrap gap-1 mb-3"><span class="badge bg-light text-dark border">#rag</span><span class="badge bg-light text-dark border">#vector-search</span><span class="badge bg-light text-dark border">#graphrag</span><span class="badge bg-light text-dark border">#hybrid-retrieval</span><span class="badge bg-light text-dark border">#reranking</span><span class="badge bg-light text-dark border">#pgvector</span></div> 

---

## 1. The End-to-End RAG Application Stack

> 🗓️ **Architecture Guide:** Enterprise Retrieval-Augmented Generation Foundations · <span class="badge bg-warning text-dark">🟡 Intermediate</span>
{: .label .label-purple }

**Architectural Summary:**  
Deconstructs the complete lifecycle of production Retrieval-Augmented Generation (RAG) systems across six core architectural stages: multi-format document ingestion, semantic chunking and metadata enrichment, dense vector embedding generation, high-dimensional vector database persistence and indexing, similarity/hybrid retrieval, and context-augmented prompt synthesis with guardrails.

### Key Diagrams

#### End-to-End RAG Application Stack
![AI App Stack RAG](/assets/images/foundations/ai-app-stack-rag.jpeg)
*Complete multi-tier RAG architecture: ingestion pipeline, chunking, embedding generation, vector indexing, retrieval routing, and LLM context synthesis.*

> 💻 **Hands-on Implementation:**  
> Looking for production code? See the runnable [Python & Java Hybrid RAG Implementation](/07-developer-tools/#pattern-1-production-hybrid-rag-pipeline-dense--sparse-rrf--reranker) in Developer AI Tools, featuring dense vector retrieval, BM25 sparse search, Reciprocal Rank Fusion (RRF), and citation tracking.
{: .prompt-tip }

---

## 2. EP229: 8 Chunking Strategies for RAG-Based Agents

> 🗓️ **Date:** 17 Oct 2026 · <span class="badge bg-warning text-dark">🟡 Intermediate</span>
{: .label .label-green }

**Architectural Summary:**  
Comprehensive technical analysis of eight text chunking strategies for agentic retrieval systems—evaluating fixed-size, sentence-level, recursive character, document structure-aware, semantic similarity shift, and agentic LLM-driven chunking to optimize context window recall versus boundary fidelity. Additionally dissects the sequence-to-sequence neural architecture of Google Translate and the modular anatomy of executable Agent Skills.

### Key Diagrams

#### 8 Chunking Strategies for RAG-Based Agents
![8 Chunking Strategies](/assets/images/rag/rag-chunking-01-strategies-for-agents.png)
*Comparative taxonomy of chunking algorithms: character/token fixed-size, recursive chunking, document-aware Markdown/HTML parsing, semantic boundary splitting, and hierarchical parent-child retrieval.*

#### Google Translate Neural Machine Translation Architecture
![Google Translate Neural Architecture](/assets/images/rag/rag-chunking-02-google-translate-architecture.png)
*Deep sequence-to-sequence transformer encoder-decoder architecture with residual connections and multi-head cross-attention for multilingual cross-lingual document translation.*

#### Agent Skills Modular Execution Architecture
![Agent Skills Modular Architecture](/assets/images/rag/rag-chunking-03-agent-skills-execution-architecture.png)
*Architectural specification of executable agent skills: schema contracts, input validation, tool isolation, state management, and orchestration loops.*

---

## 3. GraphRAG: How AI Answers Questions Hidden Across Many Documents

> 🗓️ **Date:** 19 Aug 2026

**Architectural Summary:**  
Overcomes standard vector similarity limits on corpus-wide aggregation by extracting knowledge graphs from text, clustering nodes via Leiden community detection into hierarchical summaries, and supporting both Local Search (entity neighborhood traversal) and Global Search (map-reduce over community reports) via agentic routing.

### Key Diagrams

#### Standard RAG Indexing vs. Graph Construction
![Standard RAG Indexing Pipeline](/assets/images/rag/graphrag-01-standard-rag-indexing.png)
*Linear chunk-and-embed pipeline compared against structured entity, claim, and relationship extraction.*

#### Similarity Search Limitations on Global Questions
![Similarity Search Limits](/assets/images/rag/graphrag-03-similarity-search-limits.png)
*Why vector cosine distance excels at localized needles in haystacks but fails completely on holistic corpus-wide questions.*

#### Knowledge Graph Construction Pipeline
![Knowledge Graph Construction](/assets/images/rag/graphrag-04-knowledge-graph-construction.png)
*Extracting entities, relationships, and source claims from document chunks to build a connected knowledge graph.*

#### Graph Provenance & Text Pointers
![Knowledge Graph Provenance](/assets/images/rag/graphrag-05-knowledge-graph-provenance.png)
*Enforcing strict grounding by linking every entity node and relationship edge back to exact chunk offsets in source text.*

#### Hierarchical Community Detection (Leiden)
![Hierarchical Community Detection](/assets/images/rag/graphrag-06-community-detection-hierarchy.png)
*Clustering knowledge graph partitions from high-level global themes (C0/C1) down to granular sub-topics (C2/C3).*

#### Local vs. Global Search Modes
![Local vs Global Search](/assets/images/rag/graphrag-07-local-vs-global-search.png)
*Query routing: Local Search queries entity subgraphs; Global Search performs parallel map-reduce over community summary reports.*

#### Agentic Retrieval Router
![Agentic Retrieval Routing](/assets/images/rag/graphrag-08-agentic-retrieval-routing.png)
*LLM router classifying user prompts to dispatch either Standard RAG, Local GraphRAG, or Global Community Search.*

---

## 4. Why Your RAG System Is Only as Good as Its Translator Model

> 🗓️ **Date:** 02 Sep 2026
{: .label .label-blue }

**Architectural Summary:**  
Argues that RAG accuracy is fundamentally bounded by the quality and domain alignment of the embedding model rather than generator LLM capacity, detailing indexing vs. retrieval stages, semantic search failure modes, the high re-indexing cost of model migration, and Matryoshka Representation Learning (MRL) storage designs.

### Key Diagrams

#### Separating Knowledge Retrieval from Language Generation
![Retriever vs Generator](/assets/images/rag/translator-02-retriever-vs-generator.png)
*Clear architectural separation: The embedding retriever determines context relevance; the LLM only formats the retrieved context.*

#### The Indexing Phase Pipeline
![Indexing Phase Pipeline](/assets/images/rag/translator-03-indexing-phase-pipeline.png)
*Document preprocessing, token chunking, embedding generation via translator model, and dense vector persistence.*

#### The Retrieval Phase Pipeline
![Retrieval Phase Pipeline](/assets/images/rag/translator-04-retrieval-phase-pipeline.png)
*Query embedding transformation, top-k vector similarity search, re-ranking, and dynamic prompt augmentation.*

#### Semantic Similarity Pitfalls
![Semantic Similarity Pitfalls](/assets/images/rag/translator-06-semantic-similarity-pitfalls.png)
*Failure modes where cosine similarity matches topical keywords rather than answering the user's specific operational question.*

#### The High Migration Cost of Switching Embeddings
![Cost of Changing Embeddings](/assets/images/rag/translator-07-cost-of-changing-embeddings.png)
*Why swapping embedding models requires re-computing vectors across millions of documents and invalidates existing indexes.*

#### Matryoshka Representation Learning (MRL) Storage Designs
![Matryoshka Storage Designs](/assets/images/rag/translator-08-matryoshka-storage-designs.png)
*Three multi-tier vector sizing layouts: Slicing embeddings dynamically to trade minor precision drops for massive memory savings.*

---

## 5. EP220: RAG vs Graph RAG vs Agentic RAG

> 🗓️ **Date:** 27 Jun 2026
{: .label .label-green }

**Architectural Summary:**  
Contrasts the three primary retrieval paradigms—Standard RAG (single-turn semantic vector search for localized queries), Graph RAG (community-clustered knowledge graph traversals for global dataset summaries), and Agentic RAG (multi-step iterative query decomposition, tool-routed retrieval, and automated response validation).

### Key Diagram

#### Three Retrieval Paradigms Compared
![RAG vs Graph RAG vs Agentic RAG](/assets/images/rag/rag-vs-graphrag-vs-agentic-rag-ep220.png)
*Comprehensive comparison matrix covering query complexity, indexing cost, traversal mechanics, and evaluation metrics.*

---

## 6. How Airtable Built the Search Layer Behind Their AI Features

> 🗓️ **Date:** 27 May 2026

**Architectural Summary:**  
Explains how Airtable architected a multi-tenant vector search system on Milvus across hundreds of thousands of customer bases, leveraging per-base partitioning, DiskANN SSD-resident vector indexing, and dynamic hot/cold partition offloading to achieve p99 <500ms retrieval without paying continuous in-memory RAM costs for 75% idle bases.

### Key Diagrams

#### Multi-Tenant Partitioning Strategy
![Multi-Tenant Partitioning](/assets/images/rag/airtable-02-multi-tenant-partitioning.png)
*Isolating customer data by provisioning dedicated collection partitions per table and workspace within shared Milvus clusters.*

#### Cluster Sharding Hierarchy
![Cluster Sharding Hierarchy](/assets/images/rag/airtable-03-cluster-sharding-hierarchy.png)
*Physical topology showing stateless query proxies, partition-aware routing, and distributed data nodes.*

#### End-to-End Query Execution Flow
![Query Execution Flow](/assets/images/rag/airtable-04-query-execution-flow.png)
*Proxy authentication -> targeting designated partition -> parallel vector scan -> reciprocal rank fusion.*

#### DiskANN SSD-Resident Indexing vs. HNSW RAM
![DiskANN SSD Indexing](/assets/images/rag/airtable-05-diskann-ssd-indexing.png)
*Trading minimal disk I/O latency for 80% reduction in high-cost server RAM footprints.*

#### Hot/Cold Partition Tiering
![Hot Cold Partition Tiering](/assets/images/rag/airtable-06-hot-cold-partition-tiering.png)
*Dynamically offloading dormant workspace partitions to S3 object storage and loading them back on demand.*

---

## 7. How CockroachDB Built Vector Indexing at Scale

> 🗓️ **Date:** 25 May 2026
{: .label .label-blue }

**Architectural Summary:**  
Details C-SPANN, CockroachDB's distributed vector indexing engine designed to eliminate central coordinators and massive RAM requirements by embedding a hierarchical centroid clustering tree directly into SQL table storage, automatically leveraging CockroachDB's native range sharding, Raft replication, and ACID guarantees.

### Key Diagrams

#### Vector Space vs. Distributed SQL Constraints
![Distributed SQL Constraints](/assets/images/rag/cockroach-02-distributed-sql-constraints.png)
*Architectural hurdles: Scaling approximate nearest neighbor (ANN) search across shared-nothing distributed SQL nodes.*

#### The C-SPANN Tree Architecture
![C-SPANN Tree Architecture](/assets/images/rag/cockroach-03-c-spann-tree-architecture.png)
*Hierarchical centroid clustering structure (fanout ~100) enabling localized index navigation.*

#### Vector Partitions as Native SQL Key-Value Rows
![Key-Value Partition Storage](/assets/images/rag/cockroach-04-key-value-partition-storage.png)
*Encoding high-dimensional vector centroids directly as ordered keys in RocksDB/Pebble storage engines.*

#### Automatic Range Sharding & Raft Consensus
![Automatic Range Sharding Raft](/assets/images/rag/cockroach-05-automatic-range-sharding-raft.png)
*Vector index partitions split, balance, and replicate automatically across clusters using existing SQL Raft groups.*

---

## 8. EP216: RAGs vs Agents

> 🗓️ **Date:** 23 May 2026
{: .label .label-yellow }

**Architectural Summary:**  
Contrasts the single-turn, low-cost grounding architecture of RAG (embed -> vector retrieve -> context inject -> generate) against the multi-turn dynamic feedback loop of AI Agents (reason -> tool dispatch -> syscall execution -> observe -> reflect), clarifying the performance, latency, and error-drift trade-offs between them.

### Key Diagrams

#### Linear Grounding vs. Dynamic Execution Loop
![RAGs vs Agents Comparison](/assets/images/rag/rags-vs-agents-comparison-ep216.png)
*Architectural split: Passive read-only context retrieval vs. active environment mutation via tools.*

#### Request Lifecycle Through an Agent Runtime
![Claude Code Request Travel Loop](/assets/images/rag/claude-code-request-travel-loop.jpeg)
*Step-by-step traversal: User prompt -> Plan validation -> Permission enforcement -> Shell/API tool execution.*

---

## 9. How Agentic RAG Works?

> 🗓️ **Date:** 23 Mar 2026

**Architectural Summary:**  
Replaces rigid one-way RAG pipelines with an iterative control loop where an agentic coordinator actively evaluates retrieval quality, rewrites ambiguous queries, routes sub-questions across diverse data sources, and performs self-correcting validation before generating the final response.

### Key Diagrams

#### Standard Linear Pipeline vs. Agentic Loop
![Standard Pipeline Flow](/assets/images/rag/agentic-rag-02-standard-pipeline-flow.png)
*Rigid single-pass pipeline failing when queries require multi-step reasoning or disambiguation.*

#### Shift to Active Control Loop
![Pipeline to Control Loop](/assets/images/rag/agentic-rag-06-pipeline-to-control-loop.png)
*Introducing self-reflection, retrieval validation, and iterative re-querying into retrieval workflows.*

#### Agentic RAG High-Level System Architecture
![Agentic RAG High-Level Architecture](/assets/images/rag/agentic-rag-07-high-level-architecture.png)
*Full topology: Query Decomposer -> Source Router -> Vector/Web Retrievers -> Document Grader -> Generator -> Hallucination Verifier.*

#### Query Refinement & Routing Cycle
![Query Refinement Routing](/assets/images/rag/agentic-rag-08-query-refinement-routing.png)
*Decomposing complex queries into discrete sub-questions dispatched to specialized internal or external indexes.*

---

## 10. Dropbox Multimedia Search: Making File Search More Useful

> 🗓️ **Date:** 09 Dec 2025
{: .label .label-blue }

**Architectural Summary:**  
Details the architecture powering Dropbox Dash’s multimedia search across billions of images and videos, combining an asynchronous multimodal indexing pipeline (extracting EXIF, transcripts, and CLIP embeddings) with geolocation-aware hybrid vector retrieval and just-in-time thumbnail generation to manage petabyte-scale storage costs.

### Key Diagrams

#### Overall Multimedia Search Architecture
![Multimedia Search Architecture](/assets/images/rag/dropbox-01-multimedia-search-architecture.png)
*System architecture combining offline batch feature extractors, multimodal vector indexes, and online query engines.*

#### Metadata & CLIP Embedding Indexing Pipeline
![Metadata Indexing Pipeline](/assets/images/rag/dropbox-02-metadata-indexing-pipeline.png)
*Asynchronous pipeline extracting EXIF timestamps, audio speech-to-text transcripts, and CLIP visual vectors.*

#### Geolocation-Aware Retrieval System
![Geolocation-Aware Retrieval](/assets/images/rag/dropbox-03-geolocation-aware-retrieval.png)
*Combining spatial bounding box filters with dense vector semantic search for contextual media discovery.*

---

## 11. How RAG Enables AI For Your Data

> 🗓️ **Date:** 23 Sep 2025
{: .label .label-green }

**Architectural Summary:**  
Establishes the foundational end-to-end RAG architecture—solving training cutoffs, hallucinations, and private data isolation—by decomposing the pipeline into document preparation (smart chunking and overlap), dense vector embedding generation, vector database indexing, and query-time context augmentation.

### Key Diagrams

#### Foundational RAG Overview
![RAG Foundations Overview](/assets/images/rag/rag-foundations-01-overview.png)
*Complete overview infographic mapping document ingestion, vector storage, and prompt augmentation.*

#### Document Ingestion & Chunking Strategies
![Document Preparation](/assets/images/rag/rag-foundations-03-document-preparation.png)
*Analysis of chunk sizes, sentence-boundary splitting, and sliding window overlaps.*

#### Embedding Generation & Vector Storage
![Embedding Generation](/assets/images/rag/rag-foundations-04-embedding-generation.png)
*Converting text chunks into dense floating-point vector representations stored in ANN vector indexes.*

#### Query Execution & Augmented Generation
![Query Augmentation](/assets/images/rag/rag-foundations-05-query-augmentation.png)
*Injecting top-k retrieved chunks into the prompt context window to ground LLM generation.*

---

## 12. How Dropbox Built an AI Product Dash with RAG and AI Agents

> 🗓️ **Date:** 02 Sep 2025

**Architectural Summary:**  
Explores the architecture of Dropbox Dash, uniting enterprise-wide cross-platform RAG with autonomous AI agents to index emails, documents, calendars, and chats while enforcing strict tenant access control lists (ACLs) and executing agent actions inside a custom secure interpreter.

### Key Diagrams

#### Dropbox Dash Enterprise RAG + Agents
![Dropbox Dash Overview](/assets/images/rag/dropbox-dash-01-overview.png)
*System topology integrating multi-platform enterprise SaaS connectors with agentic reasoning.*

#### Enterprise Access Control Lists (ACLs)
![Core Challenges ACLs](/assets/images/rag/dropbox-dash-02-core-challenges-acls.png)
*Enforcing strict data access permissions during vector retrieval to prevent data leaks between employee roles.*

#### Sandboxed Interpreter Execution Architecture
![Custom Interpreter Sandbox](/assets/images/rag/dropbox-dash-05-custom-interpreter-sandbox.png)
*Secure containerized environment for executing LLM-generated code and tool mutations with audit logs.*

---

## 13. EP169: RAG vs Agentic RAG

> 🗓️ **Date:** 28 Jun 2025
{: .label .label-yellow }

**Architectural Summary:**  
Contrasts static RAG architectures (linear retrieve-and-read pipelines vulnerable to query ambiguity) against Agentic RAG (incorporating query routing, iterative sub-question decomposition, multi-document retrieval, and automated answer validation).

### Key Diagram

#### Static RAG vs. Agentic Control Architecture
![RAG vs Agentic RAG EP169](/assets/images/rag/rag-vs-agentic-rag-ep169.jpeg)
*Architectural comparison highlighting router, reflection, and iterative retrieval stages.*
