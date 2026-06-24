# Security Policy

## Reporting Security Vulnerabilities

Veridapt takes security seriously. If you discover a security vulnerability in our code, **please do not open a public GitHub issue**. Instead, report it privately to our security team.

### How to Report

**Email:** security@veridapt.com

Include the following information:

- **Title:** Brief summary of the vulnerability
- **Description:** Detailed explanation of the issue
- **Type:** e.g., Smart Contract Bug, Cryptographic Flaw, Access Control, etc.
- **Severity:** Critical / High / Medium / Low
- **Affected Component:** Contracts, Circuits, Frontend, Infrastructure, etc.
- **Steps to Reproduce:** Clear, reproducible steps
- **Proof of Concept:** Code, script, or detailed walkthrough (if applicable)
- **Impact:** Describe the potential impact (data breach, fund loss, privacy violation, etc.)
- **Suggested Fix:** Optional — your proposed solution
- **Contact Information:** Your name, email, and preferred contact method

### Response Timeline

- **24 hours:** Acknowledgment of your report
- **48 hours:** Initial triage and severity assessment
- **7 days:** Initial response with mitigation plan or timeline
- **30 days:** Target fix and patch release (varies by severity)
- **90 days:** Public disclosure (if vulnerability isn't patched sooner)

We commit to working with you transparently and will keep you updated on progress.

---

## Bug Bounty Program

We offer financial rewards for responsibly disclosed security vulnerabilities that meet our bounty criteria.

### Reward Tiers

| Severity | Reward | Description |
|----------|--------|-------------|
| **Critical** | $5,000–$10,000 | Remote code execution, contract theft, complete privacy breach, loss of funds |
| **High** | $1,000–$5,000 | Significant security flaw, potential fund loss, serious privacy impact, unauthorized access |
| **Medium** | $500–$1,000 | Moderate security risk, partial privacy compromise, temporary service disruption |
| **Low** | $100–$500 | Minor security issue, weak cryptography, edge case vulnerabilities |

**Note:** Reward amounts are at the sole discretion of the Veridapt team and are based on:
- Severity and impact
- Quality of report
- Difficulty of discovery
- Cooperation and timeline
- First reporter (duplicate reports may receive lower rewards)

### Eligibility

To be eligible for the bug bounty program:

1. **You must discover the vulnerability** — Don't use known public exploits
2. **Report privately** — No public disclosure before we've had time to patch
3. **Follow responsible disclosure** — Give us reasonable time (90 days max) to fix before public disclosure
4. **Don't access other users' data** — Limit testing to your own accounts/test environments
5. **Don't damage systems** — No disruption to service or data destruction
6. **Be a good actor** — Act in good faith; don't be malicious or reckless

### Out of Scope

The following are **not** eligible for bounty rewards:

- Social engineering or phishing attacks
- Attacks on systems outside our control (e.g., GitHub, hosting providers)
- Vulnerabilities in third-party libraries or dependencies (report to maintainers)
- Issues already known to our team
- Issues in documentation or non-security-critical areas
- UI/UX issues or typos
- Vulnerabilities affecting only old/unsupported versions

---

## Vulnerability Scope

### In Scope (Eligible for Bounty)

**Smart Contracts:**
- Reentrancy attacks
- Overflow/underflow vulnerabilities
- Improper access control
- Logic bugs affecting security
- Oracle manipulation
- Front-running vulnerabilities
- Unsafe delegatecall usage

**Zero-Knowledge Circuits:**
- Soundness violations
- Privacy leaks
- Incorrect constraint systems
- Input validation flaws

**Frontend:**
- XSS (Cross-Site Scripting)
- CSRF (Cross-Site Request Forgery)
- Insecure cryptographic implementations
- Private key exposure
- Session hijacking

**Infrastructure:**
- Authentication bypass
- Unauthorized data access
- Injection attacks (SQL, Command, etc.)
- Cryptographic key exposure

### Out of Scope

- Information disclosure (non-sensitive)
- Denial of service attacks
- Rate limiting bypasses (without exploitation)
- Missing security headers
- Weak password policies
- Best practice violations (without impact)

---

## Vulnerability Examples

### Critical Vulnerability

A vulnerability in the `ComplianceVerifier` contract that allows any user to bypass proof verification and gain unauthorized compliance status, leading to unauthorized fund transfers.

### High Severity Vulnerability

A ZK circuit with a privacy leak that allows an attacker to partially recover a user's private age or KYC information from a proof.

### Medium Severity Vulnerability

An improper input validation in the frontend that could allow XSS attacks affecting user session tokens.

### Low Severity Vulnerability

A deprecated cryptographic function still in use that is not actively exploited but represents a future risk.

---

## Safe Harbor

We are committed to working with security researchers in good faith. **We will not:**

- Pursue legal action or law enforcement involvement against researchers who:
  - Comply with this security policy
  - Act in good faith
  - Avoid privacy violations, destruction of data, or disruption of service
  - Provide us with reasonable time to patch vulnerabilities

- Hold researchers liable for vulnerabilities they discover responsibly

**You are safe to work with us to improve Veridapt's security.**

---

## Security Best Practices

### For Veridapt Team

- Regular security audits (external firm review)
- Continuous integration testing
- Dependency scanning and updates
- Code review for all changes
- Multi-signature security for mainnet deployments
- Incident response plan

### For Users/Integrators

- **Never share private keys** — Keep them in secure, encrypted storage
- **Verify contract addresses** — Always double-check before interacting
- **Test on testnet first** — Validate transactions in test environment
- **Use hardware wallets** — For high-value operations
- **Keep software updated** — Use latest frontend and library versions

---

## Public Security Disclosures

We will publicly acknowledge security researchers (with permission) who report vulnerabilities through this program in:

- GitHub repository security advisories
- Release notes
- Security acknowledgments page
- Monthly security report

---

## Contact

**Security Email:** security@veridapt.com

For non-security inquiries:
- **General:** hello@veridapt.com
- **Discord:** Coming soon
- **Twitter/X:** @veridapt

---

## Incident Response

In the event of a confirmed critical vulnerability:

1. We will immediately begin mitigation
2. We will deploy a hotfix or workaround
3. We will communicate status to affected parties
4. We will publish a security advisory
5. We will credit the discoverer (if permitted)

---

## Acknowledgments

We appreciate the security research community and thank all researchers who have responsibly disclosed vulnerabilities to us.

[Researcher acknowledgments will be added here upon consent]

---

**Thank you for helping us keep Veridapt secure.**

*Last Updated: June 24, 2026*
