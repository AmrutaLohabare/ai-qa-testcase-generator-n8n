# System Architecture

## High-Level Flow

User → Chat Interface → n8n Workflow → OpenAI → Jira → Email

---

## Components

### 1. Input Layer

* Chat interface
* File upload (SRS PDF)

### 2. Processing Layer

* File extraction
* Data transformation
* AI processing (OpenAI)

### 3. Integration Layer

* Jira API (Story + Subtasks)
* Email service

### 4. Output Layer

* Jira tickets
* Email notification

---

## Key Characteristics

* Event-driven workflow
* API-first integration
* AI-assisted decision layer
* Scalable architecture

---

## Summary

This architecture demonstrates how AI can be embedded into QA workflows to automate traditionally manual processes and improve efficiency at scale.
