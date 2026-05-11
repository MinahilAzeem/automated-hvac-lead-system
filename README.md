# ⚡ Intelligent Lead Triage Automation (n8n + AI + Airtable)

![n8n](https://img.shields.io/badge/n8n-FF6D5A?style=for-the-badge&logo=n8n&logoColor=white)
![OpenAI](https://img.shields.io/badge/OpenAI-412991?style=for-the-badge&logo=openai&logoColor=white)
![Airtable](https://img.shields.io/badge/Airtable-18BFFF?style=for-the-badge&logo=airtable&logoColor=white)

An automated, end-to-end inbound lead processing system designed for service businesses (like HVAC, Plumbing, and Roofing). This workflow captures customer requests, uses an AI Agent to perform preliminary triage with empathetic responses, and seamlessly logs structured data into a CRM for dispatch.

## 🎯 The Problem It Solves
Service businesses lose revenue when inbound leads are not acknowledged immediately. This system ensures 24/7 lead capture, provides the customer with instant, intelligent reassurance, and organizes the data so dispatchers can prioritize emergency jobs without manual data entry.

## 🏗️ System Architecture

1. **Trigger (Webhook/Form):** Captures the customer's Name, Email, and a description of their problem.
2. **AI Processing (LLM Agent):** Evaluates the problem description using a strictly constrained system prompt to generate a professional, empathetic, non-binding preliminary assessment.
3. **Database (Airtable):** Appends the user data and the AI's triage notes into a structured CRM view for the business owner.

*(Note: Replace this text with an image of your n8n workflow. E.g., `![Workflow Architecture](assets/workflow-screenshot.png)`)*

## 🧠 Core Features & Prompt Engineering
The system utilizes a custom AI Agent designed specifically to avoid "hallucinating" prices or timelines. 

**Agent Directives:**
* Acknowledge the specific mechanical issue with empathy.
* Provide a brief, non-binding assessment of common causes.
* Explicitly state that a certified technician is required for on-site diagnosis.
* Maintain a humanized, reassuring tone under 4 sentences.

## 🛠️ Tech Stack
* **Orchestration:** n8n (Self-hosted / Cloud)
* **Intelligence:** OpenAI GPT-4o / Google Gemini
* **Database:** Airtable (REST API integration)

## 🚀 How to Deploy

To use this workflow in your own environment:
1. Clone this repository.
2. Import the `workflow-export.json` file into your n8n instance.
3. Configure your credentials for the **AI Agent** (API Key) and **Airtable** (Personal Access Token with `schema.bases:read` and `data.records:write` scopes).
4. Update the Airtable Node to point to your specific Base ID and Table.
