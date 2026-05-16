# Nexora MVP Roadmap

This document describes the MVP (Minimum Viable Product) roadmap of the Nexora Platform.

The MVP was designed to validate the core functionality of the platform while maintaining low operational complexity and development cost.

The initial version focuses on WhatsApp automation, AI-assisted support and human support handoff for organizations and NGOs.

---

# MVP Objective

The main goal of the MVP is to prove that Nexora can:

- automate WhatsApp communication
- organize conversations
- reduce repetitive support overload
- support donation and volunteer flows
- provide AI-assisted responses
- allow human support escalation
- operate through a centralized dashboard

---

# MVP Scope

The MVP focuses on the essential operational flow of the platform.

Included features:

- WhatsApp integration
- chatbot menu
- FAQ automation
- conversation history
- human support routing
- AI-assisted responses
- organization dashboard
- SaaS onboarding structure
- login and registration system

---

# MVP Architecture

The MVP architecture combines low-cost and scalable technologies.

Main technologies:

- WAHA
- n8n
- Docker
- PostgreSQL
- TypeScript
- Stripe
- Gemini / OpenAI integration

---

# Development Stages

## Stage 1 — Environment Preparation

### Goals

- install Docker
- configure WAHA
- configure n8n
- validate local environment
- prepare WhatsApp integration

### Expected Result

Stable communication infrastructure.

---

## Stage 2 — WhatsApp Integration

### Goals

- connect WhatsApp number
- validate message sending
- validate message receiving
- create initial test flow

### Expected Result

The platform successfully exchanges WhatsApp messages.

---

## Stage 3 — Chatbot Core Flow

### Goals

- create initial menu
- create conversation routing
- implement fallback flow
- implement FAQ responses

### Planned Menu

```txt
1. I want to donate
2. I want to volunteer
3. Information about projects
4. Talk to a human assistant
```

### Expected Result

Functional automated WhatsApp support.

---

## Stage 4 — Dashboard Implementation

### Goals

- create dashboard layout
- create conversations panel
- create messages visualization
- create FAQ management
- create support management

### Expected Result

Organizations can monitor and manage conversations.

---

## Stage 5 — Human Support System

### Goals

- create support request flow
- create “assume conversation” functionality
- create support status tracking
- link conversations to administrators

### Expected Result

The platform supports hybrid AI + human assistance.

---

## Stage 6 — AI Integration

### Goals

- integrate Gemini or OpenAI
- create controlled prompts
- implement intent detection
- create fallback logic
- improve conversational flexibility

### AI Rules

The AI must:
- stay inside organization context
- avoid invented information
- redirect uncertain situations to human support

### Expected Result

More natural conversations.

---

## Stage 7 — SaaS Structure

### Goals

- create login flow
- create organization registration
- implement plans
- integrate Stripe
- create subscription logic

### Expected Result

Organizations can subscribe and access the platform independently.

---

## Stage 8 — Data Organization

### Goals

- store conversations
- store messages
- register volunteer interests
- register donations
- implement LGPD consent logic

### Expected Result

Structured operational database.

---

## Stage 9 — Testing and Validation

### Goals

- validate chatbot flows
- validate AI responses
- validate dashboard usability
- test human support flow
- validate WhatsApp communication
- identify bugs

### Expected Result

Stable MVP ready for demonstration.

---

# Accessibility Focus

The MVP prioritizes accessible communication.

Main principles:

- simple language
- intuitive flow
- short responses
- WhatsApp-first interaction
- reduced complexity

This approach helps users with low digital familiarity interact more easily.

---

# Security Considerations

The MVP already includes basic security concepts such as:

- password hashing
- session control
- organization isolation
- administrator access levels
- audit logs
- LGPD-aware data handling

---

# Current MVP Status

Current implementation status:

| Component | Status |
|---|---|
| Database Modeling | Completed |
| SaaS Structure Planning | Completed |
| Dashboard Wireframes | In Progress |
| Stripe Setup | In Progress |
| Login System | In Development |
| WhatsApp Integration | In Development |
| n8n Workflows | In Development |
| AI Integration | Planned |
| Human Support Logic | Planned |
| Final Tests | Planned |

---

# Expected MVP Demonstration

The MVP demonstration aims to show:

- WhatsApp chatbot working
- menu interaction
- FAQ automation
- AI-assisted response
- human support handoff
- dashboard conversation visualization
- SaaS onboarding structure

---

# Future Expansion After MVP

After validating the MVP, Nexora may evolve into:

- scalable SaaS infrastructure
- advanced AI assistant
- white-label platform
- analytics dashboard
- automation templates
- workflow marketplace
- cloud deployment

---

# MVP Philosophy

The MVP was intentionally designed to:

- validate the business idea quickly
- minimize infrastructure costs
- simplify implementation
- prioritize usability
- focus on real operational problems

The goal is not to build a perfect system initially, but to create a functional and scalable foundation.

---

# Conclusion

The Nexora MVP roadmap establishes the first operational foundation of the platform, combining WhatsApp automation, AI assistance and SaaS concepts into an accessible and scalable communication solution.
