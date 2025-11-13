Conduct a security audit of the codebase.

## Instructions

1. **Define Audit Scope**
   - Code review for security issues
   - Dependency vulnerabilities
   - Configuration security
   - Authentication and authorization
   - Data protection
   - API security

2. **Dependency Security Scan**

   **Check for known vulnerabilities:**
   - Python: `pip-audit` or `safety check`
   - Node.js: `npm audit` or `yarn audit`
   - Go: `go list -json -m all | nancy sleuth`
   - Rust: `cargo audit`
   - General: Snyk, Dependabot, GitHub Security Advisories

   ```bash
   # Python
   pip-audit

   # Node.js
   npm audit --production

   # Check for outdated packages
   npm outdated
   ```

3. **Code Security Review**

   **OWASP Top 10 Checks:**

   **A01: Broken Access Control**
   - Check authorization on all endpoints
   - Verify users can't access unauthorized resources
   - Test for IDOR (Insecure Direct Object References)
   - Check for missing function-level access control

   **A02: Cryptographic Failures**
   - Verify sensitive data is encrypted at rest
   - Check TLS/SSL for data in transit
   - Look for hardcoded secrets
   - Check for weak encryption algorithms (MD5, SHA1)
   - Verify secure random number generation

   **A03: Injection**
   - SQL injection: Check for parameterized queries
   - Command injection: Avoid shell execution with user input
   - XSS: Check for output encoding/escaping
   - LDAP, XML, NoSQL injection checks

   **A04: Insecure Design**
   - Review architecture for security flaws
   - Check for security requirements in design
   - Verify threat modeling done

   **A05: Security Misconfiguration**
   - Check for debug mode in production
   - Verify error messages don't leak info
   - Review default passwords/credentials
   - Check for unnecessary features enabled
   - Verify security headers (CSP, HSTS, etc.)

   **A06: Vulnerable Components**
   - Run dependency scans (see step 2)
   - Check for outdated frameworks
   - Review third-party integrations

   **A07: Identification and Authentication Failures**
   - Check password strength requirements
   - Verify credential stuffing protections
   - Check for weak session management
   - Verify MFA implementation (if applicable)
   - Check for default credentials

   **A08: Software and Data Integrity Failures**
   - Verify CI/CD pipeline security
   - Check for unsigned packages
   - Review update mechanisms

   **A09: Security Logging and Monitoring Failures**
   - Verify security events are logged
   - Check log protection
   - Ensure alerting on suspicious activity

   **A10: Server-Side Request Forgery (SSRF)**
   - Check URL validation
   - Verify network segmentation
   - Check for SSRF in image processing, webhooks, etc.

4. **Common Vulnerabilities to Check**

   **Hardcoded Secrets:**
   ```bash
   # Search for potential secrets
   grep -r "password\s*=\s*['\"]" .
   grep -r "api_key\s*=\s*['\"]" .
   grep -r "secret\s*=\s*['\"]" .

   # Use automated tools
   trufflehog git file://. --only-verified
   gitleaks detect --source .
   ```

   **SQL Injection:**
   ```python
   # BAD: String concatenation
   query = "SELECT * FROM users WHERE id = " + user_id

   # GOOD: Parameterized query
   query = "SELECT * FROM users WHERE id = %s"
   cursor.execute(query, (user_id,))
   ```

   **XSS (Cross-Site Scripting):**
   ```javascript
   // BAD: Directly inserting user input
   element.innerHTML = userInput;

   // GOOD: Using textContent or proper escaping
   element.textContent = userInput;
   ```

   **Command Injection:**
   ```python
   # BAD: Using shell=True with user input
   subprocess.run(f"ls {user_path}", shell=True)

   # GOOD: Using list args without shell
   subprocess.run(["ls", user_path])
   ```

5. **Authentication & Authorization Review**
   - Check password hashing (bcrypt, argon2)
   - Verify JWT implementation and secret key strength
   - Check for insecure session management
   - Review permission checks on all endpoints
   - Test for privilege escalation

6. **Data Protection Review**
   - Verify PII is encrypted
   - Check for sensitive data in logs
   - Review data retention policies
   - Check for secure data deletion
   - Verify HTTPS enforcement

7. **Configuration Security**
   - Environment variables for secrets
   - No secrets in version control
   - Secure defaults
   - Principle of least privilege
   - Security headers configured

8. **Run Security Tools**
   - **SAST** (Static Analysis): `bandit` (Python), `eslint-plugin-security` (JS)
   - **Dependency Check**: As mentioned in step 2
   - **Secret Scanning**: `trufflehog`, `gitleaks`
   - **Docker**: `trivy`, `docker scan`

## Security Checklist

- [ ] No hardcoded secrets or credentials
- [ ] Dependencies are up to date and without known vulnerabilities
- [ ] SQL queries use parameterization
- [ ] User input is validated and sanitized
- [ ] Output is properly escaped to prevent XSS
- [ ] Authentication uses strong password hashing
- [ ] Authorization checks on all endpoints
- [ ] HTTPS/TLS enforced
- [ ] Security headers configured (CSP, HSTS, etc.)
- [ ] Error messages don't leak sensitive info
- [ ] Sensitive data encrypted at rest
- [ ] Logging doesn't include sensitive data
- [ ] Rate limiting implemented
- [ ] CSRF protection enabled
- [ ] File uploads validated and restricted
- [ ] No command injection vulnerabilities
- [ ] Session management is secure
- [ ] Security events are logged
- [ ] Principle of least privilege applied

## Output

Provide a security audit report:
- **Executive Summary**: High-level overview of security posture
- **Dependency Vulnerabilities**:
  - Critical/High/Medium/Low counts
  - Specific vulnerable packages
  - Remediation steps
- **Code Security Issues**:
  - Vulnerabilities found by category
  - Severity ratings
  - Code locations
  - Remediation recommendations
- **Configuration Issues**: Misconfigurations found
- **Best Practices**: Areas for improvement
- **Compliance**: OWASP Top 10 coverage
- **Action Items**: Prioritized list of fixes
- **Risk Assessment**: Overall security risk level
