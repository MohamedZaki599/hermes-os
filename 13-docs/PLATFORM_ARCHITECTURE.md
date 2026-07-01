# Hermes OS Platform Architecture

> Version: 1.0
> Status: Active
> Owner: Mohamed Zaki
> Last Updated: 2026-07-01

---

# Purpose

This document defines the high-level architecture of Hermes OS.

It explains:

- System philosophy
- Core services
- Infrastructure decisions
- Communication flow
- Responsibilities of each component

This document is the architectural reference for every future feature.

---

# Vision

Hermes OS is **not** an AI Agent.

Hermes OS is an AI Operating System.

It coordinates:

- AI Models
- AI Agents
- Workflows
- Knowledge
- Memory
- Projects
- Business Operations

The goal is to become Mohamed's autonomous AI company.

---

# Core Philosophy

Hermes OS follows one rule:

> Hermes OS owns the system.
>
> AI Agents execute tasks.

Hermes Agent is **replaceable**.

Hermes OS is not.

---

# Architecture Layers

```
                    User
                      │
                      ▼
               Telegram / Dashboard
                      │
                      ▼
                Hermes OS (Brain)
                      │
 ┌────────────────────┼────────────────────┐
 │                    │                    │
 ▼                    ▼                    ▼
Knowledge         Departments         Workflows
Memory              Router            Integrations
                      │
                      ▼
              Hermes Agent
                      │
                      ▼
         LLM Providers + MCP Servers
                      │
                      ▼
          External APIs & Tools
```

---

# Repository Structure

```
/opt/hermes

apps/
    hermes-os
    hermes-agent

configs/

docker/

data/

logs/

backups/

workspace/

scripts/
```

---

# Infrastructure Components

## PostgreSQL

Purpose:

- User Data
- Memory
- Tasks
- Projects
- Workflows
- Metadata

PostgreSQL is the primary database.

---

## Redis

Purpose:

- Event Bus
- Queue
- Cache
- Real-time communication

Redis is **not only cache**.

It is also the communication layer.

---

## Qdrant

Purpose:

- Semantic Search
- Long-term Knowledge
- Embeddings

No operational state should be stored inside Qdrant.

Only vector knowledge.

---

## Caddy

Purpose:

- Reverse Proxy
- HTTPS
- Automatic TLS
- Routing

---

## Docker

Docker owns the platform.

Services never run directly on Ubuntu.

Everything runs inside containers.

---

# Hermes OS Responsibilities

Hermes OS is responsible for:

- Routing
- Planning
- Department Coordination
- Memory
- Knowledge
- Scheduling
- AI Provider Selection
- Configuration
- Authentication

---

# Hermes Agent Responsibilities

Hermes Agent executes:

- Skills
- Tools
- MCP Servers
- Code Tasks
- Research
- Automation

Hermes Agent never owns business logic.

---

# AI Router

Hermes OS decides which provider should execute each task.

Possible providers:

- Google Gemini
- OpenRouter
- Cloudflare Workers AI
- OpenAI
- Local Models

The Agent never selects providers directly.

---

# Knowledge Architecture

Knowledge lives inside:

```
02-knowledge/
```

Operational Memory lives inside PostgreSQL.

Semantic Memory lives inside Qdrant.

---

# Workspace

Workspace is not source code.

Workspace contains active projects.

```
workspace/

BizLens/

SmartLunch/

Future Projects/
```

Hermes reads and modifies files inside Workspace.

---

# Future Services

Planned Services

- Telegram Gateway
- Dashboard
- Monitoring
- Voice
- Email
- Calendar
- Finance
- CRM

---

# Guiding Principles

1. Hermes OS owns the architecture.
2. Agents are replaceable.
3. Infrastructure is modular.
4. Everything is documented.
5. Every decision must have a reason.
6. No hidden knowledge.
7. AI augments human decisions, not replaces them.

---

# End of Document