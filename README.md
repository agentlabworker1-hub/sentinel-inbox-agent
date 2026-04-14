# Sentinel Inbox Agent

Sentinel Inbox Agent is a security triage lab project built to simulate how an AI-assisted workflow can monitor inbox events, classify potential account-risk activity, recommend policy actions, and require human approval before sensitive actions are taken.

## Project Goal

Build a safe, test-only AI security workflow that can:

- monitor a test inbox
- detect suspicious login or password reset patterns
- classify event severity
- draft a response
- log actions
- require human approval before execution

## Why This Project Exists

This project is designed as a portfolio-ready agent lab for cloud, IAM, security operations, and IT support workflows.

It is intentionally built with guardrails:

- test accounts only
- no real credentials
- no autonomous sensitive actions
- human approval required for high-risk steps
- audit logging for all recommendations

## Planned Stack

- n8n for workflow orchestration
- OpenAI API for classification and reasoning
- test email inbox for event triggers
- GitHub for version control and documentation
- later: SQLite or Postgres for logging and policy memory

## Initial Workflow Concept

1. A test email arrives in the inbox
2. The workflow reads the message
3. The message is classified by type and severity
4. A draft response is generated
5. The event is logged
6. Sensitive actions are blocked until human approval

## Status

Week 1 setup in progress:
- [x] created isolated local lab user
- [x] created isolated browser profile
- [x] created test email
- [x] created GitHub repo
- [ ] install Docker Desktop
- [ ] install VS Code
- [ ] install Git
- [ ] build first n8n workflow

## Long-Term Direction

Future versions may expand into a dual-agent model:
- Worker Agent: performs triage and proposes actions
- Guard Agent: enforces policy, blocks unsafe behavior, and requires approvals

## Safety Boundary

This lab is for simulation and controlled testing only. It does not manage real identities, real credentials, or unrestricted administrative actions.

## Architecture (v1)

The system is designed as a controlled workflow with clear boundaries.

### Components

- Inbox (Test Email)
  - Receives simulated security alerts
  - Acts as the trigger source

- Workflow Engine (n8n)
  - Monitors inbox
  - Parses incoming messages
  - Routes logic based on classification

- LLM Classification Layer
  - Determines type of request (login alert, reset, unknown)
  - Assigns severity (low, medium, high)

- Policy Layer
  - Applies rules:
    - allow
    - flag
    - require approval
    - deny

- Output Actions
  - Draft response
  - Log event
  - Escalate for human approval

- Audit Log (future)
  - Stores all actions and decisions

### Control Principles

- No autonomous sensitive actions
- Human approval required for high-risk events
- All actions logged
- Test environment only
