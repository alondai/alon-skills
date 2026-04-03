[简体中文](./README.zh.md)

# Alon GitHub Security Audit Skill

Audit GitHub repositories or local codebases for malicious code, backdoors, and supply-chain risk without executing the target project by default.

## Quick Install

```bash
npx skills add alondotsh/alon-skills --skill alon-github-security-audit
```

## When to Use

Use this skill when you want to:

- audit a GitHub repository before installing or trusting it
- review a local codebase for malicious behavior
- inspect agent skills, automation tools, or installer scripts
- perform a static-first security review before any deeper investigation

Typical user prompts:

- `审计下 https://github.com/owner/repo`
- `审计当前目录`
- `audit this repo`
- `check repo security`

## What It Does

- performs a default offline static audit
- inspects network indicators, exfiltration paths, obfuscation, and install chains
- adds a source-and-permissions preflight for skills and automation tools
- can optionally extend into online dependency vulnerability intelligence after confirmation
- writes a structured audit report to a user-specified directory or the default local report directory

## Requirements

- `git`
- `python3`

## Safety and Limits

- default mode is read-only static analysis
- default analysis scope is limited to the target repository or the current working directory
- it does not execute target repository code
- it does not run `npm install`, `pip install`, or similar install steps
- it does not query external vulnerability sources unless the user explicitly approves
- it does not read unrelated home-directory paths such as `~/.ssh` or browser profile data unless the user explicitly expands scope
- local-directory audits do not delete user files
- the default report path is `~/Security-Audit/`, but you can direct reports elsewhere

This skill is designed for triage and security review, not for proving runtime exploitability.

## Output

The audit result includes:

- high-risk entities
- logic risk analysis
- optional supplemental checks
- a final verdict: `Safe`, `Risky`, or `Dangerous`
- an audit report written to the configured local report directory

## Project Structure

```text
alon-github-security-audit/
├── SKILL.md
├── README.md
├── README.zh.md
├── docs/
│   ├── audit-standard.md
│   └── post-audit-review-checklist.md
└── tools/
    ├── clone_repo.py
    └── cleanup.py
```

## Local Development

- Python 3.6+
- Git

The canonical private source lives in the local skills workspace and may contain host-specific private workflow details. Public-safe export cleanup should happen later during release export, not during private development.

In the current private workflow, reports are written to a local report directory and may later be imported into Obsidian by separate tooling.

## About Alon

These public skills come from Alon's real daily workflows.

Alon is actively exploring the future of agent skills and is open to connecting with people who want to build useful skills.

- GitHub: https://github.com/alondotsh
- WeChat Official Account: alondotsh
- X: https://x.com/alondotsh

## License

MIT
