# AI Customer Support Escalation Workflow (n8n)

## Video Demo

Google Drive Video Demo:
https://drive.google.com/drive/folders/1IDEPG86ceJPzvGYRbBSJV97SWuOF8u5-?usp=drive_link

---

# Project Overview

This project implements an **Agentic Customer Support Automation Workflow** using **n8n**, AI agents, HTTP APIs, and Telegram integration.

The workflow is designed to automatically resolve routine customer support requests while escalating sensitive or low-confidence cases to human support teams.

Instead of relying on a single AI prompt, the workflow decomposes responsibilities into multiple AI and deterministic steps to improve reliability, explainability, and control.

---

# Problem Statement

Customer support teams receive both repetitive and high-risk requests.

Examples of routine requests include:

* Password reset
* Delivery questions
* General account inquiries

Examples of high-risk requests include:

* Refund requests
* Payment disputes
* Customer complaints
* Escalation scenarios

Handling every request manually reduces efficiency and increases response time.

At the same time, fully automated responses may generate incorrect decisions.

This workflow balances both approaches using **confidence-based routing** and **human review**.

---

# Target Users

* Customer support teams
* Service-based businesses
* Organizations managing customer requests

---

# Workflow Goal

Automatically resolve routine customer support requests and escalate uncertain or sensitive cases to human support teams.

---

# Expected Output

Low-risk requests:

→ Automatically resolved and customer notified.

High-risk requests:

→ Escalated to support team with context for manual review.

---

# Workflow Architecture

Ticket Intake (Webhook)

↓

Prepare Customer Data

↓

Support Response Generator (AI)

↓

Response Quality Reviewer (AI)

↓

Confidence Evaluator (AI)

↓

Resolution Router (Deterministic Logic)

TRUE → Notify Support → Store Ticket

FALSE → Resolution Generator → Notify Customer

---

# Workflow Explanation

## 1. Ticket Intake (Webhook)

Receives customer requests through a webhook endpoint.

Input includes:

* Customer name
* Email
* Support request

---

## 2. Prepare Customer Data

Normalizes and structures customer information before processing.

---

## 3. Support Response Generator (AI)

Responsible for:

* Understanding customer requests
* Generating structured responses

Output is returned in JSON format.

---

## 4. Response Quality Reviewer (AI)

Responsible for:

* Reviewing AI-generated responses
* Preventing unreliable outputs

This acts as a second validation layer.

---

## 5. Confidence Evaluator (AI)

Responsible for:

* Measuring confidence
* Determining whether automation is safe

---

## 6. Resolution Router (Deterministic Logic)

Routes workflow execution based on confidence thresholds.

Possible outcomes:

* Auto resolution
* Human escalation

---

## 7. Resolution Generator

Generates customer-facing solutions.

---

## 8. Notify Customer

Sends automatic customer updates.

---

## 9. Notify Support

Sends escalation notifications for manual handling.

---

## AI Agent Responsibilities

### Support Response Generator

* Understand issue
* Generate response

### Response Quality Reviewer

* Validate generated output

### Confidence Evaluator

* Assign confidence score
* Trigger escalation

### Resolution Generator

* Generate final resolution

---

# Deterministic Components

* Webhook intake
* Data preparation
* Routing
* Threshold checks
* Telegram notifications
* Ticket preparation

---

# Integrations Used

* n8n Workflow Automation
* HTTP Requests
* External AI APIs
* Telegram Bot API
* Webhooks
* Structured JSON outputs

---

# Features

* Multi-agent workflow architecture
* Structured JSON communication
* Confidence-based decision routing
* Human-in-the-loop escalation
* Deterministic validation
* Automatic customer notification

---

# Agentic Practices Demonstrated

✔ Clear AI roles and responsibilities

✔ Structured JSON outputs

✔ Tool and API integration

✔ Branching and routing logic

✔ Deterministic decision making

✔ Human-in-the-loop review

✔ Fallback handling for uncertain outputs

---

# Sample Input / Output

## Scenario 1 — Automatic Resolution

### Input

```json
{
  "customer_name": "Riya",
  "email": "riya@gmail.com",
  "message": "I forgot my password. How do I reset it?"
}
```

### Workflow Result

```json
{
  "confidence": 95,
  "escalate": false
}
```

### Customer Output

```text
✅ SUPPORT UPDATE

Issue:
Forgot Password

Resolution:
Please provide your email address and a password reset link will be sent.

Status:
Resolved Automatically
```

---

## Scenario 2 — Human Escalation

### Input

```json
{
  "customer_name": "Rahul",
  "email": "rahul@gmail.com",
  "message": "My order never arrived. I want refund immediately and I may file complaint."
}
```

### Workflow Result

```json
{
  "confidence": 20,
  "escalate": true
}
```

### Support Output

```text
🚨 SUPPORT ESCALATION ALERT

Customer issue requires manual review.

Priority:
HIGH

Status:
Awaiting Human Review
```

---

# Human-in-the-Loop Design

High-confidence outputs are resolved automatically.

Low-confidence or risky requests are escalated to support for human review.

This prevents unsafe automation.

---

# Fallback Handling

If automated resolution fails or confidence becomes insufficient:

→ Workflow automatically routes to support review.

---

# Future Improvements

* CRM integration
* Persistent ticket storage
* Customer history
* Analytics dashboard
* Support performance monitoring

---

# Repository Contents

```text


README.md

my-workflow.json

screenshots/
├── workflow.png
├── auto-resolution.png
├── escalation.png
├── auto-resolution-telegram-customer-chat.png
├── escalation-telegram-customer-chat.png
├── escalation-telegram-support-chat.png

sample-input-output/
└── examples.md

demo-link.txt
```

---


# Author

Mahak Juriani

Agentic Workflow Design and n8n Demo Assignment
