# Prototype guide for Claude Code

Agentic AI system for autonomous tactical command with human override, threat assessment, and learning from engagements.

The source PRD / Epic: https://bytecubed.atlassian.net/browse/AL-372

## How this repo works

Each ticket for this prototype is filed as a GitHub issue. When an issue is opened,
the workflow in `.github/workflows/claude.yml` runs you (Claude Code) to implement it
and open a pull request. Work one issue at a time and keep every change runnable.

## Tech stack & conventions

Python 3.11+ with FastAPI for the agent loop and REST API. Use SQLite for threat history and engagement logs. Implement agents using anthropic/Claude API for reasoning and decision-making (via tool_use for recommendations). Frontend: simple HTML/JS dashboard for command interface and override. Run locally with: python -m uvicorn agent:app --reload. No heavy dependencies—focus on a lean, runnable proof-of-concept that demonstrates perception → assessment → recommendation → override → learning.

## Working agreement

- Build the simplest thing that satisfies the issue's acceptance criteria — this is a
  prototype, not production. Favor a working end-to-end slice over breadth.
- Keep the project runnable at every step. Document any new setup/run command in the
  README under a "Running" section.
- Open one pull request per issue and reference the issue with "Closes #<number>".
- Don't introduce secrets or external services that require credentials the repo
  doesn't have.
