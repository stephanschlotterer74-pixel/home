# CLAUDE.md

This file provides guidance to Claude Code when working with code in this repository.

## Repository Status

This repository is **currently empty** — no source files, build scripts, or application code exist yet. This file will be updated as the project takes shape.

**Last reviewed:** 2026-05-31

---

## Git & Branch Conventions

- Feature branches follow the pattern `claude/<description>-<id>` (e.g. `claude/claude-md-docs-845PL`)
- Always develop on the designated feature branch; never push directly to `main`
- After pushing a feature branch, always open a **draft PR** immediately
- Commit messages should be descriptive and explain the *why*, not the *what*
- Use `git push -u origin <branch-name>` for first push

---

## Connected MCP Integrations

This Claude Code instance has the following MCP servers available. Use them proactively when relevant to the task.

| Server | Capabilities |
|--------|-------------|
| **GitHub** (`mcp__github__*`) | PRs, issues, file contents, branches, CI, reviews |
| **File System** (`mcp__3ea0d406__*`) | Read, create, copy, search files |
| **Home Assistant** (`mcp__48efbc36__*`) | Smart home control, lights, media, calendar, to-do lists |
| **Spotify** (`mcp__59c1b353__*`) | Music search, playback, playlist creation |
| **Image/Video Generation** (`mcp__83c1eddc__*`) | AI image & video generation, virality prediction |
| **Hugging Face** (`mcp__a15a5524__*`) | Model/dataset search, paper search, Hub queries (user: Steschxx99) |
| **PDF Viewer** (`mcp__a25ce4d9__*`) | List and display PDF files |
| **Canva** (`mcp__d13f868c__*`) | Design creation, editing, export |
| **Gmail** (`mcp__d5c5b96f__*`) | Email threads, labels, drafts |
| **Travel** (`mcp__e6bd173c__*`) | Accommodation search |

---

## Project Initialization Checklist

When source code is first added, update this file with:

### Build & Development Commands
```
# Examples — replace with actual commands once known:
npm run dev          # start dev server
npm run build        # production build
npm test             # run full test suite
npm test -- --watch  # run tests in watch mode
npx jest path/to/test.test.ts  # run a single test file
```

### Architecture Overview
- Describe the top-level directory structure
- Explain how major components interact
- Note any data flow or state management patterns
- List external services / APIs the application depends on

### Non-obvious Conventions
- Naming rules (files, variables, branches)
- Code generation steps (e.g. auto-generated types, migrations)
- Environment variable setup (`.env.example` → `.env`)
- Any gotchas for new contributors

### Linting & Formatting
- Tool used (ESLint, Prettier, Ruff, etc.)
- Command to auto-fix: `npm run lint:fix` / `ruff check --fix`
- Whether lint runs in CI and must pass before merge

---

## Security Notes

- Never commit `.env` files, credentials, API keys, or secrets
- Validate all user input at system boundaries
- Avoid introducing OWASP Top 10 vulnerabilities (XSS, SQLi, command injection, etc.)

---

## Working with Claude Code on the Web

This repository is used with Claude Code running in a **managed remote execution environment** (ephemeral container). Key implications:

- The container is discarded after inactivity — always commit and push work before ending a session
- All changes worth keeping must be on a pushed branch with an open PR
- Environment docs: https://code.claude.com/docs/en/claude-code-on-the-web
