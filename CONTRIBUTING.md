# Contributing to MonacoTauri

## Setup

Requirements are in the [README](README.md): macOS with Xcode Command Line Tools, Rust stable, Node.js, and `pnpm`.

```bash
pnpm install
```

## Checks

```bash
pnpm test
```

There is no separate lint or typecheck script; `pnpm test` runs the Jest suite through `react-app-rewired`.

## Try your change

- Web version: `pnpm start`
- Desktop version: `pnpm tauri dev` (web dev server for Tauri: `pnpm start:tauri`, port 4000)

## Pull requests

Create a branch from `main`, keep the change focused, and note in the PR how you verified it (tests plus web or desktop run).
