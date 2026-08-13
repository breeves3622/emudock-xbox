# Xbox Setup Guide: Moonlight + Wolf / Sunshine with ES-DE Frontend

This guide explains how to connect your **Xbox One / Xbox Series X|S** console to your Dockerized Wolf / Sunshine stack for streaming modern emulated games in 1080p/4K @ 60FPS.

---

## 🐺 Pairing Xbox Moonlight with Wolf (Games on Whales)

Wolf features two web portals:
1. **Wolf Den Dashboard** (`http://<YOUR_SERVER_IP>:8085`): Web UI for managing games, profiles, and streaming settings.
2. **Pairing Portal** (`http://<YOUR_SERVER_IP>:47989`): Instant browser portal for entering your Xbox PIN.

### How to Pair Xbox with Wolf:
1. Launch **Moonlight** on your Xbox console.
2. Select your Wolf server. Moonlight will display a 4-digit **PIN** on your TV screen.
3. In Portainer, check the **Wolf container logs** (or open `http://<YOUR_SERVER_IP>:47989/pin/#...` generated in the log).
4. Enter the PIN shown on your Xbox into the browser page.
5. Pairing completes immediately!

---

## ☀️ Pairing Xbox Moonlight with Sunshine (Optional)

1. Launch **Moonlight** on your Xbox.
2. Note the PIN on your Xbox screen.
3. Open Sunshine Web UI at `https://<YOUR_SERVER_IP>:47990`.
4. Go to the **PIN** tab, enter the PIN, and submit.

---

## Xbox Gamepad Controls & Navigation

| Action | Xbox Controller Button |
| :--- | :--- |
| **Navigate UI** | D-Pad / Left Thumbstick |
| **Select / Launch Game** | **A** Button |
| **Back / Cancel** | **B** Button |
| **View Options / Filters** | **X** Button |
| **Scrape Metadata / Settings** | **Select (View)** Button |
| **Exit Game Back to Menu** | Press **View + Menu** (or `Select + Start`) simultaneously for 2 seconds |
| **Toggle Moonlight Menu** | **LB + RB + Select + Start** |
