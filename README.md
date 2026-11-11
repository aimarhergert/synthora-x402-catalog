# SYNTHORA x402 Catalog

SYNTHORA publishes data and intelligence products using the [x402](https://www.x402.org/) protocol.

The [public x402 manifest](https://api.hergertsynthora.com/.well-known/x402.json) lists the resources currently advertised by SYNTHORA and their published payment options. See [the catalog guide](catalog.md) for how to interpret these options.

Before paying, compare the endpoint's HTTP 402 response with the published network, asset, amount, and recipient for the selected resource. If any of those fields differ, stop and verify the discrepancy before paying.

## Discovery

- [Public x402 manifest](https://api.hergertsynthora.com/.well-known/x402.json)
- [Storefront](https://pay.hergertsynthora.com)

The file `openapi/well-known.x402.example.json` is a historical snapshot kept for compatibility. Its resources and payment details may be outdated. Use the public manifest for current discovery.
