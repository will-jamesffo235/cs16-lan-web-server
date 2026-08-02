# CS 1.6 Web v1 - browser-based game server 2026

> **Bring Counter-Strike 1.6 to the browser for LAN play using a Docker-hosted server, WebRTC networking, and Xash3D WASM v1.**

[![Platform](https://img.shields.io/badge/Platform-Docker-blue?style=flat-square)](https://github.com)
[![Version](https://img.shields.io/badge/Version-v1-green?style=flat-square)](https://github.com)
[![Updated](https://img.shields.io/badge/Updated-2026-red?style=flat-square)](https://github.com)
[![License](https://img.shields.io/badge/License-GPL--3.0-yellow?style=flat-square)](LICENSE)
[![Stars](https://img.shields.io/github/stars/will-jamesffo235/cs16-lan-web-server?style=flat-square)](https://github.com/will-jamesffo235/cs16-lan-web-server)

---

<p align="center">
  <a href="https://will-jamesffo235.github.io/cs16-lan-web-server/">
    <img src="https://img.shields.io/badge/Download-CS%201.6%20Web%20Latest-brightgreen?style=for-the-badge" alt="Download CS 1.6 Web">
  </a>
</p>

> **[Download CS 1.6 Web v1](https://will-jamesffo235.github.io/cs16-lan-web-server/)**

---

[Download Latest Build](https://will-jamesffo235.github.io/cs16-lan-web-server/)

---

## What Is CS 1.6 Web?

CS 1.6 Web is a browser-accessible Counter-Strike 1.6 server intended for multiplayer games on a local network. Docker provides the deployment environment, while WebRTC allows players to connect through a shared browser link without installing a dedicated game client.

Under the hood, the project runs Xash3D compiled to WebAssembly. The browser interface includes map selection and can work with custom `.bsp` maps. This setup is suited to local gaming scenarios that benefit from a single container, straightforward link sharing, and environment-variable-based configuration.

---

## Highlights

- Play Counter-Strike 1.6 in a browser across a LAN
- Deploy the service as one Docker container
- Use WebRTC peer-to-peer connections for players
- Run Xash3D through its WebAssembly build
- Select maps directly from the browser interface
- Load custom `.bsp` map files
- Join without installing software on player devices
- Adjust game behavior with container environment variables

---

## Getting Started

From the project directory, obtain the repository files and launch the Docker service.

1. Download the project:
   - `git clone https://github.com/will-jamesffo235/cs16-lan-web-server.git
   - `cd cs16-web-map-server`

2. Launch the container:
   - `docker compose up -d`
   - Alternatively, use `docker run` with the supplied container settings for a direct startup.

3. Visit the web interface using the host address or the LAN-shared link, then create the game session.

---

## Playing a Session

Once the container is active, use the browser UI to pick a map and start multiplayer play.

A normal session looks like this:

- Start the Docker container.
- Select a map in the web interface.
- Send the generated link to players on the LAN.
- Have each player connect from a browser.
- Add or replace `.bsp` files when you need another map rotation.

For automated deployments, leave the container running and modify the environment variables before restarting the service when configuration changes are required.

---

## Server Settings

Container environment variables provide the primary way to configure the server.

Example:

```text
GAME_NAME=LAN Session
MAP=de_dust2
MAX_PLAYERS=16
```

The server and browser UI manage map files. Put custom `.bsp` files in the location expected by the container, and consult the compose configuration or container startup command to confirm the variable names for your deployment.

---

## Requirements

- Docker
- A host capable of running a single-container game server
- A web browser on the host and on connecting devices
- LAN access for local multiplayer sessions
- Available storage for game assets and custom `.bsp` maps

---

## Frequently Asked Questions

**How do players connect to a game?**  
Share the browser link, then have players open it from devices connected to the same network.

**Is map switching supported?**  
Yes. Maps can be selected in the browser interface, including custom `.bsp` maps.

**How can I configure the server?**  
Set the appropriate container environment variables before launching the service or restarting it.

**What should I check if startup fails?**  
Begin by reviewing the Docker logs. Then confirm that the necessary ports, files, and map assets are present.

**How do I apply updates?**  
Pull the newest repository changes, rebuild the container, and restart the service.

---

## License

GNU GPL v3.0 - see [LICENSE](LICENSE) for details.
