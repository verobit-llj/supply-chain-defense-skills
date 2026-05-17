# Agentic Engineering Patterns

**Version:** 1.0  
**Date:** May 2026

This document collects practical patterns for moving from casual "vibe coding" to disciplined **Agentic Engineering**.

## Core Philosophy

- **Vibe Coding**: Fast, exploratory, low-oversight prompting. Good for prototypes.
- **Agentic Engineering**: Structured, with planning, oversight, decomposition, and security considerations. Required for serious work.

## Key Patterns

### 1. Planning Mode First
Always start with explicit planning before implementation.

**Example prompt:**
> "Think step by step. First, create a detailed plan with clear phases and potential risks. Show me the plan and wait for my approval before coding."

### 2. Human Oversight Loop
Critical changes (auth, payments, dependencies, unsafe code, architecture) must go through human review.

### 3. Multi-Agent Coordination
Break complex tasks across specialized sub-agents (Planner, Implementer, Reviewer, Security Auditor).

### 4. Security by Design
Embed security and supply chain considerations from the very first prompt.

**Example:**
> "When suggesting dependencies, always consider supply chain risks and prefer well-maintained packages."

### 5. Explicit Context & Skills
Use persistent context (`.claude.md`, Skills) and reusable patterns instead of repeating instructions.

### 6. Review & Verification
Never blindly accept generated code. Always review diffs, run tests, and audit dependencies.

## Sources

- Anthropic 2026 Agentic Coding Trends Report
- Andrej Karpathy talks on Vibe Coding vs Agentic Engineering
- Industry best practices from practitioners using Claude Code and similar tools

## Related
See also the Rust + WASM security skills in `skills/rust-wasm-security/`.