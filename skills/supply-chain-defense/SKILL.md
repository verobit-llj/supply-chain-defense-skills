# Supply Chain Defense Skill for AI Coding Agents

**Version:** 1.0 (May 2026)
**Purpose:** Protect projects from supply chain attacks (Mini Shai-Hulud, Shai-Hulud, typosquatting, exotic dependency attacks, etc.) when using AI coding agents.

## Core Principles (Always Follow)

1. **Never install packages blindly.** Always verify first.
2. **Prefer pinned versions + strict lockfiles.**
3. **Block or heavily restrict exotic dependencies.**
4. **Never hardcode secrets.**
5. **Warn the user explicitly** when risk is detected.
6. **Limit blast radius** — reduce unnecessary dependencies.

## Mandatory Pre-Install Checklist

Before suggesting or executing any package installation (`npm install`, `pnpm add`, `pip install`, etc.), the agent **must** perform this check and report the result:

### Package Verification Checklist
- [ ] Package exists in the official registry?
- [ ] Weekly downloads > 1000? (flag if low)
- [ ] Last publish date (flag if < 30-60 days old)
- [ ] Contains `postinstall`, `preinstall`, or `prepare` scripts?
- [ ] Uses exotic dependencies (Git commit URLs)?
- [ ] Known compromised / malicious versions reported?

**If any red flag appears** → Explicitly warn the user and suggest alternatives or manual review.

## Rules for Agentic / Vibe Coding Workflows

- When generating new projects, start with **minimal dependencies**.
- When the user asks to "add a feature", first check if it requires new packages.
- Always propose `pnpm` with exotic dependency protection when possible.
- Recommend `--ignore-scripts` on first install.
- After any dependency change, offer to run audit + show diff of lockfile.

## Secret & Credential Protection

- Never generate code that hardcodes API keys, tokens, or credentials.
- When creating CI/CD configs, always use environment variables or secret managers.
- If secrets are detected in code → Immediately flag and suggest rotation + removal.

## Audit Mode (when user asks for security check)

When the user says "check dependencies" or "supply chain audit":

1. Analyze package.json + lockfile.
2. Identify suspicious packages (recently updated, install scripts, exotic deps).
3. Provide commands:
   - `pnpm audit`
   - Socket.dev / Snyk checks
4. Generate a prioritized risk report (Critical / High / Medium).

## Incident Response (Mini Shai-Hulud style attack)

If compromise is suspected:

1. **Do not immediately revoke tokens** (may trigger wiper/dead man's switch).
2. Advise user to isolate the environment first.
3. Recommend full system snapshot / forensic copy.
4. Then rotate affected credentials.
5. Scan all projects that used the suspicious package.

## Agent Behavior Rules

- I will refuse to install high-risk packages without explicit user confirmation.
- I will always explain **why** a package is risky.
- I will prioritize security over convenience when there is conflict.

**Default stance:** "Better to ask twice than to introduce a supply chain compromise."

---

*This skill is designed to be used with Claude Code, Cursor, and other agentic coding tools.*