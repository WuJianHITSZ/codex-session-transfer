[English](./README.md) | [简体中文](./README.zh-CN.md)

# skill-codex-session-transfer

`skill-codex-session-transfer` 是 `codex-session-transfer` 这个 Codex 技能的公开 GitHub 仓库。

这个技能用于打包、安装、重挂靠以及回滚本地 Codex Desktop 会话迁移。

## 它能做什么

- 为指定 Codex 会话打包第一阶段“最小可工作集”
- 把会话技能包安装到另一套 Codex Desktop 环境
- 按目标机器环境对工作目录路径进行本地化
- 记录事务日志和备份，以支持安全回滚
- 列出迁移事务，并在需要时执行回滚

## 技能名与仓库名

GitHub 仓库名是 `skill-codex-session-transfer`。

真正的可安装 Codex 技能名仍然是 `codex-session-transfer`，这个名字定义在 [SKILL.md](./SKILL.md) 中。安装到 Codex 时，目标目录应为：

```text
~/.codex/skills/codex-session-transfer/
```

## 仓库结构

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

## 主要工作流

这个技能围绕同一条迁移生命周期提供四个动作：

- `packup`
- `install`
- `list-transactions`
- `rollback`

核心实现位于 [scripts/install_session_skill_package.py](./scripts/install_session_skill_package.py)。

## 当前范围

当前仓库聚焦第一阶段的“最小可工作集”：

- rollout `jsonl` 文件
- `threads`
- `session_index`
- `thread_dynamic_tools`
- 用户自定义技能
- 所需的空目录骨架

暂时还不迁移：

- `logs_1.sqlite`
- `state_5.sqlite.logs`
- `state_5.sqlite.stage1_outputs`
- `.codex-global-state.json`

## 说明

- 这个仓库已经按公开 GitHub 发布的方向整理。
- 最终仍需要补一个正式的开源许可证，见 [LICENSE-DECISION.md](./LICENSE-DECISION.md)。
