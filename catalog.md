# SYNTHORA x402 Product Catalog

Use the [public x402 manifest](https://api.hergertsynthora.com/.well-known/x402.json) to discover the currently advertised resources and their published payment options.

Each entry in `resources` contains resource metadata and an `accepts` array of payment options. Before paying, compare the endpoint's HTTP 402 response with the published network, asset, amount, and recipient for the option you select. If any of those fields differ, stop and verify the discrepancy before paying.
