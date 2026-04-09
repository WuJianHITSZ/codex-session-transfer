# Publishing Notes

This file is a lightweight release-prep checklist for publishing `codex-session-transfer` as a public GitHub repository.

## Suggested Publish Checklist

1. Review [SKILL.md](./SKILL.md) for any machine-local paths or private assumptions.
2. Verify [agents/openai.yaml](./agents/openai.yaml) still matches the skill behavior.
3. Review [scripts/install_session_skill_package.py](./scripts/install_session_skill_package.py) for any environment-specific defaults.
4. Confirm that no test packages, local session bundles, or local machine artifacts are included in the repository.
5. Decide whether to add usage examples or screenshots in the repository description or GitHub release notes.

## Why This Repo Shape

This repository keeps the skill files at the root so the folder stays directly installable as a Codex skill.

Only a small set of repository-level files were added:

- [README.md](./README.md)
- [PUBLISHING.md](./PUBLISHING.md)
- [LICENSE](./LICENSE)
- [.gitignore](./.gitignore)

## Recommended First Public Release Scope

Publish the first-phase workflow only:

- `packup`
- `install`
- `list-transactions`
- `rollback`

Keep the later memory-layer migration work as a follow-up release once it is designed and tested.
