# AI in Operations & Support Engineering

**Duration:** 4 Days (1 Hour Each Day)

---

## Day 1 – Foundations of AI for Ops/Support
**Objective:** Equip Ops & Support Engineers with practical AI skills for monitoring, troubleshooting, ticket management, documentation, and future AI applications, using prompts as one of several tools.

### 1. AI Fundamentals (10 mins)
- What is AI?
- Types of AI:
  - Narrow AI (Chatbots, Alexa)
  - Generative AI (ChatGPT, text, images, code)
  - General AI (human-level thinking, future)
- AI in Ops/Support (summarization, triage, logs analysis, communication)

**Visual Idea:**
```
          Artificial Intelligence
       ┌─────────────┬─────────────┐
   Narrow AI     Generative AI   General AI
       │             │              │
   Examples:    Examples:       (Not yet achieved,
   Chatbots,    ChatGPT, AI       human-level thinking)
   Alexa        Image/Code Gen
```

### 2. Introduction to LLMs (10 mins)
- What is an LLM(Large Language Model)
- Difference: AI vs ML vs LLMs
- Examples: GPT, Claude, Gemini, Llama
- Which one to use when:
  - GPT → general-purpose
  - Claude → summarization
  - Gemini → Google ecosystem
  - Llama → private/internal use

**Visual Idea:**
```
AI (Broad Field)
   └── Machine Learning (Subset)
          └── LLMs (Specialized in text & language)
```

### 3. Sensitive Data Awareness (10 mins)
- Why it's important:
  - LLMs may temporarily store prompts
  - Confidential info could be exposed unintentionally
  - Compliance/regulatory requirements
- Types of sensitive data:
  - Customer PII: names, emails, accounts
  - Internal company info: IPs, architecture, configs
  - Security credentials: API keys, passwords
  - Incident details with sensitive info

**Examples of Unsafe vs Safe Prompts:**

| **Scenario** | **Unsafe Prompt** | **Safe Prompt** |
|--------------|-----------------|----------------|
| Jira Ticket Summarization | “Summarize ticket: Customer John Doe, email john@example.com, reports credit card issue” | “Summarize ticket: Customer reports payment issue (PII removed)” |
| Log Analysis | “Analyze logs containing IP 10.1.2.3 and database password db@1234” | “Analyze logs for errors related to database connection (mask IP/password)” |
| RCA Drafting | “RCA for incident affecting VIP customer Acme Corp” | “RCA for high-priority incident affecting a customer, anonymized” |
| Automation Script | “Fix script using my AWS keys: AKIAxxx/SECRETxxx” | “Generate script template for AWS EC2 management, keys removed” |

- Best practices:
  - Anonymize sensitive data
  - Use placeholders for IDs, IPs, credentials
  - Never share secrets with AI
  - Use internal/private LLMs for sensitive data

**Visual Idea:**
```
Sensitive Data → LLM Prompt → Risk of Exposure
        │
        └─> Always anonymize, mask, or remove before sending
```

### 4. Prompt Engineering Basics (15 mins)
- What is a prompt? (Context + Task + Format)
- Types relevant for Ops/Support: Summarization, Classification, Troubleshooting, Rephrasing

**Visual Idea:**
```
[Context] + [Task] + [Format] = Good Output
```

### 5. Hands-On Practice (25 mins)
- Summarize a customer message
- Convert logs into plain English explanations
- Draft Jira ticket summaries from messages

**Visual Idea:**
```
Customer Message → AI Prompt → Ticket Summary
```
### 6. AI for Documentation & Knowledge Bases (5 mins)
- Areas AI can help:
  - Confluence or internal documentation: auto-summarize updates, create page drafts
  - Support KB articles: convert tickets into knowledge articles, highlight common issues
  - SOP updates: draft step-by-step procedures from incident notes
  - Search & retrieval: generate FAQ-like answers from existing documentation

**Visual Idea:**
```
Tickets / Logs / Notes → AI → Draft KB Article → Review & Publish
```
### 7. Wrap-Up (5 mins)
- AI is a helper, not a replacement
- Good prompts = better outputs
- Always practice safe data sharing
- Help in maintaining documentation

---

## Day 2 – AI for Incident Investigation & Ticket Triage
**Objective:** Use AI to speed up investigation, root cause hints, and ticket classification.

### 1. Incident Workflow with AI Co-Pilot (10 mins)
```
Alert → Logs → AI Analysis → Suggested Cause → Jira Ticket → RCA Draft
```

### 2. AI Patterns Ops/Support tasks (15 mins)
- Troubleshooting: "analyze logs and suggest next steps"
- RCA: "list likely causes for X based on logs"
- Ticket classification

**Visual Idea (Mind Map):**
```
Troubleshooting Prompts
    ├── Explain error logs
    ├── Suggest likely cause
    ├── Recommend next steps

Classification Prompts
    ├── Classify ticket priority
    ├── Group alerts by service

RCA Prompts
    ├── Draft RCA structure
    ├── Summarize incident notes
```

### 3. Hands-On Practice (30 mins)
- Feed sample logs → AI suggests possible causes
- Classify tickets into P1/P2/P3
- Draft RCA outline from investigation notes

**Visual Idea:**
```
Incoming Ticket
   ├── P1 (Critical)
   ├── P2 (Major)
   └── P3 (Minor)
```

