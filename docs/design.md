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

## Wallet & Payments
- We are using MetaMask on Polygon Amoy testnet.
- Wallets hold MATIC test tokens.
- These tokens will be used to simulate agent-to-agent payments.
- Next step: extend A2A JSON schema with payment metadata.

{
  "protocol": "A2A-Message",
  "version": "1.0",
  "sender": {
    "id": "agent_123",
    "wallet": "0xYourWalletAddressHere"
  },
  "recipient": {
    "id": "agent_456",
    "wallet": "0xRecipientWalletAddressHere"
  },
  "message": {
    "type": "service_request",
    "content": "Requesting market data analysis for TSLA."
  },
  "payment": {
    "token": "MATIC",
    "amount": "0.05",
    "network": "Polygon-Amoy",
    "transaction_id": "pending"
  },
  "timestamp": "2025-08-27T15:00:00Z"
}
