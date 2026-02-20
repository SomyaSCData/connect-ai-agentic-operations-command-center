# Operations Command Center – Agentic Architecture

This project implements an agent-driven operations monitoring system using n8n and CData Connect AI.

The workflow autonomously discovers enterprise data sources, retrieves relevant operational metrics, evaluates risk conditions, and generates executive alerts.

All data exploration and query construction is performed dynamically by an AI agent using MCP tools.

---

## Overview

The workflow performs the following:

1. Discovers available operational datasets.
2. Inspects relevant schemas.
3. Retrieves aggregated operational metrics.
4. Evaluates risk conditions using reasoning.
5. Generates executive-level reporting.
6. Sends alerts when required.

---

## Workflow Structure

Schedule Trigger  
→ Discovery & Retrieval Agent  
→ Risk Analysis Agent  
→ Severity Gate  
→ Executive Reporting Agent  
→ Email Alert  

---

## Technology Stack

- n8n (workflow orchestration)
- CData Connect AI (MCP endpoint)
- Anthropic Claude models
- Gmail (alerting)

---

## Models Used

Discovery Agent: claude-3-haiku  
Risk Analysis Agent: claude-sonnet-4-5  
Reporting Agent: claude-sonnet-4-5  

---

## Repository Contents

- operations-command-center-agentic.json
- ARCHITECTURE.md
- WORKFLOW-DETAILS.md
- CONFIGURATION.md
- SETUP.md
- TROUBLESHOOTING.md

---

## Setup

See SETUP.md for full configuration steps.
