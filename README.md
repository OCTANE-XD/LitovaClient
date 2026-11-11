# Litova Client

A Minecraft: Java Edition launcher for Windows, built with Tauri 2, Rust and React. Each instance is fully isolated, with its own version, loader, mods, configs and saves.

Not affiliated with Mojang or Microsoft. You need a Microsoft account that owns Minecraft: Java Edition to play. There are no offline or cracked accounts.

## Features

- Every Minecraft version from 1.21 onward, read live from Mojang's official manifest
- Isolated instances: create, rename, duplicate, delete, and per-instance Java, memory and JVM arguments
- Vanilla and Fabric, with Fabric the default for new instances
- Modrinth mod and modpack browsing, with dependency resolution and compatibility checks
- Drag-and-drop `.jar` and `.mrpack` install, validated before anything is copied
- Skins page with a 3D preview, your own skin library, starter skins, and player skin lookup
- Discord status showing what you're playing, with privacy controls
- Resumable, hash-verified downloads
- Microsoft sign-in with tokens kept in Windows Credential Manager
- Useful offline: browse instances, manage files, and play on a saved session
- Performance Mode for low-end PCs

## Status

| Area | State |
|---|---|
| Vanilla install from Mojang, downloads, instances, Modrinth mod install, offline use, installer | Verified against real servers or in the built app |
| Fabric on 26.3 | Verified to install and boot; a full game session isn't |
| Microsoft sign-in | Verified live through Microsoft, Xbox Live and XSTS. The Minecraft step needs Mojang's approval |
| Playing a real session | **Not verified.** Needs Mojang's approval |
| Modpack install, Java runtime download, native drag-and-drop | Automated tests only, not run live |
| Applying a skin to a Mojang account | Tested only against a simulated server; needs a real sign-in |

Minecraft's services reject an Azure app until Mojang approves its client ID, so a real session isn't possible yet. See [docs/MICROSOFT_OAUTH_SETUP.md](docs/MICROSOFT_OAUTH_SETUP.md).

Only English is available so far: the language setting exists, but there's no translation layer yet.

## Quick start

You need Node 22+, Rust stable, and the Visual Studio C++ Build Tools with a Windows SDK.

```bash
npm install
```

```bash
npm run tauri dev
```

To build the Windows installer:

```bash
npm run tauri build
```

The installer is written to `src-tauri/target/release/bundle/nsis/`. Set `LITOVA_MS_CLIENT_ID` first to enable sign-in.

## Documentation

- [Microsoft OAuth setup](docs/MICROSOFT_OAUTH_SETUP.md)
- [Discord status setup](docs/DISCORD_SETUP.md)
- [Architecture](docs/ARCHITECTURE.md)
- [Development](docs/DEVELOPMENT.md)
- [Troubleshooting](docs/TROUBLESHOOTING.md)
