# Backend provenance

This fork (`vjfrosty/OpenBot`) restores the OpenBot backend that upstream removed from its public
repository. This file records where that code came from, under what license, and when it was pulled.

## License

All of the code described here is **MIT-licensed**, `Copyright (c) 2026 CopilotKit`, as stated in
the `LICENSE` file at the root of every source listed below (checked in each one). The MIT license
lets this fork keep, modify and redistribute the code, provided the copyright notice and license
text stay with it. The `LICENSE` file at the root of this repository is that same license.

CopilotKit Intelligence, which OpenBot uses, is separately licensed and is **not** part of this
code.

## Why the backend is restored here

Upstream commit `f71b0f4bb6223bc1c7aa0026ad0e3bd5ef9233b0` (2026-11-13 11:46:54 -08:00, "Run the
server from the published OpenBot images", #1530) deleted `server/`, `agent-computer/`,
`supervisor/`, `worker/`, `charts/` and related files from `CopilotKit/OpenBot`. From then on the
backend has run only from prebuilt images (`ghcr.io/copilotkit/openbot-server` and others).

## Sources

All sources were pulled on **2026-11-14** (Europe/Sofia, UTC+02:00).

| Source | Upstream commit | Upstream date | Pulled | Used on branch |
| --- | --- | --- | --- | --- |
| `CopilotKit/OpenBot` `main`, the last commit before the removal | `6d1919a3b53a0730894258f197f3beb4e8db4f2f` ("Remove the end-to-end suite from this repo", #1567) | 2026-11-13 10:34:41 -08:00 | 2026-11-14, ~11:20 EET | `add-backend-6d1919a` (PR #2), `upstream-6d1919a-with-backend` (unchanged snapshot) |
| Release asset `openbot-source.tar.gz` of release **v1.0.3** | `8e4427296b47b40face336d030d747e344e964a8` (tag `v1.0.3`, "Release v1.0.3", #1590) | 2026-11-13 19:45:33 -08:00 | 2026-11-14, ~11:15 EET | `add-backend-v1.0.3` (PR #1, closed) |

- Release tarball URL:
  `https://github.com/CopilotKit/OpenBot/releases/latest/download/openbot-source.tar.gz`
- Release tarball SHA-256: `241bfbb21f0959bb217f461c3fd893ded4a1178d559101c0cc0322b0d2f877f3`
- The frontend this backend was added to is this fork's `main` at
  `f29e647fe8adeb2251e5147dff1c9b6c99f95400` (2026-11-13 21:32:42 -08:00, "Run on CopilotKit
  1.88.0", #1578).

## What was added

The files were copied unchanged and only added; no existing file was modified:

- `server/`, `agent-computer/`, `supervisor/`, `worker/`, `toolkit/`, `agent-bot/`,
  `agent-langgraph/`, `charts/`, `docker/`, `spire/`, and the root `Dockerfile`
- On `add-backend-6d1919a` only: the chart and server scripts and tests under `scripts/`, `tests/`,
  `app/tests/` and `desktop/scripts/` that `f71b0f4` removed along with them

Database migrations: up to `0091_remote_mcp_oauth` on `add-backend-6d1919a`, and up to
`0088_approval_reviewer_guidance` on `add-backend-v1.0.3`.
