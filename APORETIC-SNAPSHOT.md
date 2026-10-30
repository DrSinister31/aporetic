# Aporetic source snapshot

Prepared for private collaboration and Emergent import on October 30, 2026.

Source: stage4-an-shell at 3ad66a994a70a7448880d83dfa17746c766f8f37.
Application source is the committed Stage 4 version; tracked documentation updates from the worktree are included. Untracked scripts are excluded.

This repository starts with fresh history. Local app data, credentials, environment files, databases, evidence/screenshots, build output, and inherited GitHub workflows are excluded. Recorded test bearer tokens are redacted.

The Electron application is in packages/desktop; the web interface is in packages/app; the agent engine is in packages/core. The upstream monorepo retains OpenCode package names. Use Bun as specified in package.json. The Windows desktop host requires an appropriate Windows environment; browser-based development tools may support only the web portion.

Source packaging and secret checks were performed. A fresh build and runtime test have not been performed for this snapshot. Existing license and attribution files are retained.
