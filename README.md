# Superpowers for Notion

A Notion-native adaptation of the [obra/superpowers](https://github.com/obra/superpowers) software-development methodology.

## What it provides

- Design approval before implementation
- Spike, bounded, and architectural request classification
- Detailed implementation planning
- Red-Green-Refactor TDD
- Root-cause-first debugging
- Parallel task delegation guidance
- Code-review workflows
- Fresh evidence before completion claims
- Safe branch and worktree completion

## Install in Notion

1. Create a new Notion custom agent named **Superpowers for Notion**.
2. Use this description:

   > Disciplined software-development agent adapted from obra/superpowers: brainstorms before coding, writes precise plans, follows TDD, debugs root causes, reviews changes, and verifies evidence before completion.

3. Copy [`agent-instructions.md`](./agent-instructions.md) into the agent's Instructions page.
4. Publish the agent.
5. Run the scenarios in [`validation-scenarios.md`](./validation-scenarios.md).
6. Optionally connect GitHub or another repository integration.

## Compatibility

Notion does not currently expose a public API for installing custom-agent instructions, so installation is manual.

| Superpowers capability | Notion adaptation |
|---|---|
| Session-start plugin hook | Custom-agent instructions |
| Skill discovery | Skill-routing section |
| Git worktrees and terminal | Used when available; otherwise exact handoff commands |
| Subagents | Notion agent sessions when available; otherwise role-based sequential review |
| Ledger files | Durable Notion progress ledger |
| Repository specs and plans | Notion pages or repository documents |

The agent must never claim that code, tests, commits, worktrees, or pull requests were executed when the required runtime is unavailable.

## Smoke test

Prompt:

> I want to build a new expense tracker web app. Follow the Superpowers workflow and do not start implementation yet.

Expected behavior:

- Classifies the request as architectural
- Does not write code
- Offers two or three approaches with trade-offs
- Asks one focused question
- Requires explicit approval before implementation

## Files

- [`agent-instructions.md`](./agent-instructions.md) — complete Notion agent instructions
- [`agent-manifest.json`](./agent-manifest.json) — portable metadata
- [`validation-scenarios.md`](./validation-scenarios.md) — behavioral test cases

## Attribution and license

Adapted from `obra/superpowers`. Distributed under the MIT License; see [`LICENSE`](./LICENSE).
