<p align="center">
  <img src="docs/img/waygate-lockup.png" alt="Waygate" width="460">
</p>

<p align="center">
  <a href="#install"><img src="https://img.shields.io/badge/Platform-Windows_10%2F11%2FServer-blue.svg" alt="Platform"></a>
  <a href="https://store.steampowered.com/app/2402680/"><img src="https://img.shields.io/badge/Game-Dimraeth-7b5cff.svg" alt="Game"></a>
  <a href="#how-many-players-can-join"><img src="https://img.shields.io/badge/Players-up_to_8-brightgreen.svg" alt="Players"></a>
  <a href="https://github.com/HumanGenome/WaygateServer"><img src="https://img.shields.io/badge/Server_Source-WaygateServer-444.svg" alt="Server Source"></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/License-MIT-lightgrey.svg" alt="License"></a>
</p>

# Waygate

Dimraeth has no dedicated server. Its multiplayer is a Steam lobby hosted from one player's copy of the game. Waygate adds a Dimraeth dedicated server: [WaygateServer](https://github.com/HumanGenome/WaygateServer) runs the game headless on a Windows machine with a public IP and port, and the Waygate app connects players to it by address.

Every player must install Waygate to join a Waygate server. Stock Dimraeth cannot connect to a Waygate server directly.

## Features

### 🗺️ Live map
Every Waygate server serves a page about itself: the world map drawn from the game's own pixels, sharp all the way in to the game's closest zoom, with each player's position every five seconds, the Waygates and crystals they have found, and a fog of war over every region nobody has discovered yet; the console, who is playing and Discord alerts. Players get the map by address; the owner unlocks the rest with the admin password. Details in [WaygateServer](https://github.com/HumanGenome/WaygateServer#the-web-page).

<p align="center">
  <img src="docs/img/web-v0.3.15.png" alt="A Waygate server's own web page: the world map from the game's own pixels with the players' live positions" width="860">
</p>

### 🧭 Join by IP
Add the server's `ip:port` in the app, pick a hero, click Connect. The app puts the connection mod next to your game files, starts Dimraeth and joins the server. The app shows whether the server is up, who is on it and your ping.

<p align="center">
  <img src="docs/img/app-v0.3.15-servers.png" alt="The Waygate app with a saved Dimraeth server online: 2 of 4 players with their time and ping, the hero you play as, and the Connect button" width="860">
</p>

### 🧝 Bring your single-player hero
Heroes are made in the game as always and stay on your PC. The app lists them and you choose which one to bring to a server.

<p align="center">
  <img src="docs/img/app-v0.3.15-characters.png" alt="The Waygate app's Characters window with two heroes on this PC and the one in use highlighted" width="620">
</p>

### 🔒 Password protection
Set one on the server and the app asks for it before connecting.

<p align="center">
  <img src="docs/img/app-v0.3.15-password.png" alt="The Waygate app asking for a server's join password before it connects" width="420">
</p>

### 🖥️ Server console
The Console tab in the app talks to the server's admin port: the live log, the command line and the same commands the server's page has, once the admin password is set.

<p align="center">
  <img src="docs/img/app-v0.3.15-console.png" alt="The Waygate app's Console tab connected to a server, after the status and players commands" width="860">
</p>

### 🧩 Mods
Server mods run on the server and players install nothing. A mod that needs a piece on the player's side is published by the server, and the Mods tab installs it into a profile for that server when you connect, asks once, and removes what a server no longer needs. A plain Steam start of the game never sees any of it.

<p align="center">
  <img src="docs/img/app-v0.3.15-mods.png" alt="The Waygate app's Mods tab for a server that needs nothing on the player's PC" width="860">
</p>

## Install

### Rent a server
[SurvivalServers.com Dimraeth server hosting](https://www.survivalservers.com/services/game_servers/dimraeth/?utm_source=github&utm_medium=readme_install&utm_campaign=waygate) comes with Waygate installed and the ports open. The control panel has an Open in Waygate button that adds the server to the app.

### Players
1. Download `WaygateSetup-latest.exe` from the [latest release](https://github.com/HumanGenome/Waygate/releases/latest/download/WaygateSetup-latest.exe).
2. Run it. If Windows shows "Windows protected your PC", choose More info, then Run anyway. One install per PC.
3. Open Waygate and add the server's IP and port.
4. Pick a hero and click Connect.

### Self-hosted servers
Requirements, ports, setup, the web page, the status file and the commands are in [WaygateServer](https://github.com/HumanGenome/WaygateServer). You need a Windows machine and a copy of Dimraeth's game files on it from your own Steam copy. Hosts can also turn player chat off for the whole server (Dimraeth's own chat setting is per player; this one is enforced on the server). The server answers Source A2S on the port above the gameplay port with its status and player count, and when it cannot start it writes what stopped it to `waygate\boot-report.txt`.

## Releases

This repo publishes the player side: `WaygateSetup-<version>.exe`, a `WaygateSetup-latest.exe` alias, and the release notes. The server package is on the [WaygateServer release page](https://github.com/HumanGenome/WaygateServer/releases/latest), with the changelog for both sides in [WaygateServer's CHANGELOG](https://github.com/HumanGenome/WaygateServer/blob/main/CHANGELOG.md).

## Source

- **Waygate** (this repo): the app players install, the downloads and the documentation.
- **[WaygateServer](https://github.com/HumanGenome/WaygateServer)**: the server package hosts run next to Dimraeth's game files.

## FAQ

### Does everyone need the app?
Yes. The game cannot reach a Waygate server without it.

### How many players can join?
Up to eight, the number Mudtek gives on Dimraeth's [Steam page](https://store.steampowered.com/app/2402680/), and the server has no character of its own, so every seat goes to a player. The first player in leads the party and the rest join it. The most we have seen on one server at once is six. The host sets the server's slot count.

### Does it change my game?
It adds `winhttp.dll`, `doorstop_config.ini`, `.doorstop_version` and the `BepInEx` and `dotnet` folders next to `Dimraeth.exe`. Steam updates the game as normal. Uninstalling the app leaves the game folder alone; delete those five to remove it from the game.

### Does single-player still work?
Yes. Starting Dimraeth from Steam runs the normal game: the mod only acts when the app started the game, and while it does, the game's version corner shows the Waygate version beside the game's. The app updates itself on start.

### Where is my hero saved?
On your PC, where Dimraeth keeps it. The server holds the world.

### Can a world move between servers?
Yes. The world save is a folder on the server; copy it to the other server.

### Why does Windows warn about the installer?
The installer is not code-signed, so Windows SmartScreen may show "Windows protected your PC". Choose More info, then Run anyway.

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
