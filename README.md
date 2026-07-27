<p align="center">
  <!-- Replace with ./media/sync-banner.png -->
  <img
    src="https://github.com/Saitarun994/SYNC/blob/main/media/banner.png"
    width="100%"
    alt="SYNC — Agentic Crypto Intelligence"
  >
</p>

<h1 align="center">SYNC - Agentic Crypto Intelligence</h1>

<p align="center">
  <strong>LIVE ON-CHAIN RESEARCH · MULTI-AGENT AUTOMATION · SOCIAL INTELLIGENCE</strong>
</p>

<p align="center">
  SYNC turns natural-language requests into live blockchain research, market analysis,
  social intelligence, and repeatable automated workflows.
</p>

Unlike crypto assistants that primarily summarize indexed webpages, SYNC was designed to operate closer to the source. It connected directly to blockchain indexers, RPC infrastructure, market-data providers, Telegram, Twitter/X, and specialized crypto APIs to retrieve live or near-real-time information and coordinate multi-step actions through dedicated agents.

> **Proprietary closed-beta project**  
> Source code, production interfaces, user data, and sensitive execution workflows are not public. Visuals in this case study are intentionally limited, sanitized, or reconstructed for portfolio use.

---

## AT A GLANCE

<p align="center">
  <img src="https://img.shields.io/badge/ADOPTION-10K%2B_SIGNUPS-16C79A?style=for-the-badge" height="28" alt="10K+ signups">
  <img src="https://img.shields.io/badge/CLOSED_BETA-800_ACTIVE_TESTERS-16C79A?style=for-the-badge" height="28" alt="800 active testers">
  <img src="https://img.shields.io/badge/ARCHITECTURE-8_AGENT_SYSTEM-16C79A?style=for-the-badge" height="28" alt="8-agent system">
  <img src="https://img.shields.io/badge/INTEGRATIONS-15%2B_APIS-16C79A?style=for-the-badge" height="28" alt="15+ integrations">
</p>

SYNC was developed within **Limitus**, an on-chain decentralized organization that reached a reported peak market capitalization of approximately **$250M**.

---

## TECHNOLOGY STACK

<p align="center">
  <img
    src="https://skillicons.dev/icons?i=python,fastapi,postgres,redis,sqlite,docker,aws,react,ts,tailwind&perline=10"
    alt="SYNC core technology stack"
  >
</p>

<p align="center">
  <img src="https://img.shields.io/badge/LangGraph-Agent_Orchestration-0B3D2E?style=for-the-badge" height="28" alt="LangGraph">
  <img src="https://img.shields.io/badge/LangChain-Tool_Integration-1C3C3C?style=for-the-badge" height="28" alt="LangChain">
  <img src="https://img.shields.io/badge/Pydantic_AI-Typed_Agents-E92063?style=for-the-badge&logo=pydantic&logoColor=white" height="28" alt="Pydantic AI">
  <img src="https://img.shields.io/badge/AWS_Bedrock-Managed_Inference-232F3E?style=for-the-badge&logo=amazonaws&logoColor=white" height="28" alt="AWS Bedrock">
  <img src="https://img.shields.io/badge/Llama_3.2-Self_Hosted-5B5BD6?style=for-the-badge" height="28" alt="Llama 3.2">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/GraphQL-On--Chain_Queries-E10098?style=for-the-badge&logo=graphql&logoColor=white" height="28" alt="GraphQL">
  <img src="https://img.shields.io/badge/Telegram-MCP_Connector-26A5E4?style=for-the-badge&logo=telegram&logoColor=white" height="28" alt="Telegram">
  <img src="https://img.shields.io/badge/Twitter%2FX-MCP_Connector-111111?style=for-the-badge&logo=x&logoColor=white" height="28" alt="Twitter X">
  <img src="https://img.shields.io/badge/Sentry-Observability-362D59?style=for-the-badge&logo=sentry&logoColor=white" height="28" alt="Sentry">
</p>

---

## THE PROBLEM

Crypto research is fragmented across blockchain explorers, token dashboards, market-data providers, social channels, Telegram groups, wallet-analysis tools, and trading interfaces.

A user investigating a token may need to:

- Inspect holders and wallet movements
- Evaluate liquidity, volume, routing, and pair activity
- Search Telegram and Twitter/X for breaking information
- Review contract and token-risk data
- Compare information across multiple chains
- Preserve the research as a repeatable workflow

Most AI assistants can explain crypto concepts or summarize webpages. They cannot reliably coordinate live on-chain queries, authenticated social sessions, structured APIs, workflow state, and user-approved actions inside one system.

---

## THE SOLUTION

SYNC used a supervisor-led multi-agent architecture to transform one request into a controlled sequence of research and automation steps.

<pre>
User Request
     ↓
Supervisor Agent
     ↓
Intent Classification + Argument Extraction
     ↓
Specialized Agent Selection
     ↓
