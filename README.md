# AI Job Email Analyzer

An AI-powered automation that analyzes job-related emails, extracts structured information, classifies each email, and stores the results in Google Sheets.

The project is built with **n8n** and is designed to demonstrate how AI can automate repetitive information-processing tasks.

## 🚀 Project Overview

Job seekers often receive a large number of emails from recruiters, job boards, companies, and hiring managers. Manually reviewing and organizing these emails is repetitive and time-consuming.

This automation processes incoming job-related emails and uses an AI model to:

- Identify the type of email
- Extract key job information
- Normalize the information into a structured format
- Generate a short summary
- Store the results in Google Sheets

### Workflow

Gmail → n8n → AI → JSON validation → Google Sheets

## 🤖 Email Classification

The AI classifies emails into one of the following categories:

- `JOB_ALERT`
- `RECRUITER`
- `INTERVIEW`
- `APPLICATION_CONFIRMATION`
- `REJECTION`
- `NETWORKING`
- `OTHER`

## 📊 Extracted Information

For each email, the automation extracts:

| Field | Description |
|---|---|
| Date | Email date |
| Sender | Email sender |
| Subject | Email subject |
| Type | Email category |
| Company | Company name |
| Position | Job position |
| Location | Job location |
| Work Model | Remote / Hybrid / On-site |
| Salary | Salary information |
| Technologies | Technologies and tools mentioned |
| Summary | Short AI-generated summary |

If information is not available in the email, the automation returns an empty value instead of guessing or inventing information.

## 🛠️ Technologies

- **n8n** — workflow automation
- **AI / LLM** — email classification and information extraction
- **JavaScript** — JSON parsing and data processing
- **Gmail** — email source
- **Google Sheets** — structured data storage
- **Docker** — local n8n environment

The project can use different LLM providers. During development, **Ollama** was used for local AI processing, with the architecture designed so that another provider such as **Claude** can be used instead.

## 🧪 QA & Reliability

The project is also designed with a QA mindset.

The AI output is treated as untrusted data and validated before it is passed to the next step.

For example:

- Only predefined categories are accepted
- Missing information must remain empty
- Company names must not be inferred from email domains
- Technologies must be returned as an array
- AI output must be valid JSON
- Invalid JSON causes the workflow to fail instead of silently storing incorrect data

This demonstrates an important principle of AI automation:

> AI-generated data should be validated before it is used by downstream systems.

## 🎯 Project Goals

This project was created to explore practical applications of AI automation and to learn how to combine:

**AI + workflow automation + data extraction + QA**

Potential future improvements include:

- Automatic Gmail email monitoring
- Claude API integration
- Duplicate email detection
- Job opportunity scoring
- Automatic CV/job matching
- Salary analysis
- Job search statistics
- Telegram notifications
- Dashboard with job market analytics
- Automated follow-up reminders

## 📁 Project Status

🚧 **Work in progress**

The project is being developed incrementally, starting with email analysis and structured data extraction and gradually moving toward a fully automated job opportunity tracking system.
