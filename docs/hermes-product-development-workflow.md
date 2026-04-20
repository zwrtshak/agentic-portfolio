# Hermes Product Development Workflow

## Overview

A comprehensive AI-powered product management framework built on the Hermes agent architecture. The system models a complete product development organization: a Product Manager agent coordinates a set of specialized sub-agents, each equipped with domain-specific skills, enabling end-to-end product development from ideation through delivery.

## Concept

Traditional product management involves coordinating across multiple disciplines — product strategy, engineering, marketing, QA, and stakeholder communication. This framework replicates that coordination structure in an agentic system, where a central PM agent delegates to capable sub-agents rather than human team members.

The key innovation is **skill-equipped agents**: each sub-agent is not only role-assigned but carries a dedicated skill set (e.g., a Marketing Agent with copywriting + SEO skills, a Coding Agent with architecture + code review skills), making their outputs significantly more specialized and actionable than generic LLM responses.

## Architecture

### Orchestrator
- **Product Manager Agent** — Maintains project state, decomposes objectives into tasks, routes work to appropriate sub-agents, consolidates outputs, and manages the overall development plan

### Sub-Agents

| Agent | Skills |
|---|---|
| Coding Agent | Software architecture, code generation, code review, debugging |
| Marketing Agent | Copywriting, market positioning, campaign planning, SEO |
| QA Agent | Test case design, acceptance criteria, bug analysis |
| Documentation Agent | Technical writing, user guides, API docs |

### Planning Layer
- Project state tracked in a structured plan (milestones, tasks, assignments, status)
- PM Agent reads and updates the plan at each coordination step
- Agents receive task context + relevant skill instructions in their system prompts

## Technical Stack

- **Agent Framework**: Hermes Agent
- **Orchestration**: Multi-agent coordination with structured message passing
- **State Management**: Persistent project plan document updated by PM Agent
- **Memory**: Hermes native self-learning capabilities with persistent agent memory
- **Personal Knowledge Base**: Obsidian Brain — Markdown-based knowledge store holding personal style, experience, specs, and preferences, accessible to agents as a structured memory layer
- **LLM Backend**: OpenAI GPT-4 / Claude (configurable per agent)
- **Skill Injection**: Domain-specific skill documents loaded into agent context

## Key Design Decisions

- **Hermes over OpenClaw**: The PM Agent was initially considered for OpenClaw, but Hermes was chosen for its superior self-learning capabilities and persistent memory — critical for a product management context where continuity across sessions directly affects output quality
- **Obsidian as Brain**: Personal style, past experiences, technical specs, and preferences are stored as Markdown files in Obsidian and fed into the relevant agent contexts, creating a personalized knowledge layer that improves output consistency over time
- **Skills as context, not code**: Agent skills are implemented as structured prompt documents injected at runtime, making them easy to update and version without code changes
- **PM as single source of truth**: All project state flows through the PM Agent, preventing inconsistent state across sub-agents

## Status

Currently in active development. The framework architecture is defined and the PM + Coding Agent + Marketing Agent coordination loop is being implemented and tested.

## Skills Demonstrated

Multi-agent system design, agent orchestration patterns, prompt engineering for role-specific agents, product management process modeling, Hermes agent framework, iterative agentic workflow development.

## Related

The Coding Agent in this framework evolved from an earlier Scrum-based multi-agent workflow. For reference, see the [Coding Workflow diagram](../../assets/diagrams/Coding_Workflow.png).
