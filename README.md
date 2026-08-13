# SYNTHORA x402 Catalog

SYNTHORA is an autonomous machine-to-machine (M2M) store selling data and
intelligence products over the [x402](https://www.x402.org/) payment protocol.
Every product is an HTTP endpoint gated by HTTP 402 Payment Required: an agent
reads the payment requirements from the 402 response, pays in USDC on Base
mainnet, and retries the request with proof of payment. No accounts, no API
keys, no human in the loop.

- **Live products:** 57 (see [catalog.md](catalog.md))
- **Network:** Base mainnet (`eip155:8453`)
- **Currency:** USDC (`0x833589fCD6eDb6E08f4c7C32D4f71b54bdA02913`)
- **Pay-to address:** `0x10800a5a5B9d72251566EC651E862A8b4B427dE0`
- **x402 version:** 2, scheme `exact`
- **Provider DID:** `did:web:pay.hergertsynthora.com`

## Discovery

The canonical, always-live list of products and prices is the public
x402 manifest:

- Manifest: <https://api.hergertsynthora.com/.well-known/x402.json>
- Agent card (A2A): <https://pay.hergertsynthora.com/.well-known/agent.json>
- Store front: <https://pay.hergertsynthora.com>

A snapshot of the manifest is included in
[openapi/well-known.x402.example.json](openapi/well-known.x402.example.json).

## How to buy (agent quickstart)

1. `POST` to any endpoint in [catalog.md](catalog.md) with a JSON body.
2. Receive HTTP 402 with an `accepts` array describing the exact payment
   required (amount in USDC atomic units, asset, network, `payTo`).
3. Settle the payment on Base and retry the request with the `X-PAYMENT`
   header (per the x402 v2 spec).
4. Receive the JSON response. Responses are deterministic and Ed25519-signed.
   No charge on upstream failure.

## Files

- `catalog.md` — table of live products: endpoint, price in USDC, description.
- `openapi/well-known.x402.example.json` — example of the public well-known
  x402 manifest served by the store.

Catalog data is generated from the live manifest (last updated: 2026-08-13T11:58:26.535222+00:00).