---
### 4. AI Techniques in Repetitive Tasks

### Ticket Categorization & Prioritization
- **Description:** AI can auto-classify tickets, suggest priority, and assign to the right team.
- **Tools:** Jira Automation, ServiceNow, Zendesk
- **Visual Guide:**
```
Incoming Ticket → Jira Automation / ServiceNow → Suggested Category & Priority → Assigned Team → Engineer Review → Final Output
```
- **Short Guide:**
  1. Use built-in AI or rule-based automation to classify and prioritize tickets.
  2. Review AI suggestions before assignment.
  3. Continuously train automation rules based on historical tickets.

### Log Analysis & Alert Management
- **Description:** AI parses logs, summarizes anomalies, and highlights critical alerts.
- **Tools:** Datadog, Splunk, ELK Stack, Prometheus + Grafana
- **Visual Guide:**
```
Server / Application Logs → Datadog / Splunk → AI Anomaly Detection → Alert Summary → Engineer Review → Action Taken
```
- **Short Guide:**
  1. Feed logs into monitoring tools with AI/ML capabilities.
  2. Configure anomaly detection and alert thresholds.
  3. Use AI-generated summaries to quickly identify root causes.

### Knowledge & Response Automation
- **Description:** AI drafts KB articles, SOP updates, and customer responses.
- **Tools:** Confluence, Notion, BugBug, ChatGPT
- **Visual Guide:**
```
Resolved Tickets / Logs → AI Drafting Tools (ChatGPT / BugBug / Confluence) → Draft KB / SOP / Customer Response → Engineer Review → Publish / Send
```
- **Short Guide:**
  1. Collect source material (tickets, logs, previous KBs).
  2. Use AI to draft consistent documentation or responses.
  3. Engineer reviews and validates before publishing.

**Tips:**
- Always validate AI outputs.
- Use role-based or context-aware prompts.
- Keep sensitive data secure.



## Advanced AI Collaboration & Role based Analysis
**Objective:** Apply advanced techniques and simulate real Ops/Support scenarios.

### 1. Advanced Techniques (15 mins)
- Role-based prompting: DevOps engineer vs Support agent
- Chain prompting for step-by-step RCA
- Verification & refinement of outputs

**Visual Idea:**
```
Role-Based Prompt → Output Type
DevOps Engineer → Technical analysis
Support Agent → Customer-friendly response
```

### 2. End-to-End AI in Ops/Support Workflow (40 mins)
- Scenario 1: CPU spike alert → AI analyzes logs → Jira ticket drafted
- Scenario 2: OTT stream downtime → AI drafts customer response
- Scenario 3: RCA drafting using AI chain prompting

**Visual Idea:**
```
Monitoring → Alert → AI Suggests Analysis → Engineer Validates → 
AI Drafts Ticket → Engineer Finalizes → RCA with AI Support
```

### 3. Best Practices (5 mins)
- Always validate AI outputs
- Use AI as co-pilot, not authority
- Keep sensitive data secure

**Visual Idea:**
```
✅ Validate Outputs
✅ Be Clear in Prompts
✅ AI as Co-Pilot
✅ Secure Data Handling
```

---

## Day 3 – The Future of AI in Operations & Support (5–10 Years Ahead)
**Objective:** Inspire team to imagine AI-driven Ops & Support.

### 1. AI Evolution Overview (10 mins)
- Today → Next 2 yrs → 5 yrs → 10 yrs

**Visual Idea (Timeline):**
```
Today: Ticket summarization & triage
Next 2 yrs: Predictive alerts & RCA
5 yrs: Self-healing & optimization
10 yrs: Autonomous Ops & strategic insights
```

### 2. Predictive & Autonomous Operations (10 mins)
- Predict incidents before they happen
- Self-healing systems

**Visual Idea:**
```
Monitoring → Predictive Analysis → Self-Healing Actions → Engineer Notified Only if Needed
```

### 3. Conversational Co-Pilot & Personalized Insights (10 mins)
- AI talks naturally, generates RCA slides, summarizes trends
- Personalized alerts based on engineer context

**Visual Idea:**
```
[Your Tasks] [Predicted Issues] [Suggested Actions] [Knowledge Updates]
```

### 4. Multi-Modal & Cross-System AI (10 mins)
- Logs, metrics, images, video, IoT telemetry analyzed together
- Example: OTT stream anomaly detection

**Visual Idea:**
```
Logs + Metrics + Video Feed → AI Analysis → Predicted RCA & Fix → Jira Ticket / Automation Trigger
```

### 5. Speculative & Mysterious Possibilities (10 mins)
- Self-documenting systems update runbooks automatically
- Cross-company AI collaboration for incident patterns
- Engineers focus on strategy & innovation

**Visual Idea:**
```
[AI Predictions] [Automation Actions] [Visual Anomaly Detection] [Strategic Insights for Engineers]
```

### 6. Hands-On Exercise / Brainstorm (10 mins)
- Team imagines their ideal AI assistant: tasks, communication, dashboards
- Present creative ideas

### 7. Key Takeaways
- AI evolves from assistant → co-pilot → autonomous partner
- Engineers focus on strategy, customer experience, innovation
- Preparing today ensures adaptability for future AI-driven Ops

