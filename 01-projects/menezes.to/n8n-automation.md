---
tags:
  - type/project
  - topic/project
---

# n8n Automation

Self-hosted workflow automation platform for personal automations.

## Goals

- Centralize personal automations in a self-hosted workflow system.
- Reduce repetitive manual tasks across tools and services.
- Build reusable workflows that can be extended over time.
- Keep data ownership and control inside a personal stack.

## Infrastructure

- n8n running in a self-hosted environment
- Persistent storage for workflows and execution history
- Secrets management for API credentials
- Optional reverse proxy and authentication layer

## Example Automations

- WhatsApp message -> parse request -> update Notion shopping list
- Calendar event reminder -> send summary by email
- Incoming email -> classify with OpenAI -> route to the right list or note

## Integrations

- Notion
- WhatsApp API
- OpenAI
- Calendar
- Email

## Future Ideas

- Voice-to-task workflows from mobile input
- Daily personal briefing across calendar, notes, and inbox
- Auto-categorization of expenses or purchase requests
- Smart notifications based on time, context, or urgency

## Tasks

- [ ] Define the first set of high-value automations.
- [ ] Set up the self-hosted n8n environment.
- [ ] Connect core integrations and store credentials securely.
- [ ] Build the WhatsApp to Notion shopping list workflow.
- [ ] Add monitoring or alerting for failed workflows.

## Related

- [[projects-moc]]
- [[menezes-to]]
