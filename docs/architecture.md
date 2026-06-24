# Veridapt Architecture

## System Overview

Veridapt is built on a modular, layered architecture designed for scalability, privacy, and cross-chain interoperability.

### Core Layers

#### 1. Issuer Network Layer
- Regulated institutions and Zyphe nodes issue zero-knowledge credentials
- Credentials are cryptographically signed and portable across chains
- Supports multiple credential types (KYC, AML, accreditation, jurisdiction attestations)

#### 2. ZK Proof Layer
- Circuits written in **Noir** for compliance predicates
- Predicates include: age verification, KYC status, sanctions screening, accreditation level, jurisdiction restrictions
- Proofs are privacy-preserving and reveal only necessary information

#### 3. Verification & Enforcement Engine
- Smart contracts on **Supra EVM** that verify zero-knowledge proofs
- Automated execution of compliance rules
- Integration with DeFi protocols for transaction gating

#### 4. Oracle & Data Layer
- **Supra native oracles** provide real-time compliance data
- Sanctions lists, risk scores, regulatory updates
- Dynamic rule updates without protocol changes

#### 5. Cross-Chain Portability
- **SupraNova** bridge for multi-chain credential verification
- Standardized credential format for universal compatibility
- Chain-agnostic proof verification

#### 6. Governance & Incentives
- Native **VERI token** for governance and incentives
- Staking mechanisms for network security
- Emission schedules aligned with protocol growth

## Data Flow

```
User/Institution
    ↓
Credential Issuance (Issuer Network)
    ↓
ZK Proof Generation (Local)
    ↓
Proof Submission (Smart Contract)
    ↓
Proof Verification (Supra Contract)
    ↓
Oracle Data Validation
    ↓
Transaction Authorization / Compliance Status
```

## Smart Contract Architecture

- **ComplianceVerifier.sol**: Core proof verification logic
- **ComplianceOracle.sol**: Real-time data integration
- **ComplianceGate.sol**: Transaction gating and enforcement
- **GovernanceToken.sol**: VERI token and governance

## Security Considerations

- Threshold encryption for "break-glass" regulated access
- Multi-signature requirements for credential issuance
- Proof freshness validation
- Rate limiting and sybil resistance mechanisms
