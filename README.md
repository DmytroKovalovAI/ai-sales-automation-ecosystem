# AI Sales Automation Ecosystem

An AI-powered sales automation ecosystem built with n8n.

## Overview

This project demonstrates an automated sales workflow covering lead qualification, voice interactions, conversation quality analysis, CRM updates, and management reporting.

## Key Workflows

- **AI Sales Qualification Agent:** qualifies inbound leads using structured qualification criteria.
- **Dialogue Quality Analyst:** evaluates AI sales conversations and identifies improvement opportunities.
- **Sales Monitoring & CEO Report:** generates sales funnel analytics and management summaries.
- **Website Form & Voice Qualification:** processes website inquiries and initiates outbound voice interactions.
- **Outbound Tools:** supports customer lookup and post-call processing.
- **Knowledge Base Pipeline:** prepares a vector database collection and imports knowledge base documents.

## Technology Stack

- n8n
- OpenAI
- Zoho CRM
- Google Sheets
- PostgreSQL Chat Memory
- Qdrant
- Happ.tools
- REST APIs and Webhooks

## Repository Structure

Workflow JSON exports are stored in the `workflows/` directory. `SANITIZATION_REPORT.md` describes the sanitization status, remaining placeholders, and known limitations.

## Setup Notes

These workflow exports are templates, not ready-to-run deployments. Configure credentials, endpoints, webhook paths, spreadsheet IDs, CRM fields, database resources, and local file paths in your own n8n environment before testing.

Never commit API keys, access tokens, private URLs, customer information, or production credentials.

## Validation Status

Static JSON validation has been performed. End-to-end execution and compatibility with a specific n8n environment have not been verified.
