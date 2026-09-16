<p align="center">
  <img src="docs/img/waygate-lockup.png" alt="Waygate" width="460">
</p>

# Waygate

[![Platform](https://img.shields.io/badge/Platform-Windows_10%2F11%2FServer-blue.svg)](#install)
[![Game](https://img.shields.io/badge/Game-Dimraeth-7b5cff.svg)](https://store.steampowered.com/app/2402680/)
[![Players](https://img.shields.io/badge/Players-up_to_8-brightgreen.svg)](#-eight-players-eight-seats)
[![Server Source](https://img.shields.io/badge/Server_Source-WaygateServer-444.svg)](https://github.com/HumanGenome/WaygateServer)
[![License](https://img.shields.io/badge/License-MIT-lightgrey.svg)](LICENSE)

Waygate is the player app and server package for **Dimraeth** dedicated servers. Dimraeth's own multiplayer is a Steam lobby run from one player's game. [WaygateServer](https://github.com/HumanGenome/WaygateServer) runs the game as a server on a UDP port, and this app connects your copy of the game to it by address.

Every player installs the app. It starts your own Steam copy of Dimraeth, so the game has to be installed on the same PC.

<p align="center">
  <img src="docs/img/launcher.png" alt="The Waygate app: a saved server with its player count and a Connect button" width="860">
</p>

## Features

### 🏰 The server runs with nobody on it
The save sits on the server and the game keeps running there with zero players connected. No player's PC is involved. Log in whenever you like and the world is where the last person left it.

<p align="center">
  <img src="docs/img/in-game.png" alt="A Dimraeth world on a Waygate server" width="860">
</p>

### 🧭 Join by address
Add the server's `ip:port` in the app, pick a character, click Connect. The app puts the connection mod next to your game files, starts Dimraeth and joins the server. The app shows whether the server is up and how many players are on it.

### 👥 Eight players, eight seats
Dimraeth's own co-op limit is eight. The server's host character takes no seat, is hidden from the player list and belongs to no party, so every seat goes to a player. The first player in leads the party and the rest join it.

### 🧝 Your own characters
Heroes are made in the game as always and stay on your PC. The app lists them and you choose which one to bring to a server.

### 🔒 Join password
Set one on the server and the app asks for it before connecting.

### 💬 Chat switch
The host can turn player chat off for the whole server. Dimraeth's own chat setting is per player; this one is enforced on the server.

### 📡 Server query
The server answers Source A2S on the port above the gameplay port with its status and player count, so monitoring tools and hosting panels can read it.

### 🚦 Boot report
If the server cannot start, it writes what stopped it to `waygate\boot-report.txt` and refuses to run. It does not come up half working.

### 🔄 Plain game afterwards
Starting Dimraeth from Steam after a Waygate session runs the normal game. The mod only acts when the app started the game. The app updates itself on start.

<p align="center">
  <img src="docs/img/exploring.png" alt="Exploring a Dimraeth world hosted on a Waygate server" width="860">
</p>

## Install

### Managed hosting
[SurvivalServers.com](https://www.survivalservers.com/services/game_servers/dimraeth/?utm_source=github&utm_medium=readme_install&utm_campaign=waygate) rents Dimraeth servers with Waygate preinstalled. The control panel has an Open in Waygate button that adds the server to the app.

### Players
1. Download `WaygateSetup-latest.exe` from the [latest release](https://github.com/HumanGenome/Waygate/releases/latest/download/WaygateSetup-latest.exe).
2. Run it. One install per PC.
3. Open Waygate, add the server address, pick a character, click Connect.

### Self-hosted servers
Requirements, ports, setup, the status file and the commands are in [WaygateServer](https://github.com/HumanGenome/WaygateServer). You need a Windows machine and a copy of Dimraeth's game files on it from your own Steam copy.

## Releases

This repo publishes the player side: `WaygateSetup-<version>.exe`, a `WaygateSetup-latest.exe` alias, and the release notes. The server package is on the [WaygateServer release page](https://github.com/HumanGenome/WaygateServer/releases/latest), with the changelog for both sides in [WaygateServer's CHANGELOG](https://github.com/HumanGenome/WaygateServer/blob/main/CHANGELOG.md).

## Source

- **Waygate** (this repo): the app players install, the downloads and the documentation.
- **[WaygateServer](https://github.com/HumanGenome/WaygateServer)**: the server package hosts run next to Dimraeth's game files.

## FAQ

### Does everyone need the app?
Yes. The game cannot reach a Waygate server without it.

### Does it change my game?
It adds `winhttp.dll` and a `BepInEx` folder next to `Dimraeth.exe`. Steam updates the game as normal. Delete those two to remove it.

### Where is my hero saved?
On your PC, where Dimraeth keeps it. The server holds the world.

### Can a world move between servers?
Yes. The world save is a folder on the server; copy it to the other server.

### Is this official?
No. Waygate is an independent project. Mudtek does not ship dedicated servers for Dimraeth.

### Something broke
[Open an issue](https://github.com/HumanGenome/Waygate/issues). If you rent a server, your host handles billing and control panel questions.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md). Security issues go through [private reporting](.github/SECURITY.md), never a public issue.

## Community note

Waygate is an independent community project. It is not affiliated with, endorsed by, or supported by Mudtek.

## License

MIT, see [LICENSE](LICENSE).
