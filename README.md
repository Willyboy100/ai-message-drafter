# AI Message Drafter

An AI-powered outbound messaging system that transforms qualified prospect records into structured, personalized outreach messages using LLM orchestration.

## Overview

This project automates personalized outbound messaging by combining lead context, business rules, and AI-generated copy into a structured workflow.

Rather than generating free-form text, the system produces validated outputs that are ready for CRM workflows and multi-channel outreach.

## Problem

Writing personalized outreach at scale is repetitive and inconsistent.

Sales teams often spend hours researching prospects, maintaining tone, and adapting messages for different channels.

## Solution

The workflow receives a qualified lead, retrieves context, generates personalized messaging with an LLM, validates the output, and returns structured content for downstream automation.

## Workflow Architecture

![Image]docs/workflow-overview.png

## Core Features

* AI-powered message generation
* Prospect context retrieval
* Structured LLM outputs
* Channel-specific messaging
* Validation before delivery
* Airtable integration
* Workflow state tracking

## Technology Stack

**AI**

* OpenAI
* Prompt Engineering
* Structured Outputs

**Automation**

* n8n
* Airtable
* Webhooks
* Conditional Logic

**Data**

* JSON
* REST APIs

## Example Output

The system generates structured responses that can be consumed by CRMs and automation workflows.

```json
{
  "channel": "LinkedIn",
  "tone": "Professional",
  "qualified": true,
  "message": "Hi Sarah, I noticed..."
}
```

## Future Improvements

* Multi-language messaging
* A/B message generation
* Human approval workflow
* Message quality evaluation
* CRM sync optimization

---

**William Njoku**

AI Automation Engineer | LLM Systems | Workflow Orchestration
