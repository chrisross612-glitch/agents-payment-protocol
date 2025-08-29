# Agent Payments Protocol – Design Doc

## Goal
Enable AI agents to not only exchange tasks (via A2A) but also exchange value using tokenized micropayments.

## Tools
- Google’s A2A Protocol (messaging between agents)
- Polygon testnet tokens (MATIC on Amoy network)
- MetaMask (wallet)

## First Use Case
Summarizer Agent:
- Agent A sends text → Agent B (summarizer) charges 0.05 MATIC per task.
- Agent A pays → Agent B returns summarized text.

## Open Questions
- How should payment metadata be standardized in the JSON schema?
- Should transactions happen before or after service delivery?
- How to handle disputes if an agent doesn’t deliver after payment?
