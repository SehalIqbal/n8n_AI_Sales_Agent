# n8n_AI_Sales_Agent
AI-powered Sales Agent built with n8n, Vapi, and Twilio – automates outbound calls, delivers real-time sales pitches, and logs results to Google Sheets.

## 📁 Project Structure
`ai_sales_agent.json` --> Triggers the AI agent to call a lead using Vapi + Twilio 
`ai_sales_agent_part_2.json`  --> Listens for the end-of-call report and handles post-call decisions 
`create_google_sheet.json`  --> One-time workflow to create and set up the Google Sheet for logging 

## 🧠 Features

- 🔁 Fully automated outbound AI calls
- 🎤 AI agent handles sales pitch via Vapi
- 📞 Integrated with Twilio for real-time voice delivery
- 📊 Logs transcript, lead details, and decision logic to Google Sheets
- 💼 Designed to scale for business use-cases

## 🛠️ Prerequisites

- [n8n](https://n8n.io/) installed (self-hosted or cloud)
- [Vapi](https://vapi.ai/) API Key (for AI voice agent)
- [Twilio](https://twilio.com/) account with number
- Google Account with Google Sheets access
- n8n credentials set up:
  - Google Sheets OAuth2
  - Vapi API Token
  - Twilio API SID/Auth Token

Step 1: One-Time Google Sheets Setup
Run the create_google_sheet.json workflow in n8n to:

Create a new Google Sheet

Add required columns like Name, Phone, Call Result, Transcript, etc.

✅ This step only needs to be done once.

Step 2: Configure & Run the Calling Workflow
Import ai_sales_agent.json into n8n.

Configure environment variables or credentials for:

Vapi API key (for AI agent)

Twilio phone number (to place the call)

This workflow triggers a call to a lead, passing lead info and starting the AI agent.

Step 3: Handle Call Results
Import ai_sales_agent_part_2.json into n8n.

This listens to Vapi’s end-of-call webhook.

Based on the transcript and metadata, it:

Logs the result to Google Sheets