Tool and Data Provider Execution
     ↓
Human Approval When Required
     ↓
Validation + Response Synthesis
</pre>

Each specialist had its own system prompt, tool registry, workflow state, validation rules, LangGraph execution path, and error-handling behavior.

The supervisor selected the correct specialist, extracted tool arguments, requested missing information, coordinated multi-step execution, and synthesized the final answer.

---

## SYSTEM ARCHITECTURE

## SYSTEM ARCHITECTURE

### 1. Overall System Architecture

<p align="center">
  <img
    src="./media/sync-overall-architecture.png"
    width="100%"
    alt="SYNC overall system architecture"
  >
</p>

A single homogeneous FastAPI application combined the supervisor, eight specialist agents, LangGraph workflows, tool registries, memory, automation, monitoring, model providers, and external data integrations.

---

### 2. Multi-Agent Orchestration & Tool Connections

<p align="center">
  <img
    src="./media/sync-agent-orchestration.png"
    width="100%"
    alt="SYNC multi-agent orchestration and tool connections"
  >
</p>

The supervisor classified each request, extracted arguments, and routed work to one or more specialist agents. Each agent maintained its own prompt, tools, workflow state, and LangGraph execution path before results were validated and synthesized.

---

### 3. Private Desktop vs Cloud Deployment

<p align="center">
  <img
    src="./media/sync-desktop-cloud-deployment.png"
    width="100%"
    alt="SYNC private desktop and cloud deployment architecture"
  >
</p>

The same application was delivered in two forms: a private Electron desktop build with a bundled React interface, local FastAPI backend, encrypted SQLite storage, and local vector database; and a cloud deployment using React, an AWS load balancer, ECS, PostgreSQL, and shared model services.

> Both deployment modes used the same core agent architecture and external integrations, with no microservices or API calls between agents.

---

## KEY ENGINEERING DECISIONS

| Decision | Why it mattered |
|---|---|
| **Supervisor-led routing** | Centralized intent detection and argument extraction, reducing unnecessary specialist-agent hops |
| **Deterministic LangGraph workflows** | Made multi-step execution testable, observable, recoverable, and easier to debug |
| **Agent-specific tool registries** | Reduced tool-selection ambiguity and constrained each agent to relevant capabilities |
| **Human approval gates** | Separated autonomous research from sensitive account, session, wallet, and trade actions |
| **Provider abstraction** | Allowed blockchain, market, search, and social providers to be combined or replaced without redesigning the agent system |
| **Local encrypted state** | Preserved user settings, sessions, secrets, and workflow context without exposing them in every model request |
| **Evaluation-first iteration** | Turned routing, tool selection, arguments, and response quality into measurable engineering targets |

---

## REPRESENTATIVE ORCHESTRATION PATTERN

> Simplified architectural example. This is not production source code.

```python
def execute_workflow(state: WorkflowState) -> WorkflowState:
    """Routes and executes one agent workflow."""
    decision = supervisor.route(
        request=state.request,
        context=state.context,
    )

    if decision.missing_fields:
        return state.request_input(decision.missing_fields)

    agent = agent_registry[decision.agent]
    result = agent.run(
        state=state,
        arguments=decision.arguments,
    )

    if result.requires_approval:
        return state.await_approval(result.pending_action)

    return synthesizer.build_response(state, result)
```

The production implementation used typed workflow state, agent-specific tool registries, validation, retry behavior, LangGraph nodes, and explicit approval checkpoints.

---

## LIVE ON-CHAIN DATA LAYER

SYNC did not depend solely on browser search. It combined structured providers, blockchain indexers, aggregators, and RPC infrastructure.

### Blockchain indexers and data providers

Custom SQL and GraphQL queries retrieved structured blockchain information including:

- Token holders
- Wallet activity
- Transfers and transactions
- DEX and liquidity-pair activity
- Token metadata
- Market signals
- Block-level information

Integrations included:

**Bitquery · Codex · Solscan · Etherscan · DefiLlama · GeckoTerminal · RugCheck · Jupiter**

### RPC and chain infrastructure

RPC access supported lower-level retrieval across Solana and EVM-style workflows, including transaction, block, wallet, token, and contract information.

This enabled SYNC to reason over live or near-real-time chain activity instead of relying only on articles and search-engine summaries.

### Market and execution infrastructure

Market-data and routing providers supplied:

- Prices
- Liquidity
- Pair information
- Transaction routes
- Token-risk signals
- Trade-support data

Sensitive buy or sell workflows remained behind explicit user-authorization gates.

---

## CONNECTED SOCIAL INTELLIGENCE

SYNC connected to user-authorized Telegram and Twitter/X sessions through dedicated connector workflows.

These connectors allowed agents to:

- Search relevant conversations and channels
- Collect recent project or market discussions
- Identify emerging information
- Summarize high-volume message streams
- Combine social context with blockchain and market data

