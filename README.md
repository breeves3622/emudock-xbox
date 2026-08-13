# EmuDock Xbox Stack: Dockerized Emulator Host with ES-DE Frontend & Wolf / Sunshine

A complete, self-hosted Docker gaming stack hosted on GitHub and deployed via **Portainer**. Built for playing modern emulated games (PS2, PS3, GameCube, Wii, Switch, N64, SNES, Arcade) on an **Xbox One / Xbox Series X|S** console with **EmulationStation Desktop Edition (ES-DE)** as a 10-foot TV frontend, reading ROMs from a network drive (SMB/CIFS or NFS).

---

## 🐺 What is Wolf? (Games on Whales)

**Wolf** (developed by the *Games on Whales* open-source project) is a **Docker-native streaming server** designed specifically as a containerized alternative to Sunshine/Moonlight.

### Sunshine vs. Wolf Comparison

| Feature | Sunshine | Wolf (Games on Whales) |
| :--- | :--- | :--- |
| **Primary Architecture** | Captures host OS desktop & passes through X11 display. | **100% Docker-Native**. Spins up isolated Wayland containers on-demand. |
| **Multi-Session Support** | 1 Stream at a time (captures physical display). | 🏆 **Multi-User**: Multiple users can stream separate games simultaneously. |
| **Headless Support** | Requires virtual display configuration. | Built-in headless virtual framebuffer generation. |
| **Portainer Deployment** | Standard container setup. | Deploys via `docker-compose.wolf.yml` accessing Docker socket. |

---

## 📁 Repository Structure

```
.
├── docker-compose.yml          # Primary Sunshine + ES-DE Stack
├── docker-compose.wolf.yml     # Games on Whales Wolf Docker-Native Stack
├── docker-compose.smb.yml      # SMB/CIFS Network Storage Compose Override
├── docker-compose.nfs.yml      # NFS Network Storage Compose Override
├── docker-compose.romm.yml     # Alternative RomM + EmulatorJS Web Stack
├── .env.example                # Portainer Environment Variables Template
├── README.md                   # Main Setup & Deployment Documentation
├── xbox-moonlight-guide.md     # Xbox Moonlight Pairing & Controller Guide
├── config/
│   ├── sunshine/apps.json      # Sunshine profile setting ES-DE as auto-launch
│   └── es-de/es_settings.xml   # Pre-configured ES-DE 10-foot TV settings
└── .gitignore                  # Git secrets & log ignores
```

---

## 🚀 Portainer Deployment Guide

### Step 1: Clone Repository to GitHub
Push this repository to your personal **GitHub** account.

### Step 2: Add Stack in Portainer
1. Open **Portainer** (`http://<YOUR_PORTAINER_IP>:9000`).
2. Navigate to **Stacks** > **+ Add stack**.
3. Select **Repository** method.
4. Enter your GitHub Repository URL.
5. Set **Compose path**:
   - `docker-compose.wolf.yml` (for **Wolf / Games on Whales**)
   - `docker-compose.smb.yml` (for **Sunshine + SMB**)
   - `docker-compose.nfs.yml` (for **Sunshine + NFS**)

### Step 3: Configure Environment Variables in Portainer
Scroll down to **Environment variables** in Portainer and load keys from `.env.example`:

| Environment Variable | Example Value | Description |
| :--- | :--- | :--- |
| `SMB_USER` | `nas_user` | Network share username |
| `SMB_PASS` | `secret123` | Network share password |
| `SMB_ROMS_PATH` | `//192.168.1.50/roms` | UNC Path to your ROM directory |
| `SUNSHINE_USER` | `admin` | Sunshine Web Dashboard username |
| `SUNSHINE_PASS` | `password123` | Sunshine Web Dashboard password |

### Step 4: Deploy Stack
Click **Deploy the stack**. Portainer will launch the container stack and mount your network ROM drive.

---

## 🎮 Connecting your Xbox

See the detailed [Xbox Setup Guide](xbox-moonlight-guide.md) for step-by-step pairing instructions, controller mappings, and 60FPS display optimizations.
