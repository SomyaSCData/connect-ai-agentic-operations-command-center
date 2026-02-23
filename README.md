# Operations Command Center – Agentic Workflow (n8n + CData Connect AI)

This repository contains an n8n workflow that enables automated operational risk monitoring using CData Connect AI and large language models.

The workflow dynamically discovers enterprise datasets, retrieves operational metrics, evaluates risk conditions, and generates executive alerts without hardcoded SQL queries or JavaScript rule engines.

---

## Overview

This workflow is designed to automate operational monitoring across enterprise systems.

It leverages:

- n8n for workflow orchestration
- CData Connect AI (MCP) for live data access
- Claude models for reasoning and reporting
- Structured JSON communication between agents

The workflow:

1. Discovers available operational datasets.
2. Inspects relevant schemas.
3. Retrieves aggregated operational metrics.
4. Evaluates risk conditions using reasoning.
5. Classifies severity (CRITICAL / WARNING / NORMAL).
6. Generates executive-ready alerts when required.

---

## Setup Instructions

### 1. Import the Workflow

- Download `operations-command-center-agentic.json`
- In n8n, select **Import from file**
- Upload the JSON file

---

### 2. Configure Credentials

You must configure the following credentials:

- MCP (CData Connect AI)
- Anthropic API Key
- Gmail (optional for alerts)

See `CONFIGURATION.md` for detailed setup.

---

### 3. Validate Execution

After configuration:

- Run the workflow manually
- Confirm the Discovery Agent completes successfully
- Confirm structured JSON output from the Risk Analysis Agent
- Confirm alerts trigger only for WARNING or CRITICAL

---

## Configuration

### MCP Credential Setup (n8n)

Create a Header Authentication credential:

Header Name:
Authorization

Header Value:
Bearer YOUR_API_KEY

Allowed HTTP Domain:
https://your-connect-ai-instance.cdata.com

---

### Model Configuration

Discovery Agent:
- Model: claude-3-haiku
- Max Iterations: 5
- Max Output Tokens: 800
- Return Intermediate Steps: Disabled

Risk Analysis Agent:
- Model: claude-sonnet-4-5
- Max Iterations: 1

Reporting Agent:
- Model: claude-sonnet-4-5

---

## Example Usage

This workflow can be scheduled to run on a recurring basis (e.g., daily or hourly) to monitor operational risk.

Example scenarios:

- Inventory levels decline below expected thresholds
- Supplier delivery performance degrades
- Demand coverage weakens relative to supply

When overall severity is classified as WARNING or CRITICAL, an executive summary is generated and delivered via email.

---

## Workflow Structure

Schedule Trigger  
→ Discovery & Retrieval Agent  
→ Risk Analysis Agent  
→ Severity Gate  
→ Executive Reporting Agent  
→ Email Alert  

---

## Requirements

- n8n (latest stable version)
- CData Connect AI (MCP endpoint)
- Anthropic API Key
- Gmail account (optional)

---

## Repository Contents

.
├── operations-command-center-agentic.json  
├── ARCHITECTURE.md  
├── WORKFLOW-DETAILS.md  
├── CONFIGURATION.md  
├── SETUP.md  
├── TROUBLESHOOTING.md  
└── README.md  

---

## Documentation

- Architecture Overview – ARCHITECTURE.md
- Workflow Details and Agent Prompts – WORKFLOW-DETAILS.md
- Configuration Guide – CONFIGURATION.md
- Setup Guide – SETUP.md
- Troubleshooting – TROUBLESHOOTING.md

---

## License

MIT License © CData Software
