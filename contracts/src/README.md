# Smart Contracts

This directory contains the Solidity smart contracts for the Veridapt compliance verification and enforcement system.

## Contract Files

- **ComplianceVerifier.sol**: Core zero-knowledge proof verification logic
- **ComplianceOracle.sol**: Integration with Supra oracles for real-time compliance data
- **ComplianceGate.sol**: Transaction gating and enforcement based on compliance status
- **VeridaptToken.sol**: VERI token contract (ERC-20 with governance)
- **GovernanceModule.sol**: DAO governance and voting mechanisms

## Development Setup

```bash
# Install dependencies
npm install

# Compile contracts
npm run compile

# Run tests
npm run test

# Deploy to testnet
npm run deploy:testnet
```

## Contract Interactions

### User Flow
1. User generates ZK proof locally using Noir circuits
2. Proof is submitted to ComplianceVerifier contract
3. Contract verifies the proof cryptographically
4. Oracle data is checked for sanctions/restrictions
5. ComplianceGate allows/denies transaction

### Attestation Flow
1. Issuer submits signed credential to network
2. Credential is stored on IPFS (hash on-chain)
3. User can reference credential in proofs
4. Credentials have expiry and refresh mechanisms

## Testing

All contracts include comprehensive test suites covering:
- Proof verification correctness
- Oracle integration
- Access control
- Token mechanics
- Governance voting

## Security

- All contracts undergo professional audits before mainnet
- Bug bounty program for community participation
- Formal verification for critical paths
