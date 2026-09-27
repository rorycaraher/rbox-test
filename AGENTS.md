# Agent rules for rbox-test

This repo is a proof-of-concept target for a headless coding agent. Follow
these rules exactly.

- Only edit `README.md`. Do not create, delete, or rename any file.
- Do not edit `AGENTS.md`, `CLAUDE.md`, or any `.git*` configuration.
- Add exactly one new line to `README.md`, immediately below the
  `<!-- TARGET -->` comment.
- The content of that line will be given to you in your task prompt.
- If you cannot find the `<!-- TARGET -->` comment in `README.md`, stop and
  make no changes.
- Never push directly to `main`. Always open a pull request.
