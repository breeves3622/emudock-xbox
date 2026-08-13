# EmuDock Xbox Stack: Dockerized Emulator Host with ES-DE Frontend & Wolf / Sunshine

A complete, self-hosted Docker gaming stack hosted on GitHub and deployed via **Portainer**. Built for playing modern emulated games (PS2, PS3, GameCube, Wii, Switch, N64, SNES, Arcade) on an **Xbox One / Xbox Series X|S** console with **EmulationStation Desktop Edition (ES-DE)** as a 10-foot TV frontend, reading ROMs from your network drive (`\\10.80.1.50\Public\Emulator\Roms`).

---

## ⚠️ Headless Server Note: Why Wolf is Recommended

If your Portainer host server is a **headless Linux machine** (no physical monitor plugged in or no active desktop GUI session running on the host OS), Sunshine will throw:
> `Fatal: Unable to find display or encoder during startup. Please check that a display is connected and powered on.`

**Wolf (Games on Whales)** solves this natively! Wolf spins up its own internal Wayland headless display compositor inside Docker, automatically detecting your AMD (`amdgpu`) or NVIDIA GPU without needing any physical display or host desktop environment.

---

## 🚀 Portainer Deployment Guide

### Recommended for Headless Servers: Wolf Stack
1. Open **Portainer** > **Stacks** > **+ Add stack**.
2. Select **Repository** method.
3. Repository URL: `https://github.com/breeves3622/emudock-xbox.git`
4. Set **Compose path**: `docker-compose.wolf.yml`
5. Click **Deploy the stack**.

---

## 📁 Repository Files

- `docker-compose.wolf.yml`: **Wolf (Games on Whales)** Headless Docker-native streaming stack.
- `docker-compose.smb.yml`: **Sunshine** stack for servers with active desktop environment & Guest SMB share.
- `docker-compose.nfs.yml`: **Sunshine** stack for servers with active desktop environment & NFS share.
- `docker-compose.romm.yml`: **RomM + EmulatorJS** Web-browser emulation stack.
- `.env.example`: Environment variables template.
- `xbox-moonlight-guide.md`: Detailed Xbox setup guide.
