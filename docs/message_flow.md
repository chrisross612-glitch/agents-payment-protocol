# Agent-to-Agent Payment Flow

This document describes how two autonomous agents (AgentA and AgentB) communicate and verify payments using tokenized messages.

---

## Flow Overview

1. **AgentA → AgentB (payment_message.json)**
   - AgentA initiates a payment for a service.
   - Message includes:
     - intent = "payment_for_service"
     - amount = 0.01 MATIC
     - transaction_id = on-chain hash

2. **Blockchain Validation**
   - The transaction ID is checked on Polygon Amoy testnet.
   - If confirmed, AgentB can trust funds are transferred.

3. **AgentB → AgentA (payment_confirmation.json)**
   - AgentB sends a confirmation message.
   - Message includes:
     - reference_transaction = same transaction hash
     - status = "confirmed"
     - timestamp

---

## Example Sequence


---

## Future Extensions

- Add more intents (e.g., escrow, refund, subscription).
- Add multi-chain support (Ethereum, Solana, Cosmos).
- Add authentication (signed messages).
