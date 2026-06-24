# Deployment Scripts

Automated deployment and configuration scripts for Veridapt smart contracts and infrastructure.

## Available Scripts

### deploy.js
Deploys smart contracts to Supra network:

```bash
node scripts/deploy.js --network testnet
node scripts/deploy.js --network mainnet
```

### setup-oracle.js
Configures Supra oracle integration:

```bash
node scripts/setup-oracle.js
```

### verify-contracts.js
Verifies contract deployment and functionality:

```bash
node scripts/verify-contracts.js
```

### init-governance.js
Initializes DAO governance structures:

```bash
node scripts/init-governance.js
```

### migrate.js
Handles contract migrations and upgrades:

```bash
node scripts/migrate.js --from v1 --to v2
```

## Environment Setup

Create `.env` with:

```env
SUPRA_TESTNET_RPC=https://testnet-rpc.supra.com
SUPRA_MAINNET_RPC=https://rpc.mainnet.supra.com
PRIVATE_KEY=0x...
DEPLOYER_ADDRESS=0x...
```

## Safety Practices

- All scripts support dry-run mode (--dry-run flag)
- Require explicit confirmation before mainnet deployments
- Generate deployment reports for audit trails
- Support rollback procedures

## Development Workflow

1. Test on testnet first
2. Run verification scripts
3. Get community approval (governance)
4. Execute mainnet deployment
5. Monitor contract status

See [docs/](../docs/) for more information.
