# Veridapt Frontend

Next.js 15 dashboard application for Veridapt compliance verification and attestation management.

## Features

- **Proof Generation UI**: User-friendly interface for creating ZK proofs
- **Credential Management**: View, verify, and manage issued credentials
- **Compliance Dashboard**: Real-time status of compliance predicates
- **Analytics**: Track attestations and verification history
- **Enterprise Admin Panel**: Custom predicate management, SLA monitoring

## Tech Stack

- **Framework**: Next.js 15
- **Styling**: Tailwind CSS
- **Web3 Integration**: Wagmi + Viem
- **State Management**: React Context / TanStack Query
- **Testing**: Jest + React Testing Library

## Getting Started

```bash
cd frontend

# Install dependencies
npm install

# Run development server
npm run dev

# Build for production
npm run build
npm start
```

## Project Structure

```
frontend/
├── app/
│   ├── page.tsx
│   ├── layout.tsx
│   ├── proof/
│   ├── credentials/
│   ├── dashboard/
│   └── admin/
├── components/
│   ├── ProofGenerator/
│   ├── CredentialCard/
│   ├── ComplianceStatus/
│   └── shared/
├── hooks/
│   ├── useProof.ts
│   ├── useCredential.ts
│   └── useOracle.ts
├── utils/
│   ├── crypto.ts
│   ├── contract.ts
│   └── api.ts
└── styles/
    └── globals.css
```

## Key Pages

- **/** - Landing page and quick start
- **/proof** - Zero-knowledge proof generation interface
- **/credentials** - Credential issuance and management
- **/dashboard** - Compliance status and history
- **/admin** - Enterprise administration (SaaS features)

## Environment Variables

```env
NEXT_PUBLIC_SUPRA_RPC=https://rpc.mainnet.supra.com
NEXT_PUBLIC_CONTRACT_ADDRESS=0x...
NEXT_PUBLIC_ORACLE_ADDRESS=0x...
NEXT_PUBLIC_API_URL=https://api.veridapt.com
```

## Testing

```bash
npm run test
npm run test:e2e
```

## Deployment

Frontend is optimized for Vercel:

```bash
npm run build
vercel deploy
```

## Contributing

See [CONTRIBUTING.md](../../CONTRIBUTING.md) for guidelines.
