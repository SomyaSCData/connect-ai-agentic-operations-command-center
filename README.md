# Connect AI – Agentic Operations Command Center

This project demonstrates how CData Connect AI enables autonomous agents to reason over real enterprise data without hardcoded SQL queries or JavaScript rule engines.

The workflow replaces deterministic ETL logic with a structured, multi-agent architecture that performs schema discovery, risk analysis, and executive reporting.

---

## Overview

This implementation showcases:

- Autonomous schema discovery
- Agent-generated SQL queries
- Reasoning-based risk classification
- Structured JSON outputs between agents
- Model specialization for performance and cost efficiency

---

## Architecture

Schedule Trigger  
→ Discovery Agent (claude-3-haiku + MCP tools)  
→ Risk Analysis Agent (claude-sonnet-4-5)  
→ Severity Gate (IF Node)  
→ Executive Reporting Agent (claude-sonnet-4-5)  
→ Email Alert  

---

## Agent Responsibilities

### 1. Discovery & Retrieval Agent
- Calls listTables
- Inspects relevant schemas
- Dynamically generates SQL
- Returns aggregated operational metrics

Model: claude-3-haiku

---

### 2. Risk Analysis Agent
- Identifies operational risks
- Classifies severity (CRITICAL / WARNING / NORMAL)
- Replaces deterministic rule engine logic

Model: claude-sonnet-4-5

---

### 3. Executive Reporting Agent
- Generates executive-level summary
- Recommends actions
- Formats output for stakeholders

Model: claude-sonnet-4-5

---

## Requirements

- n8n
- CData Connect AI (MCP endpoint)
- Anthropic API key
- Gmail credentials (optional)

---

## Setup Instructions

See SETUP.md for configuration details.
