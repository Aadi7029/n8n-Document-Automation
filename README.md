For this you would need the n8n Self Hosted Starter kit or else the n8n cloud service access.
The kit is free to downlaod and for setting it up you either need Docker Desktop to host it or you can use
render and supabase as its database.

You can download the self hosted starter kit from the github repo " https://github.com/n8n-io/self-hosted-ai-starter-kit " and clone the repo.

You can learn more about how to host this at "https://docs.n8n.io/hosting/"

ABOUT THIS PROJECT:

The project aims to automate the generation of business documents (specifically, contract proposals) and their distribution via email, using AI in combination with workflow automation tools. The core automation is accomplished using n8n (an open-source workflow automation platform) and Google Gemini’s AI technology. The goal is to reduce manual effort, improve consistency, and scale document management workflows efficiently.

Main Components and Workflow: 
Information Collection
User or client project details are collected via a trigger (like an online form or Google Sheet). This kickstarts the automation.

AI-Powered Drafting: 
The collected information is passed to an AI agent (Google Gemini/GPT-4), which generates a draft of the required proposal, ensuring all important aspects (scope, deliverables, pricing, timelines) are covered accurately.

Template Merging: 
The AI-generated draft is inserted into a standard, professional template (Google Docs or PDF), with correct formatting and branding.

Contextual Retrieval: 
The system can recall relevant sections (such as previous clauses, policies, or best practices) using embeddings and vector stores, making the proposals more contextually accurate.

Automated Email Dispatch: 
Once the documents are generated and reviewed, n8n automatically sends them as attachments to the desired recipients using Gmail or other email APIs.
