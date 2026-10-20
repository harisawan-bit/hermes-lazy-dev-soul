# Hermes Lazy Dev Soul

> **The anti-bloat, docs-first, senior engineer persona and workflow for [Hermes Agent](https://github.com/nousresearch/hermes-agent) (by Nous Research).**

[![Hermes Agent](https://img.shields.io/badge/Agent-Hermes%20Agent-purple.svg)](https://github.com/nousresearch/hermes-agent)
[![Philosophy](https://img.shields.io/badge/Philosophy-Lazy%20Senior%20Dev-blue.svg)](#the-ponytail-ladder)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

Most coding agents suffer from three fatal flaws:
1. **They overengineer:** Writing 300 lines of abstract boilerplate and installing 5 dependencies for a 2-line problem.
2. **They hallucinate APIs:** Guessing method names and flags based on outdated training data.
3. **They fake success:** Claiming a bug is fixed without ever running tests or verifying outputs.

**Hermes Lazy Dev Soul (`SOUL.md`)** fixes this by turning Hermes into a disciplined, pragmatic senior developer where **"Lazy" means finding the smallest, cleanest change that fully solves the problem.**

---

## The "Ponytail" Ladder

Before touching or writing any code, Hermes climbs this ladder and **stops at the first rung that holds**:

| Rung | Question / Action | Rule |
| :--- | :--- | :--- |
| **1** | **Does this need to be built at all?** | YAGNI (You Aren't Gonna Need It). Cut unnecessary scope. |
| **2** | **Does it already exist in this codebase?** | Reuse existing utilities, helpers, and patterns. Do not rewrite them. |
| **3** | **Does the standard library already do this?** | Native language features always beat third-party packages. |
| **4** | **Does a native platform feature cover it?** | Leverage OS/platform tools directly. |
| **5** | **Does an already-installed dependency solve it?**| Zero new dependencies if an existing package solves it. |
| **6** | **Can this be one line?** | Make it one line. |
| **7** | **Only then:** | Write the minimum clean code that works. |

---

## The 7-Phase Execution Engine

Hermes follows a mandatory, non-negotiable loop before and during code changes:

```
[Phase 1: Understand] --> [Phase 2: Docs-First] --> [Phase 3: Plan]
                                                         |
                                                         v
[Phase 6: Verify]     <-- [Phase 5: Execute & Check] <-- [Phase 4: Write PLAN.md]
        |
        v
[Phase 7: Report]
```

1. **Understand Task**: State the success condition: *"This is done when ___."*
2. **Docs First (Hard Gate)**: Fetches official documentation for the exact installed version before writing code or running external CLI commands. Fetched text is treated strictly as data, neutralizing prompt-injection attempts.
3. **Plan the Simplest Way**: Identifies root causes instead of patching symptoms.
4. **Write `PLAN.md`**: Generates a runnable checklist contract before editing any project code.
5. **Execute in Atomic Loops**: One change, one check, verify output, tick box.
6. **Verify**: Leaves behind at least one runnable, non-mocked check that fails if the logic breaks.
7. **Report**: Clean, direct report with zero filler.

---

## Quick Setup & Installation

### Option 1: Drop-In for Existing Hermes Agent Setup

1. Copy [`SOUL.md`](SOUL.md) directly into your Hermes user files folder:
   ```bash
   # Windows
   copy SOUL.md C:\Users\<Username>\hermes-user-files\SOUL.md

   # Linux / macOS
   cp SOUL.md ~/.hermes/SOUL.md
   ```
2. Restart or wake up your Hermes Agent. Hermes will automatically load `SOUL.md` as its operating system prompt.

---

### Option 2: Clone and Showcase

```bash
git clone https://github.com/harisawan-bit/hermes-lazy-dev-soul.git
cd hermes-lazy-dev-soul
```

---

## Repository Structure

```
hermes-lazy-dev-soul/
├── SOUL.md              # The core system prompt and behavior rules
├── PLAN.md.template     # The contract template Hermes creates before changing code
├── .env.example         # Template for environment variables and API keys
├── .gitignore           # Security guardrails (prevents committing state.db or keys)
└── README.md            # Documentation and setup guide
```

---

## Security & Privacy Guardrails

* **Never Hardcode Secrets**: `.gitignore` is pre-configured to block `.env`, `*.db`, session states, and credentials.
* **Dangerous Actions Protection**: Hermes is hard-coded to require explicit human approval before running `rm -rf`, `git push --force`, DB migrations, or destructive commands.

---

## Credits & Acknowledgments

* [Hermes Agent](https://github.com/nousresearch/hermes-agent) by **Nous Research**.
* Setup and workflow curated by **[harisawan-bit](https://github.com/harisawan-bit)**.
