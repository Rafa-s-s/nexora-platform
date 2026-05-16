# Nexora SaaS Structure

This document describes the SaaS architecture and subscription model of the Nexora Platform.

The platform was designed to operate as a scalable multi-tenant SaaS solution focused on WhatsApp automation, AI-assisted support and conversation management for organizations and businesses.

---

# SaaS Concept

Nexora operates as a subscription-based platform where each organization has its own isolated environment inside the system.

Each organization may have:

- administrators
- WhatsApp channels
- chatbot configuration
- FAQ structure
- projects
- volunteers
- donations
- conversations
- AI configuration
- subscription plan

This architecture allows multiple organizations to use the platform simultaneously while keeping data isolated and secure.

---

# Multi-Tenant Structure

The database architecture was designed around a multi-tenant model.

The `ONG` entity acts as the tenant owner.

All operational entities are connected to organizations, including:

- conversations
- messages
- FAQ records
- projects
- administrators
- donations
- volunteer registrations
- bot configuration
- subscriptions

This structure allows Nexora to scale efficiently as the number of organizations grows.

---

# Organization Registration Flow

The SaaS onboarding flow begins with organization registration.

Example flow:

```txt
Landing Page
    ↓
Create Account
    ↓
Register Organization
    ↓
Create Administrator
    ↓
Select Plan
    ↓
Activate Subscription
    ↓
Access Dashboard
```

The platform automatically creates the organization environment after registration.

---

# Administrator Structure

Organizations can create internal users to access the dashboard.

Possible access levels:
- admin
- support agent
- viewer

Administrators are isolated per organization.

This prevents users from accessing data from other organizations.

---

# Subscription Plans

Nexora was designed to support multiple SaaS plans.

Possible plans include:

---

## Starter Plan

Designed for small organizations that need basic WhatsApp automation.

Possible features:
- chatbot menu
- FAQ responses
- basic dashboard
- limited conversations

---

## Professional Plan

Designed for organizations requiring advanced operational control.

Possible features:
- full dashboard
- multiple administrators
- human support management
- project management
- advanced workflows

---

## Premium AI Plan

Designed for organizations requiring AI-powered support automation.

Possible features:
- AI-assisted conversations
- advanced intent detection
- contextual responses
- enhanced automation
- scalable support flows

---

# Subscription Lifecycle

The platform controls the complete subscription lifecycle.

Possible states:
- trial
- active
- pending payment
- overdue
- canceled
- blocked

The SaaS structure supports trial periods before billing activation.

---

# Trial System

Organizations may receive a free trial period during onboarding.

Example trial flow:

```txt
Organization Registration
        ↓
Trial Activated
        ↓
Dashboard Access
        ↓
Trial Expiration
        ↓
Subscription Required
```

This allows organizations to test the platform before purchasing a paid plan.

---

# Stripe Integration

Stripe is used as the primary payment infrastructure.

Responsibilities include:
- recurring subscriptions
- billing management
- checkout sessions
- payment status
- invoice handling

Possible payment methods:
- credit card
- PIX
- boleto (future possibility)

---

# Payment Structure

The platform stores payment-related information including:

- gateway identifiers
- payment status
- billing links
- subscription identifiers
- payment method
- billing history

This structure allows Nexora to evolve into a fully commercial SaaS operation.

---

# Dashboard Access Control

Dashboard access depends on:
- active administrator status
- active subscription status
- valid authentication session

The system may restrict access if:
- subscription expires
- payment fails
- organization is blocked

---

# WhatsApp Session Structure

Each organization may connect its own WhatsApp session through WAHA.

This allows:
- organization isolation
- independent support operation
- scalable communication channels

Each WhatsApp session is linked to:
- one organization
- one chatbot configuration
- one operational dashboard

---

# AI Configuration Per Organization

Each organization may configure:
- bot name
- AI prompt
- support hours
- AI activation status

This allows personalized chatbot behavior for each customer.

---

# Scalability Vision

The SaaS architecture was designed to support future growth.

Planned scalability goals:
- cloud deployment
- scalable containers
- multiple WhatsApp instances
- distributed infrastructure
- AI scaling
- advanced analytics
- white-label support

---

# Security and Isolation

The platform was designed with organizational isolation as a core principle.

Main security concepts:
- tenant isolation
- access levels
- session control
- audit logs
- encrypted passwords
- controlled AI access
- LGPD-aware structure

---

# Future SaaS Features

Planned future SaaS improvements include:

- analytics dashboard
- AI conversation insights
- organization metrics
- white-label platform
- advanced billing
- team permissions
- automation templates
- workflow marketplace
- API integrations

---

# Revenue Potential

Nexora was designed as a recurring revenue SaaS model.

Possible monetization strategies:
- monthly subscriptions
- AI feature upgrades
- premium plans
- onboarding services
- automation templates
- white-label licensing

The platform may serve:
- NGOs
- small businesses
- support teams
- clinics
- schools
- service providers
- community organizations

---

# Product Vision

The long-term vision of Nexora is to become a scalable WhatsApp-first automation platform combining:

- chatbot automation
- AI assistance
- human support
- operational dashboards
- subscription infrastructure
- accessible communication

The goal is to simplify support operations while improving communication efficiency and accessibility.

---

# Conclusion

The Nexora SaaS structure was designed to provide a scalable, accessible and commercially viable platform capable of supporting organizations through intelligent WhatsApp automation and AI-assisted communication workflows.
