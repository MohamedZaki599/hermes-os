# Project Structure

Version: 1.0

Status: Foundational

---

# Purpose

This document explains the repository organization of Hermes OS.

Folders represent business capabilities rather than technical layers.

Every directory has a clear responsibility.

---

# Root Structure

01-core

Core runtime of Hermes.

Contains the kernel of the system.

---

02-knowledge

Business knowledge.

Projects.

Playbooks.

Research.

Documentation.

---

03-persona

Founder identity.

Goals.

Preferences.

Operating profile.

---

04-departments

Business departments.

CEO

COO

CTO

Marketing

Research

Sales

Life

Finance

---

05-skills

Reusable capabilities.

Coding.

Writing.

Research.

Planning.

Marketing.

Analysis.

---

06-workflows

Business processes.

Daily planning.

Client onboarding.

Product development.

Reflection.

Weekly review.

---

07-integrations

External systems.

Telegram

GitHub

Google

OpenRouter

Cloudflare

Vercel

DigitalOcean

---

08-memory

Persistent memory.

Working.

Long-Term.

Patterns.

Projects.

Clients.

---

09-prompts

Reusable prompt library.

System prompts.

Department prompts.

Templates.

---

10-templates

Business templates.

Proposal.

Invoice.

PRD.

Landing Page.

Email.

---

11-assets

Images.

Icons.

Branding.

Diagrams.

---

12-configs

Configuration.

Routing.

Providers.

Environment.

---

13-docs

Architecture.

Vision.

Identity.

Documentation.

Specifications.

---

14-roadmap

Roadmap.

Milestones.

Future plans.

---

# Design Rules

Folders represent responsibilities.

Not technologies.

---

Dependencies should flow downward.

Core should never depend on Departments.

Departments should never depend on Providers.

Providers should never contain business logic.

---

Business knowledge lives in Knowledge.

Personal context lives in Persona.

Operational history lives in Memory.

Execution logic lives in Core.

---

# Repository Philosophy

Hermes is organized like a company.

Not like a web application.

Every folder represents an organizational responsibility.

This makes the architecture scalable, understandable, and maintainable.