# Codex configuration

Personal Codex CLI and desktop configuration tracked directly from `~/.codex`.

## Versioned files

- `config.toml`: Codex settings, permissions, integrations, and terminal UI configuration.
- `.gitignore`: Default-deny protection for credentials and runtime state.
- `README.md`: Repository purpose and operating notes.

Everything else is ignored by default. This prevents accidental commits of:

- `auth.json` and OAuth state
- sessions, prompts, history, attachments, and memories
- SQLite databases and their WAL/SHM files
- logs, caches, temporary files, locks, and shell snapshots
- generated images and visualizations
- installed plugins, system skills, models, and vendor imports
- machine identifiers, migration markers, backups, and application state

OpenAI documents that `auth.json` can contain access tokens and must not be
committed or shared. See the [Codex authentication documentation](https://learn.chatgpt.com/docs/auth).

## Daily use

```bash
cd ~/.codex
git status
git diff
git add config.toml
git commit -m "chore(config): update Codex settings"
git push
```

## Notes

- The repository is public. Review `config.toml` before committing new values.
- `config.toml` contains machine-specific paths and may need adjustment on another computer.
- To version another durable file, explicitly add an allowlist exception to `.gitignore` first.
