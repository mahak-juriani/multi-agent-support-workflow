# AI Customer Support Escalation Workflow (n8n)

## Project Overview

This project implements an **Agentic Customer Support Automation Workflow** using **n8n**, AI agents, and Telegram integration.

The workflow is designed to automatically resolve routine customer support requests while escalating sensitive or low-confidence cases to human support teams.

Instead of relying on a single AI prompt, the workflow decomposes responsibilities into multiple AI and deterministic steps to improve reliability, explainability, and control.

---

## Problem Statement

Customer support teams often receive large volumes of repetitive requests such as:

* Password reset
* Delivery questions
* General account inquiries

At the same time, they also handle high-risk requests including:

* Refund requests
* Payment disputes
* Customer complaints
* Escalation scenarios

Fully manual handling reduces efficiency, while fully automated responses introduce risk.

This workflow balances both approaches using confidence-based routing and human review.

---

## Workflow Architecture

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

## AI Agent Responsibilities

### 1. Support Response Generator

* Interprets customer request
* Produces structured support output

### 2. Response Quality Reviewer

* Evaluates generated responses
* Prevents unreliable outputs

### 3. Confidence Evaluator

* Assigns confidence score
* Determines escalation requirements

### 4. Resolution Generator

* Produces customer-facing resolutions

---

## Deterministic Components

* Webhook intake
* Data preparation
* Confidence thresholds
* Routing decisions
* Telegram notifications
* Ticket preparation

---

## Integrations Used

* n8n Workflow Automation
* HTTP Requests
* External AI APIs
* Telegram Bot API
* Webhooks
* JSON-based structured outputs

---

## Features

* Multi-agent workflow architecture
* Confidence-based decision routing
* Human-in-the-loop escalation
* Automatic customer notification
* Structured JSON communication
* Deterministic validation

---

## Example Workflow Behavior

### Scenario 1 — Automatic Resolution

Customer Issue:
Forgot password

Result:

* AI generates response
* Confidence remains high
* Customer receives automatic resolution

---

### Scenario 2 — Human Escalation

Customer Issue:
Refund request with complaint

Result:

* Confidence decreases
* Workflow escalates to support team
* Support receives notification

---

## Agentic Practices Demonstrated

✔ Clear AI roles
✔ Structured JSON outputs
✔ Tool and API integration
✔ Branching and routing logic
✔ Deterministic decision making
✔ Human-in-the-loop review
✔ Fallback handling for uncertain cases

---

## Future Improvements

* CRM integration
* Persistent ticket storage
* Analytics dashboard
* Customer history context
* Support performance tracking

---

## Repository Contents

* n8n workflow export
* Demo video link
* Documentation
* Workflow screenshots

---

## Demo

Video Demo (Google Drive):
(https://drive.google.com/drive/folders/1IDEPG86ceJPzvGYRbBSJV97SWuOF8u5-?usp=drive_link)

---

## Author 
Mahak Juriani
