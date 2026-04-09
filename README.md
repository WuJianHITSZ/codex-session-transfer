[English](./README.md) | [简体中文](./README.zh-CN.md)

# skill-codex-session-transfer

`skill-codex-session-transfer` is the public GitHub repository for the `codex-session-transfer` Codex skill.

The skill helps you package, install, re-home, and roll back local Codex Desktop session migrations.

## What It Does

- Package the first-phase minimum working set for selected Codex sessions
- Install a session skill package onto another Codex Desktop environment
- Localize working-directory paths for the destination machine
- Record transaction logs and backups for safe rollback
- List migration transactions and roll them back when needed

## Skill Name vs Repository Name

The GitHub repository is named `skill-codex-session-transfer`.

The installable Codex skill name remains `codex-session-transfer`, as defined in [SKILL.md](./SKILL.md). When you install it into Codex, place the folder at:

```text
~/.codex/skills/codex-session-transfer/
```

## Repository Layout

```text
skill-codex-session-transfer/
  SKILL.md
  agents/
    openai.yaml
  references/
    package-format.md
  scripts/
    install_session_skill_package.py
  README.md
  README.zh-CN.md
  PUBLISHING.md
  LICENSE-DECISION.md
  .gitignore
```

## Primary Workflow

This skill provides one migration lifecycle with four actions:

- `packup`
- `install`
- `list-transactions`
- `rollback`

The main implementation lives in [scripts/install_session_skill_package.py](./scripts/install_session_skill_package.py).

## Current Scope

This repository currently focuses on the first-phase minimum working set:

- rollout `jsonl` files
- `threads`
- `session_index`
- `thread_dynamic_tools`
- user-defined skills
- required empty directory skeletons

It does not yet migrate:

- `logs_1.sqlite`
- `state_5.sqlite.logs`
- `state_5.sqlite.stage1_outputs`
- `.codex-global-state.json`

## Notes

- The repository is prepared for public GitHub distribution.
- A final open-source license still needs to be chosen. See [LICENSE-DECISION.md](./LICENSE-DECISION.md).
