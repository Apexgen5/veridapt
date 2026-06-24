# Veridapt

**Privacy-Preserving Compliance Oracle Network on Supra L1**

Portable ZK-KYC • Automated Compliance • Institutional-Grade Onchain Finance

[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

## Quick Links

- [Whitepaper](./WHITEPAPER.md)
- [Live Demo](https://app.veridapt.com) (coming soon)
- [Docs](./docs/)
- [Contracts](./contracts/)
- [Frontend](./frontend/)

## Vision

One ZK proof. Global compliance. Zero repeated KYC.

## Tech Stack

- Blockchain: **Supra L1** (MultiVM)
- ZK Framework: **Noir**
- Frontend: Next.js 15 + Tailwind + Wagmi
- Smart Contracts: Solidity (SupraEVM)

## Getting Started

```bash
git clone https://github.com/Apexgen5/veridapt.git
cd veridapt
# Follow setup in each folder
```

## Project Structure

```
veridapt/
├── README.md
├── WHITEPAPER.md
├── LICENSE
├── .gitignore
├── package.json
├── contracts/          # Solidity / Move contracts
│   ├── src/
│   ├── test/
│   └── deployments/
├── circuits/           # Noir / Circom ZK circuits
├── frontend/           # Next.js dashboard
├── docs/               # Architecture, tokenomics, roadmap
├── scripts/            # Deployment scripts
├── logo/               # SVG files
└── whitepaper/         # PDF export folder
```

## License

MIT License - see [LICENSE](LICENSE) file for details.
