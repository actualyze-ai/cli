<p align="center">
  <a href="https://actualyze.ai/">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="https://actualyze.ai/brand/logo-horizontal-dark.svg">
      <img src="https://actualyze.ai/brand/logo-horizontal-light.svg" alt="Actualyze" width="320">
    </picture>
  </a>
</p>

# Actualyze CLI

Official release binaries for the [Actualyze](https://actualyze.ai/) command-line interface, `actualyze`.

This repository hosts **releases only** — binaries, checksums, install scripts, a changelog, an SPDX SBOM, and third-party license notices are published here for every CLI release. Source code is developed in a private repository.

## Install

**Linux/macOS:**

```sh
curl -fsSL https://github.com/actualyze-ai/cli/releases/latest/download/install.sh | sh
```

**Windows (PowerShell):**

```powershell
irm https://github.com/actualyze-ai/cli/releases/latest/download/install.ps1 | iex
```

The command installs to `~/.local/bin/actualyze` on Linux/macOS and `%LOCALAPPDATA%\actualyze\bin\actualyze.exe` on Windows; set `ACTUALYZE_INSTALL_DIR` to choose a different directory. To install a specific version, set `ACTUALYZE_VERSION` (e.g. `ACTUALYZE_VERSION=12.0.0`) before running the script, or download binaries directly from the [releases page](https://github.com/actualyze-ai/cli/releases).

Supported platforms: Linux (x64, arm64), macOS (x64, arm64), Windows (x64).

## Getting started

The CLI talks to the Actualyze SaaS (`https://app.actualyze.ai`) out of the box — there is nothing to configure before logging in. Authenticate by pairing with your browser session:

```sh
actualyze auth login
```

If your organization runs its own Actualyze deployment, set the `ACTUALYZE_URL` environment variable to its URL before logging in. The full walkthrough — including the interactive TUI and the agent skill — is in the CLI getting-started guide in the product's Get help section.

## What you get

- One-shot commands for scripts and quick lookups — add `--json` for machine-readable output
- An interactive TUI (`actualyze tui`) with TAB completion and live panes
- Shell completions: `actualyze completion bash|zsh|fish`
- An agent skill (`actualyze skill`) that teaches AI coding agents how to drive the CLI

## Verify

Every release ships a `checksums.txt`. The install scripts verify SHA-256 checksums automatically after download, and the built-in self-updater verifies the same checksums as it downloads.

## Updating

Native installs (from the scripts above) keep themselves current: the CLI checks for new releases in the background and prints a notice when one is available, and `actualyze update` downloads, verifies, and installs the update in place. Installs managed by a package manager defer to that manager's own update mechanism. Set `ACTUALYZE_NO_UPDATE_CHECK=1` to suppress the background check and notice — useful in CI pipelines and scripts.

## License

The Actualyze CLI is proprietary software © ActualyzeAI, Inc. Third-party license notices ship with each release as `NOTICE.txt`.
