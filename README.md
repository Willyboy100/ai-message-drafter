# AI Message Drafter

An AI-powered outbound messaging system that turns qualified prospect data into personalized, multi-channel sales messages using n8n, Airtable, and LLM orchestration.

## Overview

The AI Message Drafter automates one of the repetitive parts of outbound sales: turning prospect information into relevant, personalized messaging.

The workflow monitors qualified prospects, checks whether they meet the messaging criteria, gathers relevant context, generates channel-specific messages with an LLM, and stores the results for review and follow-up.

## The Problem

Personalized outbound messaging becomes difficult to manage as the number of prospects increases.

Sales teams need to:

- Review prospect information
- Decide which prospects are worth contacting
- Personalize messages
- Adapt messaging to different channels
- Keep track of generated outreach
- Avoid contacting the same prospect repeatedly

These steps create repetitive manual work and increase the chance of inconsistent messaging.

## The Solution

This workflow turns the process into an automated pipeline:

**Qualified Prospect → Qualification Check → Context Retrieval → AI Message Generation → Review → CRM/Database Update**

A prospect must meet the defined qualification threshold before the AI generates outreach.

## Workflow Architecture

![Workflow Overview](docs/workflow-overview.png)

## Core Workflow

### 1. Qualification

The workflow evaluates the prospect's qualification score.

Only prospects meeting the configured **ASSET Score ≥ 4** threshold continue to the messaging stage.

### 2. Duplicate Prevention

Before generating new outreach, the workflow checks whether messaging has already been created for the prospect.

This prevents unnecessary duplicate outreach.

### 3. Context Retrieval

Relevant prospect and company information is retrieved from the existing data source.

This context is passed to the AI generation stage.

### 4. AI Message Generation

The LLM generates personalized outreach based on the available prospect information and defined messaging rules.

The system generates messaging for multiple channels, including:

- LinkedIn connection
- LinkedIn follow-up
- X
- Telegram

### 5. Review & Tracking

Generated messages are written back to the data layer with a review/status state so they can be reviewed before being used for outreach.

## Example

### Input

```json
{
  "first_name": "Sarah",
  "last_name": "Chen",
  "title": "VP of Engineering",
  "company": "Acme AI",
  "company_size": "201-500",
  "industry": "Developer Tools"
}