Telegram login, OTP input, session access, and Twitter/X authentication required explicit human involvement.

<pre>
On-Chain Activity
      +
Market Data
      +
Telegram Intelligence
      +
Twitter/X Intelligence
      +
Live Web Research
      ↓
Unified Agent Response
</pre>

---

## WORKFLOWS AND AUTOMATION

Users could save repeatable multi-step processes and execute them manually or on a recurring schedule.

<pre>
Research Token
    ↓
Inspect Holders
    ↓
Review Wallet Activity
    ↓
Check Liquidity and Market Data
    ↓
Search Telegram and Twitter/X
    ↓
Generate Risk and Opportunity Summary
</pre>

Cron-style scheduling allowed saved workflows to run repeatedly for monitoring, research, and notification use cases.

---

## HUMAN-IN-THE-LOOP SAFETY

Sensitive operations required user confirmation.

Approval checkpoints covered:

- Trade authorization
- Telegram login and session access
- OTP entry
- Twitter/X session access
- Wallet-related operations
- Execution of sensitive saved workflows

The system separated research from execution so an agent-generated recommendation could not automatically become an irreversible action.

---

## MEMORY AND LOCAL DATA

SYNC used encrypted SQLite storage for:

- User settings
- API credentials
- Telegram sessions
- Twitter/X cookies
- Workflow state
- Local secrets
- Wallet-related configuration

Stored text embeddings supported retrieval of relevant user context and prior conversations.

This enabled personalization without injecting the entire conversation history into every request.

---

## ENGINEERING OUTCOMES

| Area | Result |
|---|---:|
| Platform adoption | **10,000+ signups** |
| Closed-beta usage | **800 active testers** |
| Agent architecture | **8 agents across 3 tiers** |
| External integrations | **15+ APIs and providers** |
| Routing and tool-call evaluation | **46% → 78%** |
| Average workflow latency | **~10s → ~6s** |

---

## RELIABILITY AND EVALUATION

A dedicated evaluation suite measured:

- Supervisor routing
- Agent selection
- Tool selection
- Argument extraction
- API-response handling
- Workflow completion
- Final-answer quality

Routing and tool-call evaluation improved from **46% to 78%** through failed-call analysis, prompt refinement, argument-validation fixes, routing changes, and expanded evaluation coverage.

Average workflow latency improved from approximately **10 seconds to 6 seconds** by restructuring the tool hierarchy and moving frequently used search tools into the supervisor registry, avoiding unnecessary specialist-agent hops.

The system also handled:

- Malformed API responses
- Missing arguments
- Timeouts
- Truncated outputs
- Unavailable providers
- Incorrect tool calls
- Partial workflow failures

Sentry monitoring with custom error codes tracked agent failures, backend exceptions, tool outcomes, API errors, and workflow success states.

---

## PRODUCT AND WORKFLOW PREVIEW

<p align="center">
  <!-- Replace with ./media/sync-product-collage.png -->
  <img
    src="https://placehold.co/1600x900/07110F/5EE6BC?text=SANITIZED+PRODUCT+AND+WORKFLOW+SHOWCASE"
    width="100%"
    alt="Sanitized SYNC product and workflow showcase"
  >
</p>

> Interfaces and outputs shown here should be sanitized, recreated, or explicitly approved for portfolio use.

A future collage can include:

- Sanitized chat interactions
- Onboarding screens
- Workflow configuration
- Agent-status interfaces
- Anonymized research outputs
- A simplified request-to-agent execution sequence

---

## MY CONTRIBUTION

### Architecture

Designed and helped refine the supervisor-led eight-agent architecture, workflow state model, tool hierarchy, and human-approval system.

### Backend and integrations

Built FastAPI services, LangGraph workflows, encrypted storage, retrieval memory, custom SQL and GraphQL queries, and 15+ blockchain, market, search, automation, and social integrations.

### Reliability

Developed agent evaluations, integration tests, Sentry observability, error handling, workflow recovery mechanisms, and routing/tool-call improvements.

### Product delivery

Contributed to React/Tailwind interfaces, onboarding, closed-beta iteration, technical demonstrations, architecture communication, and investor-facing product materials.

---

## PROJECT STATUS

<p>
  <img src="https://img.shields.io/badge/STATUS-CLOSED_BETA-16C79A?style=for-the-badge" alt="Closed beta">
  <img src="https://img.shields.io/badge/TYPE-PROPRIETARY-111111?style=for-the-badge" alt="Proprietary software">
  <img src="https://img.shields.io/badge/SOURCE-INTENTIONALLY_PRIVATE-555555?style=for-the-badge" alt="Source intentionally private">
</p>

> This repository is an engineering case study covering the product architecture, technical decisions, system capabilities, engineering outcomes, and my contributions.  
> Proprietary source code, production data, user information, credentials, and confidential implementation details are intentionally excluded.
