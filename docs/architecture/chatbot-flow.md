# Nexora Chatbot Flow

This document describes the logical conversation flow used by the Nexora Platform chatbot.

The chatbot was designed to provide accessible, fast and intelligent support through WhatsApp while maintaining the possibility of human assistance when necessary.

---

# Main Objectives

The chatbot flow was designed to:

- simplify communication
- reduce repetitive support overload
- improve accessibility
- automate common requests
- organize conversations
- support human handoff
- integrate AI assistance safely

---

# Initial User Interaction

The conversation begins when a user sends a message through WhatsApp.

Example:

```txt
Hello
```

The Nexora platform receives the message through WAHA and processes the request using n8n workflows.

---

# Main Menu Flow

After the first interaction, the chatbot presents the main menu.

Example:

```txt
Welcome to Nexora Support.

Please choose an option:

1. I want to donate
2. I want to volunteer
3. Information about projects
4. Talk to a human assistant
```

This menu represents the initial routing layer of the system.

---

# Donation Flow

If the user selects the donation option, the chatbot provides information about donation methods.

Possible responses include:

- PIX instructions
- donation contact information
- donation types
- event campaigns
- organization details

The system may also register donation interest in the database.

Example status:
- donation_pending
- donation_registered

---

# Volunteer Flow

If the user selects the volunteer option, the chatbot collects volunteer-related information.

Possible collected data:
- name
- WhatsApp number
- area of interest
- availability

Example volunteer areas:
- events
- logistics
- education
- communication

The information is stored for organization review.

---

# Social Projects Flow

The chatbot can present information about the organization's active projects.

Possible information:
- project description
- active campaigns
- project objectives
- event schedules
- organization initiatives

This information can be dynamically loaded from the database.

---

# FAQ Flow

The chatbot uses FAQ records to answer repetitive questions automatically.

Examples:
- opening hours
- address
- how to donate
- volunteer requirements
- support information

FAQ responses can be:
- static
- AI-assisted
- organization-specific

---

# AI Assistance Flow

When the user sends messages outside the predefined menu, the AI layer may assist the conversation.

Example:

```txt
How can I help your organization?
```

The AI attempts to:
- understand user intent
- answer contextually
- maintain conversation flow
- avoid unrelated responses

The AI operates under controlled prompts defined by the organization.

---

# Intent Detection

The Nexora platform stores the detected user intention inside the conversation structure.

Possible detected intentions:
- donation
- volunteer
- FAQ
- social projects
- human support
- unknown

This information helps the platform decide how the conversation should continue.

---

# Fallback Flow

When the system cannot understand the message, the chatbot activates a fallback response.

Example:

```txt
Sorry, I couldn't understand your message.

Please choose one of the available menu options or type 4 to talk to a human assistant.
```

The fallback prevents the chatbot from becoming unusable during unexpected interactions.

---

# Human Support Flow

If the user requests human assistance or the AI cannot safely continue the conversation, the chatbot creates a human support request.

Flow:
1. conversation status changes
2. support request is created
3. administrator sees pending support
4. administrator assumes conversation
5. human support becomes active

The dashboard reflects:
- waiting support
- assigned support
- active human support
- finalized support

---

# Conversation Lifecycle

A conversation may transition through multiple states.

Example lifecycle:

```txt
started
   ↓
menu_active
   ↓
faq_response
   ↓
ai_assistance
   ↓
waiting_human_support
   ↓
human_support_active
   ↓
conversation_closed
```

---

# Accessibility Principles

The chatbot flow was designed with accessibility in mind.

Key principles:
- short messages
- simple language
- guided interaction
- low cognitive complexity
- WhatsApp-first communication
- reduced dependency on websites

This helps users with low digital familiarity interact more easily.

---

# Multi-Organization Structure

Each organization may have:
- custom FAQ
- custom projects
- custom prompts
- custom support flow
- custom WhatsApp session

The chatbot flow dynamically adapts based on the organization context.

---

# Security and Data Awareness

The chatbot flow respects basic privacy and LGPD principles.

Examples:
- minimal data collection
- explicit consent flows
- support traceability
- organization isolation
- controlled AI context

---

# Future Improvements

Planned future enhancements include:

- voice interaction
- advanced AI context memory
- analytics
- smart routing
- sentiment detection
- multi-language support
- advanced workflow customization

---

# Conclusion

The Nexora chatbot flow combines automation, AI assistance and human support into a structured WhatsApp-first communication system designed for accessibility, scalability and operational simplicity.
