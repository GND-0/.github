# Security Policy

## Reporting a vulnerability

Please **do not open a public issue** for security problems.

1. **Preferred:** use GitHub's **private vulnerability reporting** on the affected repo (*Security* tab → *Report a vulnerability*).
2. **Or email:** gnd0vlsi@iiitdwd.ac.in with the subject `[SECURITY] <repo name>`.

Include the affected repo, URL or page, steps to reproduce, and the impact you expect. We will acknowledge within **3 days** and keep you updated until it's fixed. With your permission, we'll credit you in the fix.

### In scope
- The club website ([gnd0.vercel.app](https://gnd0.vercel.app/)) and its source in `VLSI_WEB`
- The Sanity content studio (`VLSI-CLUB-SANITY`) and any club API routes
- Leaked credentials in any GND-0 repository
- CI/CD workflows that could be abused (e.g. `pull_request_target` misuse)

### Out of scope
- Bugs in hardware designs: these are normal issues, so open one!
- Denial-of-service or brute-force testing against hosted services
- Social engineering of club members

Please test only against your own accounts and data. Good-faith research that follows this policy will not be reported to the institute.

## 🚨 If you leaked a secret (members, read this)

It happens. Speed matters more than embarrassment.

1. **Revoke or rotate the secret immediately** in its provider (Sanity → API → Tokens, Firebase console, Gmail app passwords, Vercel, and so on). *Deleting the commit does not help.* Bots scrape public commits within minutes.
2. **Tell the Core Team** at gnd0vlsi@iiitdwd.ac.in, or ping `@GND-0/core` in a private channel.
3. Update the new secret in Vercel / GitHub Actions secrets / `.env.local` (never in code).
4. A maintainer will decide whether the Git history also needs cleaning.

## Practices every repo follows
- `.env*` files are git-ignored; each repo ships a `.env.example` with placeholder values only.
- Secrets live in **Vercel environment variables** or **GitHub Actions secrets**, owned by club accounts, never personal ones.
- **Secret scanning and push protection** are enabled on all public repos.
- **Dependabot** alerts and security updates are enabled.
- Workflows use the least `permissions:` needed and never run untrusted PR code with secrets.
