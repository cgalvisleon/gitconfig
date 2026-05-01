# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Purpose

This is a personal git configuration reference repository. It contains a single `README.md` with git alias setup commands and workflow documentation for Cesar Galvis Leon (`cgalvisleon@gmail.com`).

## Repository Contents

`README.md` is a reference document — not a script. It contains:

- **Global git aliases** to set via `git config --global alias.<name> "..."` — covering log formatting (`l`), status (`s`), branch operations (`new`, `set`, `del`, `lb`), commit/push workflows (`backup`, `feat`, `fix`, `deploy`, `review`), tag management, and reset shortcuts (`rhs`, `rhh`).
- **Two remote targets**: `origin` (GitHub personal, `github-cgalvisleon`) and `josephine` (Celsia, `github-celsia`). Aliases prefixed with `j` target `josephine`.
- **SSH multi-account config** for `~/.ssh/config` with separate key files per identity.
- **Gitignore troubleshooting** commands using `git rm --cached`.
- **Merge/conflict resolution** patterns including `--theirs`/`--ours` strategies.
- **History rewriting** via `git filter-repo` (requires `brew install git-filter-repo`).

## Key Aliases (after setup)

| Alias | Effect |
|-------|--------|
| `git l` | Pretty graph log |
| `git s` | Short status with branch |
| `git backup` | add + commit "Backup" + push origin |
| `git feat "<msg>"` | add + commit "Feat:<msg>" + push origin |
| `git fix "<msg>"` | add + commit "fix:<msg>" + push origin |
| `git rhs` | `reset HEAD^ --soft` |
| `git rhh` | `reset HEAD^ --hard` |
| `git new <branch>` | `checkout -b` |
| `git tags` | push all tags to origin |
