# zivana-identity

Identity layer for the Zivana Protocol, built on 
[Hyperledger Identus](https://hyperledger-identus.github.io/docs/) 
with Cardano as the Verifiable Data Registry.

This repository contains the DID credential schemas, verifiable 
credential templates, KYC workflow definitions, and jurisdiction 
configurations that form the first of Zivana's four core protocol 
primitives. Every participant in the Zivana ecosystem — SME, investor, 
agent, or oracle node operator — holds a DID-anchored credential 
issued through this layer.

Trust that belongs to the holder travels with the holder. This 
repository is where that guarantee is implemented.

---

## What lives here

| Component | Purpose |
|---|---|
| Participant credential schema | DID, role, jurisdiction, KYC status, and access tier definitions |
| Credential issuance flow | ZVN.Identity.issue() implementation connecting applications to Identus Cloud Agent |
| Credential verification flow | ZVN.Identity.verify() implementation for protocol gate checks |
| Jurisdiction configurations | Country-specific compliance flags for Nigeria and supported jurisdictions |
| Feature-phone access path | USSD and SMS-based credential flows for participants without smartphones |
| Identus Cloud Agent config | Docker Compose configuration for self-hosted agent deployment |

---

## Protocol Context

`zivana-identity` is the identity primitive of the Zivana Protocol:

Primitive 1 — Identity    ← this repository
Primitive 2 — Trust Score ← zivana-midnight + zivana-core
Primitive 3 — Covenant    ← zivana-midnight + zivana-core
Primitive 4 — Distribution ← zivana-core + zivana-oracle

Full protocol documentation: [zivana-docs](https://github.com/zivana-labs/zivana-docs)

---

## Development Status

> Phase 0 — Identus environment setup and first credential issuance verification

This repository is under active early development. All credential 
flows are being tested on Cardano preprod testnet and against a local 
Identus Cloud Agent instance before any production deployment.

---

## Getting Started

Prerequisites:
- [Docker](https://docker.com) and Docker Compose
- Cardano preprod access via Blockfrost

```bash
# Clone the repository
git clone https://github.com/zivana-labs/zivana-identity.git
cd zivana-identity

# Start local Identus Cloud Agent
docker-compose up -d

# Verify agent is running
curl http://localhost:8080/cloud-agent/_system/health
```

Full setup guide: coming in Phase 0 documentation.

---

## Contributing

Read the [contributing guidelines](https://github.com/zivana-labs/.github/blob/main/CONTRIBUTING.md) 
before opening a pull request. All PRs target the `develop` branch.

## Licence

MIT — see [LICENSE](./LICENSE)

---

*Part of [Zivana Labs](https://github.com/zivana-labs) — 
built for Africans, open to the world.*
