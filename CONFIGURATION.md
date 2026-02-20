# Configuration

## MCP Credential Setup (n8n)

Create Header Authentication credentials.

Header Name:
Authorization

Header Value:
Bearer YOUR_API_KEY

Allowed HTTP Domain:
https://your-connect-ai-instance.cdata.com

---

## Agent Configuration

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

## IF Node Configuration

Condition:

overall_severity != "NORMAL"

Only proceed for WARNING or CRITICAL.
