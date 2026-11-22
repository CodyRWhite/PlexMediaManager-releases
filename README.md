# Plex Media Manager — releases

This repository publishes **release information** for Plex Media Manager (PMM). The application's source code is
private for now; this feed is public so that every install can see which version is the latest.

- [`releases.json`](releases.json) — machine-readable feed, read by PMM's **System → Updates** page.
- [`notes/`](notes/) — release notes per version, in Markdown.

## Versions

PMM uses four-part versions: **MAJOR.MINOR.RELEASE.BUGFIX**

| Part | Increases when |
|---|---|
| MAJOR | Breaking changes (database or worker protocol), with a migration |
| MINOR | A feature release |
| RELEASE | A release without new features (refactors, performance, packaging) |
| BUGFIX | Fixes only |

Channels: **release** (stable, deployed) and **develop** (preview builds, never auto-deployed).

## Feed format

```json
{
  "schema": 1,
  "updated": "2026-11-22T00:00:00Z",
  "channels": {
    "release": { "latest": "0.2.0.0" },
    "develop": { "latest": null }
  },
  "releases": [
    {
      "version": "0.2.0.0",
      "channel": "release",
      "date": "2026-11-22",
      "notes": "notes/0.2.0.0.md",
      "docker": "ghcr.io/codyrwhite/plexmediamanager:0.2.0.0",
      "worker_flatpak": "0.2.0.0",
      "min_worker": "0.2.0.0",
      "highlights": { "new": [], "fixed": [], "changed": [] }
    }
  ]
}
```

This repository is updated automatically by the application's release pipeline.
