# From Workflow Automation to Agentic Systems

## Overview

A reflection on the architectural evolution across my projects — from structured n8n workflow automation toward fully agentic systems built with OpenClaw and Hermes. This transition represents both a technical shift and a change in how I think about automating complex, dynamic processes.

## The Evolution

### Phase 1: n8n Workflow Automation
My first generation of production systems was built entirely in n8n. The Booking Agency Workflow is the primary example: a multi-agent system with Admin, Booking, Contract, Finance, Logistics, Artist, and Promo agents — all coordinated through n8n's node-based workflow engine.

**Strengths of the n8n approach:**
- Visual workflow editor made architecture legible to non-engineers
- Solid integration library (email, webhooks, databases, APIs)
- Reliable trigger/execution model for event-driven processes
- Strong for well-defined, linear or branching business processes

**Limitations encountered:**
- Agent-to-agent communication felt constrained by the node graph model
- Dynamic, context-dependent routing required complex workarounds
- System prompts and agent logic lived inside node parameters — difficult to version and maintain
- Agentic loops (an agent deciding its own next step) were architecturally awkward

### Phase 2: OpenClaw for Agentic Runs
The Booking Agency Workflow was rebuilt and extended using **OpenClaw** — an agentic runtime that enables longer-horizon, tool-using agent runs via messenger-channel interaction. This shift enabled:

- More natural agent-to-agent communication patterns
- Dynamic tool selection at runtime rather than pre-wired node connections
- Longer execution contexts with heartbeat and state management
- Model flexibility (switchable between OpenAI Codex, GPT-4, etc.)

OpenClaw's architecture is better suited to processes where the agent needs to reason about what to do next, rather than following a pre-defined execution graph.

### Phase 3: Hermes Agent Framework
The Scrum/coding workflow I had previously prototyped in n8n (with Scrum Brain, Product Owner, Scrum Master, Developer agents coordinated via a live log dashboard) is now being re-implemented using the **Hermes agent framework**.

Hermes provides:
- Native multi-agent coordination with structured skill injection
- PM/orchestrator agent that reads and updates a persistent project plan
- Sub-agents with domain-specific skill sets loaded as context documents
- Cleaner separation between orchestration logic and agent capabilities

## Architectural Comparison

| Dimension | n8n | OpenClaw | Hermes |
|---|---|---|---|
| Workflow definition | Visual node graph | Conversational / tool-driven | Code + prompt documents |
| Agent communication | Node connections | Message passing | Structured agent calls |
| Dynamic routing | Complex workarounds | Native | Native |
| Skill/prompt management | Inside node params | Config files | Skill document injection |
| Best for | Event-driven integrations | Agentic long-horizon tasks | Multi-agent product workflows |

## Key Insight

n8n remains the right tool for integration-heavy, event-driven automation with well-defined process flows. As the complexity of agent reasoning increases — particularly in systems where agents must plan, adapt, and coordinate dynamically — dedicated agentic runtimes like OpenClaw and Hermes are architecturally superior.

The transition is not a rejection of workflow automation, but a recognition that different problem classes require different tools. The patterns learned in n8n (structured state management, agent role separation, error handling, testing discipline) transfer directly and remain foundational regardless of the runtime.

## Skills Demonstrated

Architectural decision-making, multi-agent system design, agentic runtime evaluation, n8n expertise, OpenClaw and Hermes agent frameworks, iterative technical migration, production system evolution.
