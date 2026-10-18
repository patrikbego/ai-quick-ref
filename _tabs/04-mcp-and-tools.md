---
layout: page
title: "Model Context Protocol & Tools"
icon: fas fa-plug
order: 4
toc: true
---

# Model Context Protocol (MCP) & Tools

Comprehensive quick reference covering Anthropic's Model Context Protocol (MCP), tool use evolution, enterprise MCP ecosystems (Pinterest, Figma), MCP vs Skills, and protocol architectures 

---

## 1. EP224: MCP vs RAG vs AI Agents

> 🗓️ **Date:** 05 Sep 2026

**Architectural Summary:**  
Compares the three foundational pillars of modern LLM architectures—MCP (open standard client-server protocol for dynamic tool and data connectivity), RAG (retrieval-augmented generation for grounding static knowledge from external documents and vector stores), and AI Agents (autonomous multi-turn goal execution and decision-making systems).

### Key Diagram

#### Architectural Comparison Matrix
![MCP vs RAG vs AI Agents Comparison](/assets/images/mcp/mcp-vs-rag-vs-agents-ep224.png)
*Detailed matrix evaluating MCP, RAG, and AI Agents across primary role, data access mechanics, interaction modes, statefulness, and autonomy levels.*

---

## 2. How Pinterest Built a Production MCP Ecosystem

> 🗓️ **Date:** 11 May 2026
{: .label .label-blue }

**Architectural Summary:**  
Examines how Pinterest scaled an enterprise-wide production MCP architecture to collapse $N \times M$ tool integrations into $N + M$ via three architectural bets: cloud-hosted micro-MCP servers, a centralized registry with unified CI/CD, and a two-layer authentication mechanism (user identity propagation alongside service-to-service auth) across IDE, chat, and CLI agent surfaces.

### Key Diagrams

#### What is MCP: Core Concept
![What is MCP Concept](/assets/images/mcp/pinterest-01-what-is-mcp-concept.png)
*Client-server architecture bridging generative models to external internal company tools and databases.*

#### Standardized Tool Discovery & Execution
![Tool Discovery and Execution](/assets/images/mcp/pinterest-02-tool-discovery-and-execution.png)
*JSON-RPC flow for querying available tool schemas and dispatching authorized execution calls.*

#### Collapsing the $N \times M$ Integration Problem
![NxM to N+M Problem](/assets/images/mcp/pinterest-03-nxm-to-npm-problem.png)
*How a standardized protocol avoids building separate custom connectors between every client surface and internal service.*

#### Pinterest Production MCP Ecosystem
![Pinterest Production MCP Ecosystem](/assets/images/mcp/pinterest-04-production-ecosystem-architecture.png)
*High-level topology showing Developer Surfaces, Central Registry, MCP Gateway, Authentication, and internal micro-MCP servers.*

#### Two-Layer Authentication Architecture
![Two-Layer Authentication Architecture](/assets/images/mcp/pinterest-05-two-layer-auth-architecture.png)
*Enforcing security via Service-to-Service mTLS/tokens combined with end-user OAuth token propagation to respect existing ACLs.*

#### Multi-Surface Integration
![Multi-Surface Integration](/assets/images/mcp/pinterest-07-multi-surface-integration.png)
*Enabling consistent tool execution across IDE extensions, terminal CLI agents, and Slack enterprise bots.*

---

## 3. Connecting LLMs to the Real World: Tool Use, Function Calling, and MCP

> 🗓️ **Date:** 04 May 2026
{: .label .label-green }

**Architectural Summary:**  
Traces the architectural evolution bridging isolated text-prediction LLMs to external systems—moving from prompt-based parsing and native JSON function calling to Anthropic's Model Context Protocol (MCP) client-server standard to resolve tool fragmentation.

### Key Diagrams

#### Tool Evolution Timeline
![Tool Evolution Timeline](/assets/images/mcp/connect-04-tool-evolution-timeline.png)
*Four evolutionary stages: Manual Prompt Engineering -> ReAct Loops -> Native Function Calling -> Standardized Model Context Protocol.*

#### The Agentic Tool Execution Loop
![Agentic Tool Loop](/assets/images/mcp/connect-03-agentic-tool-loop.png)
*User prompt -> Model decides tool call -> Client executes tool -> Observation returned to context window -> Model completes synthesis.*

#### MCP Client-Server Three-Component Architecture
![MCP Client-Server Architecture](/assets/images/mcp/connect-06-mcp-client-server-architecture.png)
*Separation of concerns between Host Application (e.g. Claude Desktop/IDE), MCP Client, and modular MCP Servers.*

