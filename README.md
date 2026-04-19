# Sentinel Inbox Agent

Sentinel Inbox Agent is a security triage lab project built to simulate how an AI-assisted workflow can monitor inbox events, classify potential account-risk activity, recommend policy actions, and require human approval before sensitive actions are taken.

## Project Goal

## Current Implementation (v1)

This version of the project simulates an email security triage workflow using manual input.

The workflow:
- accepts email text input
- classifies risk level (High / Medium / Low) using an LLM
- routes decisions using conditional logic
- assigns outcomes (escalate, review, safe)
- logs structured output with timestamps

## Status

Phase 1 Complete:
- [x] built AI classification workflow in n8n
- [x] implemented conditional routing (high / medium / low)
- [x] added structured logging with timestamps
- [x] exported workflow to GitHub

Phase 2 (Planned):
- [ ] connect real inbox trigger
- [ ] add approval step for high-risk actions
- [ ] persist logs to database (SQLite/Postgres)
