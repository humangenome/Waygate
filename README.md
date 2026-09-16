<p align="center">
  <img src="docs/img/waygate-lockup.png" alt="Waygate" width="460">
</p>

# Waygate

[![Platform](https://img.shields.io/badge/Platform-Windows_10%2F11%2FServer-blue.svg)](#install)
[![Game](https://img.shields.io/badge/Game-Dimraeth-7b5cff.svg)](https://store.steampowered.com/app/2402680/)
[![Server Source](https://img.shields.io/badge/Server_Source-WaygateServer-444.svg)](https://github.com/HumanGenome/WaygateServer)
[![License](https://img.shields.io/badge/License-MIT-lightgrey.svg)](LICENSE)

Waygate is a Windows app that connects your copy of [Dimraeth](https://store.steampowered.com/app/2402680/) to a dedicated server. Dimraeth's own multiplayer is a Steam lobby run from one player's game. There is no dedicated server and no way to join by address. [WaygateServer](https://github.com/HumanGenome/WaygateServer) runs the game as a server; this app joins it.

<p align="center">
  <img src="docs/img/launcher.png" alt="The Waygate app: saved servers, player count, Connect" width="860">
</p>

## What you need

- Dimraeth installed from Steam. The app starts your own copy of the game.
- Windows 10, 11 or Server.
- The server address as `ip:port`, and the join password if the server has one.

## Install

1. Download `WaygateSetup-latest.exe` from the [latest release](https://github.com/HumanGenome/Waygate/releases/latest/download/WaygateSetup-latest.exe).
2. Run it. One install per PC.
3. Open Waygate, add the server address, pick a character, click Connect.

Characters are your normal Dimraeth heroes and stay on your PC. The world save is on the server.

<p align="center">
  <img src="docs/img/in-game.png" alt="A Dimraeth world on a Waygate server" width="860">
</p>

## How it works

- The server runs Dimraeth with no screen and no Steam login, listening on a UDP port. A mod switches the game to direct connections.
- The app puts the same mod next to your game files, writes the server address into it, and starts the game. The game connects on its own.
- Starting Dimraeth from Steam afterwards runs the plain game. The mod only acts when Waygate started the game.
- The app updates itself on start.

## Running your own server

Requirements, ports, setup, the status file and the commands are in [WaygateServer](https://github.com/HumanGenome/WaygateServer). If you would rather not run a machine, [SurvivalServers.com](https://www.survivalservers.com/services/game_servers/dimraeth/?utm_source=github&utm_medium=readme_install&utm_campaign=waygate) rents them with Waygate preinstalled.

## Questions

**Does everyone need the app?** Yes. The game cannot reach a Waygate server without it.

**Does it change my game?** It adds `winhttp.dll` and a `BepInEx` folder next to `Dimraeth.exe`. Steam updates the game as normal. Delete those two to remove it.

**Where is my hero saved?** On your PC, where Dimraeth keeps it.

**Is this official?** No. Waygate is an independent project and is not affiliated with Mudtek.

**Something broke.** [Open an issue](https://github.com/HumanGenome/Waygate/issues). Security issues go through [private reporting](.github/SECURITY.md).

## License

MIT, see [LICENSE](LICENSE).