#### MCP Request Execution Sequence
![MCP Request Execution Flow](/assets/images/mcp/connect-07-mcp-request-execution-flow.png)
*Protocol handshake, capability negotiation, tool dispatch, and JSON-RPC response lifecycle.*

---

## 4. EP213: MCP vs Skills, Clearly Explained

> 🗓️ **Date:** 02 May 2026

**Architectural Summary:**  
Differentiates Model Context Protocol (MCP) from Agent Skills across five dimensions—identifying MCP as a typed JSON-RPC client-server integration protocol for connecting to external services, whereas Skills are file-based prompt and script instructions (`SKILL.md`) dynamically injected into the context window.

### Key Diagrams

#### Five-Dimension Comparison: MCP vs Skills
![MCP vs Skills Comparison](/assets/images/mcp/mcp-vs-skills-comparison-ep213.png)
*Comparative breakdown across Integration Type, Execution Environment, Invocation Mechanics, State Management, and Distribution Packaging.*

#### Defending Tool Execution Against Prompt Injection
![Defending Prompt Injection with Least-Privilege Tools](/assets/images/mcp/prompt-injection-least-privilege-tools.png)
*Implementing least-privilege tool access, schema validation, and human-in-the-loop approvals for sensitive API mutations.*

---

## 5. Figma Design to Code, Code to Design: Clearly Explained

> 🗓️ **Date:** 14 Apr 2026
{: .label .label-blue }

**Architectural Summary:**  
Explains how Figma’s production MCP server bridges design files and codebases by transforming noisy raw REST API JSON into token-efficient semantic design context, powering bidirectional workflows: design-to-code (via `get_design_context` and Code Connect) and code-to-design (via live DOM inspection and HTML-to-native-Figma-layer mapping).

### Key Diagrams

#### Figma Design to Code & Code to Design Overview
![Figma Design to Code Overview](/assets/images/mcp/figma-01-design-to-code-overview.png)
*End-to-end architecture enabling bidirectional translation between Figma canvas nodes and production frontend components.*

#### The Context Gap: Raw JSON vs. MCP Semantic Context
![Gap Between Design and Code](/assets/images/mcp/figma-02-gap-between-design-and-code.png)
*Why raw Figma REST JSON blows context budgets and how the MCP server distills it into semantic component tokens.*

#### Design-to-Code Workflow Sequence
![Design to Code Workflow](/assets/images/mcp/figma-03-design-to-code-workflow.png)
*Agent queries Figma MCP -> extracts design tokens & node hierarchy -> maps to Design System components via Code Connect -> outputs code.*

#### Code-to-Design via DOM Tree Walking
![DOM Tree Walking Extraction](/assets/images/mcp/figma-09-dom-tree-walking-extraction.png)
*Extracting rendered DOM bounding boxes, computed styles, and SVG paths to reconstruct native Figma canvas components.*

#### Code Connect Component Mapping
![Code Connect Component Mapping](/assets/images/mcp/figma-11-code-connect-component-mapping.png)
*Connecting production React/Vue component libraries directly to Figma component variants for pixel-accurate code generation.*

---

## 6. EP202: MCP vs RAG vs AI Agents

> 🗓️ **Date:** 14 Feb 2026
{: .label .label-yellow }

**Architectural Summary:**  
Compares the execution architectures of MCP (tool & data connectivity protocol), RAG (document retrieval for knowledge grounding), and AI Agents (autonomous decision-making workflows), alongside a dedicated breakdown of the Agent Skills workflow showing how `SKILL.md` bundles are dynamically selected and injected to execute tasks with minimal context overhead.

### Key Diagrams

#### Architecture Comparison Chart
![MCP vs RAG vs Agents EP202](/assets/images/mcp/mcp-vs-rag-vs-agents-ep202.jpeg)
*Contrasting protocol interfaces (MCP), vector embedding indexes (RAG), and reasoning control loops (Agents).*

#### Dynamic Agent Skills Execution Workflow
![Agent Skills Execution Workflow](/assets/images/mcp/agent-skills-execution-workflow.png)
*Step-by-step resolution: Intent classification -> loading `SKILL.md` instructions -> running bundled scripts -> returning structured results.*

---

## 7. EP183: MCP vs API: what’s the difference?

> 🗓️ **Date:** 04 Oct 2025

