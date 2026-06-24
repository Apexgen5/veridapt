# Contributing to Veridapt

Thank you for your interest in contributing to Veridapt! We're building the trust and compliance infrastructure for the tokenized economy, and we welcome contributions from developers, researchers, designers, and community members.

This document provides guidelines and instructions for contributing to the Veridapt project.

## Table of Contents

1. [Code of Conduct](#code-of-conduct)
2. [Getting Started](#getting-started)
3. [Development Workflow](#development-workflow)
4. [Branch Strategy](#branch-strategy)
5. [Commit Conventions](#commit-conventions)
6. [Pull Request Process](#pull-request-process)
7. [Development Guidelines](#development-guidelines)
8. [Testing Requirements](#testing-requirements)
9. [Security & Bug Bounty](#security--bug-bounty)
10. [Documentation](#documentation)
11. [Issue Labels](#issue-labels)
12. [Community & Support](#community--support)

---

## Code of Conduct

### Our Commitment

We are committed to providing a welcoming and inclusive environment for all contributors. We pledge to:

- Treat all people with respect and dignity
- Welcome individuals of all backgrounds and identities
- Foster a harassment-free environment
- Value diverse perspectives and constructive feedback

### Unacceptable Behavior

The following behaviors are unacceptable:

- Harassment, discrimination, or intimidation
- Offensive comments related to identity or protected characteristics
- Trolling, insulting, or derogatory comments
- Unwelcome sexual attention or advances
- Publishing others' private information without consent
- Other unethical or unprofessional conduct

### Reporting Issues

If you witness or experience unacceptable behavior, please report it to **hello@veridapt.com** with details and context. All reports will be handled confidentially.

---

## Getting Started

### Prerequisites

Before you begin, ensure you have installed:

- **Node.js** 18+ and npm/yarn
- **Git** 2.30+
- **Foundry** (for smart contracts): https://book.getfoundry.sh/getting-started/installation
- **Noir** (for ZK circuits): https://noir-lang.org/docs/getting_started/
- **Supra Testnet Access** (optional but recommended)

### Local Setup

1. **Fork the repository**
   ```bash
   # Go to https://github.com/Apexgen5/veridapt and click "Fork"
   ```

2. **Clone your fork**
   ```bash
   git clone https://github.com/<YOUR-USERNAME>/veridapt.git
   cd veridapt
   ```

3. **Add upstream remote**
   ```bash
   git remote add upstream https://github.com/Apexgen5/veridapt.git
   ```

4. **Install dependencies**
   ```bash
   # Root dependencies
   npm install

   # Frontend
   cd frontend && npm install && cd ..

   # Contracts
   cd contracts && forge install && cd ..

   # Circuits (if applicable)
   cd circuits && nargo check && cd ..
   ```

5. **Set up environment variables**
   ```bash
   # Copy example env files
   cp frontend/.env.example frontend/.env.local
   cp contracts/.env.example contracts/.env

   # Fill in your values (RPC URLs, private keys, etc.)
   ```

---

## Development Workflow

### 1. Create a Feature Branch

```bash
# Ensure you're on the latest upstream main
git fetch upstream
git checkout upstream/main

# Create a feature branch
git checkout -b feature/your-feature-name
```

### 2. Make Your Changes

- Keep commits focused and atomic
- Update tests as you go
- Follow the development guidelines below

### 3. Test Locally

```bash
# Frontend
cd frontend && npm run test && npm run lint

# Contracts
cd contracts && forge test && forge fmt --check

# Circuits
cd circuits && nargo test && nargo check
```

### 4. Commit and Push

```bash
git add .
git commit -m "feat: add your feature description"
git push origin feature/your-feature-name
```

### 5. Open a Pull Request

Create a PR against `upstream/main` with a clear description (see [Pull Request Process](#pull-request-process)).

---

## Branch Strategy

We use a **Git Flow** variant:

- **`main`** — Production-ready code. Only merged via PR with reviews.
- **`develop`** — Integration branch for features. All PRs target this first.
- **`feature/*`** — Feature branches. Naming: `feature/zk-age-proof`, `feature/dashboard-redesign`
- **`bugfix/*`** — Bug fixes. Naming: `bugfix/proof-verification-error`
- **`docs/*`** — Documentation updates. Naming: `docs/api-reference`
- **`chore/*`** — Maintenance tasks. Naming: `chore/update-dependencies`

### Branch Naming Convention

```
<type>/<kebab-case-description>
```

**Types:** `feature`, `bugfix`, `docs`, `chore`, `refactor`, `perf`

---

## Commit Conventions

We follow **Conventional Commits** for clear, semantic commit messages.

### Format

```
<type>(<scope>): <subject>

<body>

<footer>
```

### Examples

```
feat(circuits): add age verification Noir circuit

- Implement age range proof without revealing exact age
- Add test cases for age >= 18 predicate
- Performance: <1s proving time

Closes #42
```

```
fix(contracts): resolve proof verification race condition

Ensures proper nonce handling in ComplianceVerifier contract.

Fixes #99
```

### Types

- **feat** — New feature
- **fix** — Bug fix
- **docs** — Documentation changes
- **style** — Code style changes (formatting, semicolons, etc.)
- **refactor** — Code refactoring without feature changes
- **perf** — Performance improvements
- **test** — Test additions/updates
- **chore** — Build, dependency, or maintenance tasks

### Scopes

- `contracts` — Smart contracts
- `circuits` — Noir circuits
- `frontend` — Next.js frontend
- `docs` — Documentation
- `scripts` — Deployment scripts
- `ci` — CI/CD configuration
- `deps` — Dependencies

---

## Pull Request Process

### Before Submitting

1. **Sync with upstream**
   ```bash
   git fetch upstream
   git rebase upstream/develop
   ```

2. **Run all tests**
   ```bash
   npm run test       # Frontend
   forge test         # Contracts
   nargo test         # Circuits
   ```

3. **Update documentation** — If applicable, update README, docs/, or inline comments

4. **Verify no merge conflicts** — Resolve any conflicts before submitting

### PR Title Format

```
<type>(<scope>): <description>
```

Example: `feat(circuits): add sanctions screening predicate`

### PR Description Template

```markdown
## Description
Brief summary of changes and motivation.

## Changes
- Change 1
- Change 2
- Change 3

## Testing
- [x] Unit tests pass
- [x] Integration tests pass
- [x] Manual testing completed

## Type of Change
- [ ] New feature
- [ ] Bug fix
- [ ] Breaking change
- [ ] Documentation update

## Checklist
- [ ] Code follows project style guidelines
- [ ] Self-review completed
- [ ] Comments added for complex logic
- [ ] Documentation updated
- [ ] Tests added/updated
- [ ] No new warnings generated

## Related Issues
Fixes #123
Related to #456

## Screenshots (if applicable)
[Add screenshots for UI changes]
```

### Review Process

1. **Automated Checks**
   - GitHub Actions must pass (tests, lint, security)
   - Code coverage requirements met

2. **Code Review**
   - Minimum 1 approval required (2 for smart contracts)
   - Address all review comments

3. **Approval & Merge**
   - Squash commits before merging
   - Use PR title as commit message

---

## Development Guidelines

### Smart Contracts (Solidity)

- **Style:** Follow [Solidity Style Guide](https://docs.soliditylang.org/en/latest/style-guide.html)
- **Tools:** Use Foundry for testing and deployment
- **Patterns:**
  - Use OpenZeppelin contracts for standard functionality
  - Implement access control (onlyOwner, roles)
  - Add natspec documentation for all public functions
  - Use SafeMath or Solidity 0.8+ built-in checks
- **Security:** 
  - No external calls in loops
  - Proper reentrancy guards
  - Validate all inputs

Example:
```solidity
/// @notice Verifies a zero-knowledge proof for compliance
/// @param proof The ZK proof bytes
/// @param publicInputs Array of public inputs
/// @return isValid Whether the proof is valid
function verifyProof(
    bytes calldata proof,
    uint256[] calldata publicInputs
) external view returns (bool isValid) {
    // Implementation
}
```

### ZK Circuits (Noir)

- **Style:** Follow [Noir Conventions](https://noir-lang.org/docs/)
- **Testing:** Comprehensive test cases for all predicates
- **Performance:** 
  - Target <2s proving time for Phase 1
  - Document circuit complexity
- **Privacy:**
  - Ensure zero-knowledge property
  - No leaking of private inputs
  - Test with diverse inputs

Example:
```noir
fn verify_age(age: Field, min_age: Field) -> bool {
    age >= min_age
}

#[test]
fn test_age_verification() {
    assert(verify_age(25, 18) == true);
    assert(verify_age(17, 18) == false);
}
```

### Frontend (Next.js/React)

- **Style:** Use Prettier + ESLint configuration
- **Patterns:**
  - Functional components with hooks
  - Component composition over inheritance
  - Use TanStack Query for data fetching
  - Tailwind CSS for styling
- **Accessibility:**
  - WCAG 2.1 AA compliant
  - Proper semantic HTML
  - ARIA labels where needed
- **Performance:**
  - Code splitting for routes
  - Image optimization
  - Memoization for expensive computations

Example:
```typescript
'use client';

import { useState } from 'react';

interface ProofGeneratorProps {
  onProofGenerated: (proof: string) => void;
}

export default function ProofGenerator({
  onProofGenerated,
}: ProofGeneratorProps) {
  const [loading, setLoading] = useState(false);

  const handleGenerateProof = async () => {
    setLoading(true);
    try {
      // Implementation
    } finally {
      setLoading(false);
    }
  };

  return <button onClick={handleGenerateProof}>Generate Proof</button>;
}
```

---

## Testing Requirements

### Smart Contracts

```bash
cd contracts
forge test --coverage
```

**Requirements:**
- 100% line coverage for critical paths
- Test all state transitions
- Test access control
- Test edge cases (overflow, underflow)

### Circuits

```bash
cd circuits
nargo test
```

**Requirements:**
- Test happy path
- Test boundary conditions
- Test with various input types

### Frontend

```bash
cd frontend
npm run test -- --coverage
npm run test:e2e
```

**Requirements:**
- Unit tests for components and hooks
- E2E tests for critical user flows
- >80% code coverage

---

## Security & Bug Bounty

### Reporting Security Issues

**Do not open public issues for security vulnerabilities.**

Instead, email: **security@veridapt.com**

Include:
- Description of the vulnerability
- Steps to reproduce
- Potential impact
- Suggested fix (if any)

We will acknowledge receipt within 24 hours and provide updates as we work on a fix.

### Bug Bounty Program

We offer rewards for responsibly disclosed security vulnerabilities:

- **Critical** ($5,000–$10,000): Remote code execution, contract theft
- **High** ($1,000–$5,000): Significant privacy or security impact
- **Medium** ($500–$1,000): Moderate security risk
- **Low** ($100–$500): Minor issues or improvements

See [SECURITY.md](./SECURITY.md) for full details.

---

## Documentation

### Code Documentation

- **Solidity:** Use natspec comments for all public functions
- **Noir:** Add comments explaining complex constraints
- **TypeScript/React:** Use JSDoc for exported functions

Example:
```typescript
/**
 * Generates a zero-knowledge proof for age verification
 * @param age - The user's age (private)
 * @param minAge - The minimum required age (public)
 * @returns ZK proof bytes
 * @throws Error if proof generation fails
 */
export async function generateAgeProof(
  age: number,
  minAge: number
): Promise<Uint8Array> {
  // Implementation
}
```

### Repository Documentation

- Update **README.md** if adding new features
- Add docs to **docs/** for architecture changes
- Update **WHITEPAPER.md** for protocol changes
- Add inline comments for non-obvious logic

---

## Issue Labels

We use GitHub labels to organize issues:

### Priority
- `priority:critical` — Blocks release
- `priority:high` — Important, should be done soon
- `priority:medium` — Normal priority
- `priority:low` — Nice to have

### Type
- `bug` — Defect or issue
- `feature` — New functionality
- `enhancement` — Improvement to existing feature
- `docs` — Documentation
- `security` — Security-related

### Difficulty
- `good first issue` — Great for newcomers
- `help wanted` — Need assistance
- `complex` — Requires deep knowledge

### Status
- `in progress` — Currently being worked on
- `blocked` — Waiting on something
- `review` — Under review
- `ready` — Ready to implement

---

## Community & Support

### Communication Channels

- **Discord** — General discussion, announcements (coming soon)
- **Telegram** — Quick updates and community chat (coming soon)
- **GitHub Discussions** — Technical discussions
- **Twitter/X** — @veridapt for announcements
- **Email** — hello@veridapt.com for inquiries

### Getting Help

- **Development questions?** → GitHub Discussions
- **Bug report?** → GitHub Issues (with reproducible example)
- **Security issue?** → security@veridapt.com (private)
- **Feature request?** → GitHub Issues with detailed use case

### Recognition

Contributors will be recognized in:
- GitHub Contributors page
- Monthly changelog highlights
- Special mentions in community calls
- Future DAO governance participation

---

## License

By contributing to Veridapt, you agree that your contributions will be licensed under the MIT License (see [LICENSE](./LICENSE)).

---

## Questions?

Have questions? Feel free to:
- Open a discussion in GitHub Discussions
- Reach out on Discord (coming soon)
- Email hello@veridapt.com

**Thank you for contributing to Veridapt! Together we're building the trust infrastructure for the tokenized economy.** 🚀

---

**Veridapt: Verify Once. Comply Everywhere.**
