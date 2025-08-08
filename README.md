# 📄 Document Automation with n8n

This repository contains the workflows and supporting assets for a **Document Automation** system built using **n8n** (self-hosted via the [n8n Starter Kit](https://github.com/n8n-io/self-hosted-ai-starter-kit)).

## 🚀 Overview

This project streamlines document generation by:

- Collecting user data via webhooks
- Enriching missing fields using an AI agent (LLM)
- Generating structured documents (PDF, DOCX, etc.)
- Sending the final documents via email or other delivery channels

It’s designed to be **modular, scalable**, and **fully automated**, using n8n as the core orchestrator.

---
# About This Project

The project aims to automate the generation of business documents (specifically, contract proposals) and their distribution via email, using AI in combination with workflow automation tools. The core automation is accomplished using n8n (an open-source workflow automation platform) and Google Gemini’s AI technology. The goal is to reduce manual effort, improve consistency, and scale document management workflows efficiently.

## Main Components and Workflow: 
- Information Collection
- User or client project details are collected via a trigger (like an online form or Google Sheet). This kickstarts the automation.

## AI-Powered Drafting: 
- The collected information is passed to an AI agent (Google Gemini/GPT-4), which generates a draft of the required proposal,    ensuring all important aspects (scope, deliverables, pricing, timelines) are covered accurately.

## Template Merging: 
- The AI-generated draft is inserted into a standard, professional template (Google Docs or PDF), with correct formatting and branding.

## Contextual Retrieval: 
_ The system can recall relevant sections (such as previous clauses, policies, or best practices) using embeddings and vector stores, making the proposals more contextually accurate.

## Automated Email Dispatch: 
- Once the documents are generated and reviewed, n8n automatically sends them as attachments to the desired recipients using Gmail or other email APIs.


## 🔧 Technologies Used

- [n8n](https://n8n.io/) – Workflow Automation Tool (Self-hosted)
- AI Agent – Powered by Gemini Chat Model with structured output
- Webhooks – For input data ingestion
- Custom Nodes / HTTP Requests – For integration with third-party APIs
- File generation tools (e.g., PDFKit, Docx templates)

---

## 📁 Project Structure

```bash
├── workflows/               # n8n workflows (exported as JSON)
├── assets/                  # Icons, templates, and example files
├── docs/                    # Flow diagrams, documentation, architecture
├── .env.example             # Environment variable template
└── README.md                # You're here!
```

---

## 🧠 Workflow Summary

1. **Collect User Data**  
   Triggered via `Webhook` node.

2. **AI Agent Fills Missing Fields**  
   Uses Gemini LLM with a structured prompt to enrich input.

3. **Generate Document**  
   Conditional logic + document template node/API to produce output.

4. **Deliver Output**  
   Via email, API, or external service (e.g., Google Drive, Notion).

5. **Log Activity / Send Confirmation**

---

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/Aadi7029/n8n-Document-Automation.git
cd n8n-Document-Automation
```

### 2. Set Up Environment

Copy `.env.example` to `.env` and configure your secrets (e.g., OpenAI/Gemini key, SMTP, storage).

### 3. Import Workflows

- Log into your self-hosted n8n instance.
- Go to **Workflows** > **Import from File**.
- Upload workflows from the `/workflows(.json)` folder.

### 4. Start the Server

Ensure your [n8n starter kit](https://github.com/n8n-io/self-hosted-ai-starter-kit) is running:

```bash
docker-compose up -d
```

---

## 📌 Notes

- **Security**: Be cautious with webhook exposure—use tokens or authentication for production.
- **Backups**: Export your workflows regularly.
- **Monitoring**: Integrate logging/error handling for long workflows.

---

## 📷 Diagrams & Docs

Flow diagrams and architecture explanations can be found in the `/docs` folder.

---

## 🙌 Contributing

Open to pull requests and discussions! Please fork the repo and submit PRs for new features or improvements.
