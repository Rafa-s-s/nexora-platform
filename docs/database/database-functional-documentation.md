# Nexora Functional Database Documentation

This document explains the purpose and functionality of the Nexora Platform database structure.

The database was designed to support:

- Multi-organization SaaS structure
- WhatsApp conversation management
- AI-powered chatbot flows
- Human support handoff
- FAQ automation
- Volunteer and donation management
- Subscription and payment systems
- LGPD-aware data handling

---

# Core System Structure

The Nexora database is centered around organizations (ONGs), administrators and WhatsApp conversations.

Each organization has its own:

- administrators
- WhatsApp channels
- conversations
- FAQ records
- projects
- volunteers
- donations
- bot configurations
- subscription data

This architecture allows Nexora to operate as a scalable multi-tenant SaaS platform.

---

# Main Database Entities

## ONG

Represents the organization or company using the platform.

Stores:
- organization data
- contact information
- identification records

Main usage:
- dashboard ownership
- subscription ownership
- WhatsApp channel ownership
- project management

---

## Administrador

Represents internal users who can access the Nexora dashboard.

Supports:
- authentication
- access control
- human support assignment
- audit tracking

Access levels may include:
- admin
- support agent
- viewer

---

## Usuario

Represents the WhatsApp user interacting with the chatbot.

Can represent:
- donors
- volunteers
- collaborators
- general users

Main purpose:
- conversation tracking
- donation flows
- volunteer registration

---

## Conversa

Represents a WhatsApp support session between a user and an organization.

Tracks:
- conversation status
- AI flow state
- detected intent
- WhatsApp channel
- human support state

Example statuses:
- in progress
- waiting human support
- human support active
- closed

---

## Mensagem

Stores all messages exchanged during conversations.

Supports:
- text
- audio
- image
- document
- system messages

Also differentiates message direction:
- incoming
- outgoing
- AI
- human
- system

---

## Atendimento_Humano

Controls conversations transferred to real human support.

Tracks:
- assigned administrator
- support status
- transfer reason
- support lifecycle

This table is essential for hybrid support logic.

---

## FAQ

Stores frequently asked questions used by the chatbot and AI.

Examples:
- donation instructions
- opening hours
- addresses
- volunteer information

FAQs can be enabled or disabled dynamically.

---

## Voluntario

Stores volunteer applications and interest records.

Tracks:
- area of interest
- availability
- application status

---

## Doacao

Stores donation intentions or donation records.

Possible donation types:
- PIX
- money
- food
- clothes
- materials

Supports anonymous donation scenarios.

---

## Projeto_Social

Stores social projects managed by organizations.

Allows chatbot and dashboard to present:
- project descriptions
- status
- active campaigns
- events

---

## Configuracao_Bot

Stores chatbot and AI behavior settings.

Controls:
- bot identity
- AI prompt
- support hours
- AI activation status

---

## Sessao_Login

Stores administrator authentication sessions.

Supports:
- login persistence
- security
- access control
- session expiration

---

## Consentimento_LGPD

Stores user consent records related to data processing.

Supports LGPD-aware flows such as:
- volunteer registration
- donations
- contact authorization

---

## Log_Auditoria

Stores important dashboard actions for traceability and security.

Examples:
- FAQ changes
- project edits
- support actions
- bot configuration changes

---

# SaaS and Billing Structure

## Plano

Defines available SaaS plans.

Controls:
- monthly pricing
- AI access
- admin limits
- conversation limits

---

## Assinatura

Represents an organization's active subscription.

Tracks:
- subscription status
- trial period
- billing cycle
- cancellation

---

## Pagamento

Stores payment records associated with subscriptions.

Supports integration with:
- Stripe
- Mercado Pago
- other payment gateways

Tracks:
- payment status
- checkout links
- payment method
- gateway identifiers

---

# System Design Goals

The database was designed with focus on:

- scalability
- SaaS architecture
- organization isolation
- accessibility
- automation
- AI integration
- human support integration
- low operational cost
- maintainability

---

# Conclusion

The Nexora database structure was designed not only to support chatbot automation, but also to provide the foundation for a scalable SaaS platform capable of managing organizations, WhatsApp communication, AI-powered support and subscription-based services.
