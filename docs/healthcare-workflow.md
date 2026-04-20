# Healthcare Workflow — Dermatology Practice Automation

## Overview

An intelligent automation system built for a dermatological practice, designed to reduce administrative overhead and streamline patient communication. This was an early agentic workflow project, developed at the start of my journey into AI-powered automation — demonstrating the application of LLMs and RAG to a regulated, real-world healthcare environment.

## Problem Statement

The practice required a significant reduction in manual administrative work across appointment scheduling, patient communication, document management, and clinical knowledge retrieval. Staff time was disproportionately consumed by repetitive, rule-based tasks that could be automated safely.

## Solution

An n8n-based workflow system with an integrated RAG (Retrieval Augmented Generation) layer:

- **Appointment Scheduling Automation** — Automated handling of scheduling requests via email, with calendar integration and confirmation dispatch
- **Patient Communication** — Template-driven, context-aware email responses for common inquiries
- **Document Management** — AI-assisted processing and routing of incoming documents and referrals
- **Medical Knowledge Base** — Supabase pgvector-backed RAG system storing clinical guidelines, protocols, and FAQs for AI-assisted decision support
- **Decision Logic** — Conditional routing based on patient status, appointment type, and urgency classification

## Technical Stack

- **Workflow Automation**: n8n
- **Vector Database**: Supabase (pgvector for semantic search)
- **LLM**: OpenAI GPT-4 (document processing, response generation)
- **RAG Pipeline**: Embedding-based retrieval for medical protocol lookups
- **Communication**: Email integration (SMTP/IMAP)

## Outcome

Achieved approximately 30% reduction in administrative workload. The system was deployed for a real patient environment, requiring particular attention to data privacy, response accuracy, and reliability. Edge case handling and graceful fallbacks to human review were core design requirements.

## Key Learning

This project was foundational in establishing patterns I've since applied across more complex systems: structured prompt engineering, RAG pipeline design, error handling in production workflows, and the discipline of designing for non-technical end users in sensitive domains.

## Skills Demonstrated

RAG system design, Supabase/pgvector integration, prompt engineering for structured outputs, n8n workflow architecture, healthcare data sensitivity awareness, production deployment for real users.
