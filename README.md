<p align="center">
  <img src="docs/img/waygate-lockup.png" alt="Waygate" width="460">
</p>

# Waygate

[![Platform](https://img.shields.io/badge/Platform-Windows_10%2F11%2FServer-blue.svg)](#install)
[![Game](https://img.shields.io/badge/Game-Dimraeth-7b5cff.svg)](https://store.steampowered.com/app/2402680/)
[![Players](https://img.shields.io/badge/Players-up_to_8-brightgreen.svg)](#-up-to-eight-players)
[![Server Source](https://img.shields.io/badge/Server_Source-WaygateServer-444.svg)](https://github.com/HumanGenome/WaygateServer)
[![License](https://img.shields.io/badge/License-MIT-lightgrey.svg)](LICENSE)

Waygate gives **Dimraeth** always-on dedicated servers: players join through the Waygate app, hosts run the Waygate server package next to Dimraeth's game files, and the world lives on the server instead of on one player's PC. No waiting for the host to come online, no world that vanishes when they quit.

Every player installs Waygate to join a Waygate server, the host included: Dimraeth's own multiplayer is a Steam lobby owned by whoever is hosting, so the game cannot reach a dedicated server on its own. The app installs once per person and takes a minute. Your copy of Dimraeth is bought, launched, and updated through Steam exactly as normal; Waygate replaces nothing and ships no part of the game.

<p align="center">
  <img src="docs/img/launcher.png" alt="The Waygate app: saved servers, who is online right now, and a Connect button" width="860">
</p>

## Features

### 🌙 Your world never sleeps
The world lives on the server, not on anyone's PC. One of you explores at noon, another builds the stronghold at midnight, and the same world is waiting for both. When the last player logs off, the server keeps running, keeps saving, and holds the gate open.

<p align="center">
  <img src="docs/img/in-game.png" alt="A hero in a Dimraeth world hosted on a Waygate server" width="860">
</p>

### 🧭 Join by address
Save a server's address once. From then on the app shows the server's status and who is online at a glance, and joining is one click: **Connect** readies Dimraeth and takes you straight into the world. A `waygate://` link from a web page does the same with no typing.

### 🧑‍🤝‍🧑 Up to eight players
The full co-op limit Dimraeth supports, with nobody's PC doing the hosting. Heroes are made in the game, the same as always, and stay with the player who made them; the world stays on the server.

### 👻 Nobody plays the host
A Dimraeth world needs a host character. On a Waygate server that character is invisible, silent and takes no slot, so all eight seats are for real players.

### 🔒 Password if you want one
Set a join password on the server and only the people you gave it to get in. The app asks once and remembers.

### 📡 Server query
The server answers Source A2S query with live status and real player counts, so monitoring tools, Discord bots, and hosting panels can see it.

### 🚦 Refuses to run broken
If the server cannot come up healthy, it refuses to start and writes exactly what stopped it to its boot report, instead of limping up half-working with no way to tell.

## Install

### Managed hosting
[Dimraeth hosting from SurvivalServers.com](https://www.survivalservers.com/services/game_servers/dimraeth/?utm_source=github&utm_medium=readme_install&utm_campaign=waygate) comes with Waygate installed and kept up to date, the ports open, and a connect link ready to hand to your players.

### Players
1. Download `WaygateSetup-<version>.exe` from the [latest release](https://github.com/HumanGenome/Waygate/releases/latest).
2. Run the installer. It is a one-time install per person.
3. Open Waygate, add the server address your host gave you, and click **Connect**. The app readies Dimraeth and takes you in. Heroes are made in the game, the same as always.

### Self-hosted servers
Downloads and setup live in [HumanGenome/WaygateServer](https://github.com/HumanGenome/WaygateServer). You will need a Windows machine, a copy of Dimraeth's game files on it (from your own Steam copy; the server package ships no part of the game), and two open UDP ports.

## Releases

This repo publishes the player side:

- `WaygateSetup-<version>.exe`, the installer for players
- Release notes for each version

The server package for hosts lives on the [WaygateServer release page](https://github.com/HumanGenome/WaygateServer/releases/latest), and the public changelog for both sides is [WaygateServer's CHANGELOG.md](https://github.com/HumanGenome/WaygateServer/blob/main/CHANGELOG.md).

## Source

Waygate is split into two repos:

- **Waygate** (this repo): the player side, the desktop app players install, plus the public downloads and documentation.
- **[WaygateServer](https://github.com/HumanGenome/WaygateServer)**: the dedicated server package hosts run next to Dimraeth's game files.

Players only need this repo's releases; hosts run the server from WaygateServer's.

## FAQ

### Do all my friends need the app?
Yes, and so do you. Dimraeth cannot reach a Waygate server without it. It installs once per person, and normal Dimraeth co-op still works whenever you want it.

### Do I need to leave my PC on?
No. That is the entire point. Once the world is on a server, your machine has nothing to do with it.

### Does this change my copy of Dimraeth?
No. You buy, run, and update Dimraeth through Steam as normal, and your ordinary single-player and co-op games are untouched.

### Where is my hero saved?
On your own PC, in the same place Dimraeth always keeps it. The server holds the world; you bring the hero.

### Can I move a world between servers?
Yes. World saves are ordinary files, so a host can copy one across.

### Is this an official Dimraeth feature?
No. Waygate is an independent community project. Mudtek does not ship dedicated servers for Dimraeth, which is why this exists.

### Where do I report a problem?
[Open an issue](https://github.com/HumanGenome/Waygate/issues). If you rent a managed server, your host handles billing and control-panel questions.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md). Security issues go through [private reporting](.github/SECURITY.md), never a public issue.

## Community note

Waygate is an independent community project. It is not affiliated with, endorsed by, or supported by Mudtek.

## License

MIT — see [LICENSE](LICENSE).
