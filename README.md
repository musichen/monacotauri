# MonacoTauri

A quick experiment combining [Tauri](https://tauri.app/) and the
[Monaco Editor](https://microsoft.github.io/monaco-editor/) in a lightweight
macOS desktop editor.

This project began from
[TimSusa/montauri-editor](https://github.com/TimSusa/montauri-editor) and was
updated to Tauri 2 so it builds on current macOS, Xcode and Rust toolchains.

## Requirements

- macOS with Xcode Command Line Tools installed
- Rust stable (`rustup` and `cargo`)
- Node.js and `pnpm`

## Install

```sh
pnpm install
```

## Run

Run the web version in a browser:

```sh
pnpm start
```

Run the Tauri desktop app in development mode:

```sh
pnpm tauri dev
```

## Build For macOS

Build the macOS application and Apple Silicon DMG installer:

```sh
pnpm run bundle
```

Artifacts are written to:

```text
src-tauri/target/release/bundle/macos/MonacoTauri.app
src-tauri/target/release/bundle/dmg/MonacoTauri_0.1.0_aarch64.dmg
```

The build uses non-interactive DMG packaging so it runs reliably from a
terminal without waiting for Finder automation.

## Development scripts

All scripts are defined in `package.json`:

| Script | Description |
| --- | --- |
| `pnpm start` | Run the web version in a browser (Webpack dev server) |
| `pnpm start:tauri` | Run the web version on port 4000 for Tauri development |
| `pnpm tauri dev` | Run the Tauri desktop app in development mode |
| `pnpm run build` | Build the web version for production |
| `pnpm run bundle` | Build the macOS app and DMG installer (see Build For macOS) |
| `pnpm test` | Run the Jest test suite via `react-app-rewired` |

## Notes

- The original UI is based on React and `react-monaco-editor`.
- Monaco is pinned to the version compatible with the original Webpack
  integration.
- The native wrapper has been migrated from pre-1.0 Tauri to Tauri 2.

## License

MIT. See [LICENSE](LICENSE).
