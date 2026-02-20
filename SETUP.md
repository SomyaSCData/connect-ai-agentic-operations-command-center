# Setup Guide

## Step 1 – Configure MCP Credential in n8n

Create a Header Auth credential.

Header Name:
Authorization

Header Value:
Bearer YOUR_API_KEY

Set Allowed HTTP Domain:
https://your-connect-ai-instance.cdata.com

---

## Step 2 – Configure Agent Models

### Discovery Agent
Model: claude-3-haiku  
Max Iterations: 5  
Max Output Tokens: 800  
Return Intermediate Steps: Disabled  
Streaming: Disabled  

---

### Risk Analysis Agent
Model: claude-sonnet-4-5  
Max Iterations: 1  

---

### Reporting Agent
Model: claude-sonnet-4-5  

---

## Step 3 – Import Workflow

Import:
operations-command-center-agentic.json

---

## Step 4 – Validate Execution

Run the workflow manually.

Confirm:

- Discovery Agent completes within 5 iterations
- Risk Analysis Agent outputs valid JSON
- Severity Gate filters NORMAL results
- Email triggers only for WARNING or CRITICAL
