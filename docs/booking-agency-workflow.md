# Booking Agency Workflow

## Overview

A fully automated end-to-end booking agency management system built with n8n, replacing traditional manual agency operations. The system orchestrates a network of specialized AI agents that handle the complete lifecycle of a DJ/artist booking — from initial inquiry to post-event settlement.

## Architecture

The system is built on a **multi-agent architecture** using a NO-TOOL Flat JSON communication pattern, where a central Admin Agent coordinates a set of specialized sub-agents:

- **Admin Agent** — Central orchestrator, routing messages and coordinating agent responses
- **Booking Agent** — Handles incoming booking inquiries and availability checks
- **Contract Agent** — Generates and manages contract lifecycle (DRAFT → SENT → SIGNED)
- **Finance Agent** — Fee tracking, invoicing, payment monitoring
- **Logistics Agent** — Travel coordination and technical rider management
- **Artist Agent** — Artist communication and profile management
- **Promo/Social Agent** — Promotional material and social media coordination
- **Release Agent** — Music release coordination and scheduling

## Technical Stack

- **Agent Runtime**: OpenClaw
- **Database**: Supabase (PostgreSQL + pgvector for RAG)
- **Communication**: Email (primary), WhatsApp Business API (Phase 2)
- **AI/LLM**: OpenAI GPT-4, Claude (via API)
- **Contract Generation**: PDF generation with e-signature workflow
- **Infrastructure**: Docker (local), cloud-deployable

## Key Features

- Automated email parsing for incoming booking requests
- AI-driven intent classification and routing
- Contract PDF generation and email-based signature workflow
- Supabase-backed state management for all bookings, artists, and contracts
- Structured agent-to-agent communication via flat JSON messages
- Multi-channel support (Email + WhatsApp)
- Automated test loop with documented testing sessions

## Development Status

Fully migrated to OpenClaw and productive. All agents are implemented and operational end-to-end.

## Skills Demonstrated

Business process automation, multi-agent orchestration, API integration, prompt engineering, production-grade error handling, Supabase/PostgreSQL schema design, OpenClaw agent runtime.

## Workflow Diagram

For a visual overview of the agent architecture, see the [Booking Agency Workflow diagram](../../assets/diagrams/Booking_Agency_Linear.png).
