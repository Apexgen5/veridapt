# ZK Circuits

This directory contains the Noir zero-knowledge circuits for Veridapt compliance predicates.

## Circuit Overview

Noir circuits enable privacy-preserving verification of compliance attributes without exposing personal information.

### Available Predicates

#### Phase 1 (MVP)
- **age.nr**: Verify user is 18+ without disclosing exact age
- **kyc_status.nr**: Prove KYC completion without revealing identity details

#### Phase 2 (Mainnet)
- **accreditation.nr**: Verify investor accreditation status
- **sanctions.nr**: Prove non-presence on sanctions lists
- **jurisdiction.nr**: Verify allowed jurisdiction for transaction

#### Phase 3 (Expansion)
- **income_level.nr**: Income range verification
- **credit_score.nr**: Credit tier without exact score
- **institutional_tier.nr**: Institutional customer classification
- And 30+ more domain-specific predicates

## Circuit Structure

Each circuit includes:
1. **Input witness** (private data from user)
2. **Public inputs** (credential hash, oracle data)
3. **Constraints** (proof logic)
4. **Outputs** (boolean result or selective disclosure data)

## Development

### Prerequisites
- Noir compiler (nargo)
- Circom/Noir CLI tools

### Compiling Circuits

```bash
nargo compile
```

### Testing Circuits

```bash
nargo test
```

### Proving & Verification

```bash
nargo prove
nargo verify
```

## Privacy Properties

All circuits maintain the following privacy guarantees:
- **Zero-knowledge**: Proof reveals nothing but the boolean result
- **Selective disclosure**: Can reveal subsets of attributes if needed
- **Unlinkability**: Multiple proofs from same user are unlinkable

## Performance Targets

| Circuit | Proving Time | Proof Size |
|---------|--|--|
| age.nr | <1s | <1KB |
| kyc_status.nr | <2s | <2KB |
| Multi-predicate | <5s | <5KB |

## Auditability

- All circuits reviewed by cryptography specialists
- Production circuits use proven Noir patterns
- Regular updates for privacy improvements
