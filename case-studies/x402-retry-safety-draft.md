# Deterministic retry-safety tests for an open-source x402 service

Public draft: <https://staging.poidh.xyz/d/bafkreiae67qwhf4zh25sjkxi6ehul6hgiob3e2mq4e5uon753suwnhitdm>

This is a public, unfunded POIDH bounty draft. It proposes a 0.020 ETH reward on
Base for a deterministic test pack covering one agreed open-source Python x402
entry point. Publishing the draft did not create an onchain bounty, escrow ETH,
or authorize a payment.

The proposed acceptance cases cover:

- duplicate payment intents without duplicate settlement or result release;
- lost-response retry and reconciliation after successful settlement;
- recovery from a crash at the persistence boundary;
- rejection of an idempotency key reused with a changed payload;
- rejection of a completed payment-signature replay; and
- withholding paid output when settlement fails.

The delivery would include no more than eight deterministic cases, local
fixtures or doubles rather than live payments, a state-transition table, a
before/after failing test, and a reproducible verification command. Any
production fix is limited to one entry point and 150 non-generated lines unless
the funder approves a revised scope. The target repository and contribution
route must be agreed before work begins; production systems, private
credentials, customer data, paid facilitators, and broadcast payments are out
of scope.

The canonical full wording is the POIDH draft linked above.