**Architectural Summary:**  
Contrasts traditional software-to-software APIs (fragmented across REST/GraphQL/gRPC, requiring external documentation and human integration) with Anthropic's Model Context Protocol (an AI-native, self-describing standard providing uniform schemas for resources, prompts, and tools).

### Key Diagram

#### MCP vs API Architecture Comparison
![MCP vs API Comparison](/assets/images/mcp/mcp-vs-api-comparison.png)
*Side-by-side architectural analysis contrasting programmatic REST interfaces with self-describing JSON-RPC AI agent protocols.*

---

## 8. Why Anthropic’s MCP is a Big Deal

> 🗓️ **Date:** 30 Sep 2025
{: .label .label-green }

**Architectural Summary:**  
Details Anthropic's Model Context Protocol (MCP) as an open standard bridging models to real-time data, breaking down its three architectural components (Host, Client, Server), its three-tiered protocol stack (Transport, JSON-RPC Protocol, and Capabilities: Resources/Tools/Prompts), and the complete lifecycle journey of a request.

### Key Diagrams

#### Why Anthropic's MCP is a Big Deal Overview
![MCP Big Deal Overview](/assets/images/mcp/mcp-big-deal-overview.png)
*Foundational infographic introducing open standardized context integration for foundation models.*

#### The Three Architectural Components
![MCP Three Components Architecture](/assets/images/mcp/mcp-three-components-architecture.png)
*Interaction boundaries between Host Applications, embedded MCP Clients, and standalone MCP Servers.*

#### Three-Tiered Protocol Stack
![MCP Three-Tier Protocol Stack](/assets/images/mcp/mcp-three-tier-protocol-stack.png)
*Detailed stack: Transport (Stdio / SSE) -> Protocol (JSON-RPC 2.0) -> Primitives (Resources, Tools, Prompts).*

#### The Complete Journey of a Request
![MCP Journey of a Request](/assets/images/mcp/mcp-journey-of-a-request.png)
*Lifecycle sequence: Client initialization -> Server handshake -> Tool enumeration -> User prompt -> Model function call -> Server response.*

---

## 9. EP173: BIGGEST Mistakes to Avoid in System Design Interviews

> 🗓️ **Date:** 26 Jul 2025
{: .label .label-blue }

**Architectural Summary:**  
Catalogs 12 essential production MCP servers (FileSystem, GitHub, Slack, Postgres, Docker, Stripe, etc.) connecting LLMs to runtime tools, while analyzing how MCP (vertical agent-to-tool context integration) complements A2A (horizontal agent-to-agent peer collaboration) in a composite architecture.

### Key Diagrams

#### 12 Production MCP Servers Catalog
![12 MCP Servers Catalog](/assets/images/mcp/12-mcp-servers-catalog-ep173.jpeg)
*Directory of battle-tested MCP servers spanning storage, version control, messaging, containers, and databases.*

#### MCP vs. A2A Protocol Architecture
![MCP vs A2A Protocol Architecture](/assets/images/mcp/mcp-vs-a2a-protocol-architecture.png)
*Vertical tool connectivity (Model Context Protocol) working in harmony with horizontal multi-agent collaboration (Agent-to-Agent).*

---

## 10. EP163: 12 MCP Servers You Can Use in 2025

> 🗓️ **Date:** 17 May 2025

**Architectural Summary:**  
Surveys 12 foundational Model Context Protocol (MCP) servers across local environments, cloud tools, databases, and APIs (such as FileSystem, GitHub, PostgreSQL, Docker, Redis, Slack, Stripe, and Google Drive) that provide LLMs with standardized, secure read/write capabilities.

### Key Diagram

#### Production MCP Servers for Modern Engineering
![12 MCP Servers Infographic](/assets/images/mcp/12-mcp-servers-catalog-ep163.jpeg)
*Infographic highlighting setup, security parameters, and data schemas for 12 key community and official MCP servers.*

---

## 11. EP154: What is MCP?

> 🗓️ **Date:** 15 Mar 2025
{: .label .label-yellow }

**Architectural Summary:**  
Introduces the fundamental architecture of Anthropic's Model Context Protocol (MCP), breaking down its client-server model (Host, MCP Client, and MCP Server) and its core primitives (Resources, Prompts, Tools, Roots, Sampling) for standardizing LLM access to external data.

### Key Diagram

#### MCP Architecture & Core Primitives
![What is MCP Primitives](/assets/images/mcp/what-is-mcp-primitives-ep154.gif)
*Visual primer on how MCP Clients negotiate capability primitives with Host applications and remote MCP Servers.*
