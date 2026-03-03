# Operations Command Center – Agentic Workflow (CData Connect AI + n8n)

This repository contains an agent-driven Manufacturing & Supply Chain Intelligence workflow built with CData Connect AI and orchestrated using n8n.

The workflow dynamically discovers enterprise datasets, retrieves operational metrics across ERP, production, supplier, and logistics systems, evaluates risk conditions, and generates executive alerts without hardcoded SQL queries or JavaScript rule engines.

---

## Overview

This workflow is designed to automate manufacturing and supply chain monitoring across enterprise systems.

It leverages:

- CData Connect AI (MCP) for unified, governed data access
- n8n for workflow orchestration
- Claude models for reasoning and reporting
- Structured JSON communication between agents

The workflow:

1. Discovers available operational datasets dynamically.
2. Inspects relevant schemas at runtime.
3. Retrieves aggregated operational metrics.
4. Evaluates risk conditions using contextual reasoning.
5. Classifies severity (CRITICAL / WARNING / NORMAL).
6. Generates executive-ready alerts when required.
This architecture enables proactive operational intelligence rather than reactive reporting.

---

## Setup Instructions

### 1. Import the Workflow

- Download [`operations-command-center-agentic.json`](https://github.com/SomyaSCData/connect-ai-agentic-operations-command-center/blob/main/operations-command-center-agentic.json)
- In n8n, select **Import from file**
- Upload the JSON file

---

### 2. Configure Credentials

You must configure the following credentials:

- MCP (CData Connect AI)
- Anthropic API Key
- Gmail (optional for alerts)

See the [Configuration Guide](https://github.com/SomyaSCData/connect-ai-agentic-operations-command-center/blob/main/CONFIGURATION.md) for detailed setup instructions.

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
Using a lighter model for data retrieval and a more capable model for reasoning ensures cost and performance optimization.

---

## Example Usage

This workflow can be scheduled to run on a recurring basis (e.g., daily or hourly) to monitor operational risk.

Example scenarios:

- Inventory coverage drops below projected demand, increasing stock-out risk
- Supplier lead times trend upward, threatening production schedules
- Excess inventory accumulates, increasing carrying costs
- Cost anomalies appear in ERP procurement data
- Open order volume rises faster than replenishment rates

When overall severity is classified as WARNING or CRITICAL, an executive summary is generated and delivered via email.

---

## Workflow Structure

Schedule Trigger  
→ Discovery & Retrieval Agent  
→ Risk Analysis Agent  
→ Severity Gate  
→ Executive Reporting Agent  
→ Email Alert  

CData Connect AI provides the unified enterprise data layer.
n8n handles orchestration and workflow execution.

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

- [Architecture Overview](https://github.com/SomyaSCData/connect-ai-agentic-operations-command-center/blob/main/ARCHITECTURE.md)
- [Workflow Details and Agent Prompts](https://github.com/SomyaSCData/connect-ai-agentic-operations-command-center/blob/main/WORKFLOW-DETAILS.md)
- [Configuration Guide](https://github.com/SomyaSCData/connect-ai-agentic-operations-command-center/blob/main/CONFIGURATION.md)
- [Setup Guide](https://github.com/SomyaSCData/connect-ai-agentic-operations-command-center/blob/main/SETUP.md)
- [Troubleshooting](https://github.com/SomyaSCData/connect-ai-agentic-operations-command-center/blob/main/TROUBLESHOOTING.md)

---

## License

MIT License © CData Software
