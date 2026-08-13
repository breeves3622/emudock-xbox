# Xbox Setup Guide: Moonlight + Sunshine with EmulationStation-DE Frontend

This guide explains how to connect your **Xbox One / Xbox Series X|S** console to your Dockerized Sunshine + EmulationStation-DE stack for streaming modern emulated games in 1080p/4K @ 60FPS.

---

## Option 1: Moonlight App on Xbox (Recommended for Best Performance)

### Step 1: Install Moonlight UWP on Xbox
1. On your Xbox, switch to **Xbox Developer Mode** (or download Moonlight via standard Xbox Store if available in your region/beta).
2. Install the **Moonlight Xbox (UWP)** app.
3. Ensure your Xbox is connected to the same local network (Ethernet recommended).

### Step 2: Pair Xbox Moonlight with Sunshine Server
1. Launch **Moonlight** on your Xbox.
2. It should automatically discover your Sunshine server on your local network. Click on your server name.
3. Moonlight will display a **PIN code** (e.g., `1234`).
4. On your PC or phone, open the Sunshine Web UI at:
   `https://<YOUR_SERVER_IP>:47990`
5. Go to the **PIN** tab, enter the PIN code displayed on your Xbox, and click **Send**.
6. Your Xbox is now securely paired!

### Step 3: Launch EmulationStation-DE (ES-DE)
1. On your Xbox, click on the paired Sunshine server in Moonlight.
2. Select **EmulationStation-DE**.
3. EmulationStation-DE will launch in full screen with box art, video trailers, and gamepad sound effects!

---

## Option 2: Microsoft Edge Browser on Xbox (No Dev Mode Required)

If you prefer not to use Developer Mode, you can stream directly through Microsoft Edge on your Xbox:

1. Open **Microsoft Edge** on your Xbox.
2. Navigate to your Sunshine Moonlight Web URL or WebRTC streaming endpoint:
   `http://<YOUR_SERVER_IP>:47989`
3. Press the **Menu Button (▤)** on your Xbox controller and select **Use Game Controller**.
4. Click **EmulationStation-DE** to launch full screen streaming.

---

## Xbox Gamepad Controls & Navigation

| Action | Xbox Controller Button |
| :--- | :--- |
| **Navigate UI** | D-Pad / Left Thumbstick |
| **Select / Launch Game** | **A** Button |
| **Back / Cancel** | **B** Button |
| **View Options / Filters** | **X** Button |
| **Scrape Metadata / Settings** | **Select (View)** Button |
| **Exit Game Back to ES-DE Menu** | Press **View + Menu** (or `Select + Start`) simultaneously for 2 seconds |
| **Toggle Moonlight Menu** | **LB + RB + Select + Start** |

---

## Performance & Display Optimization Tips

1. **Resolution & Refresh Rate**:
   - In Moonlight Xbox settings, set resolution to **1920x1080 @ 60 FPS** (or 4K @ 60 FPS if your host server has a powerful GPU).
2. **Audio Latency**:
   - Set Audio Sync to **Enabled** in Moonlight settings.
3. **Network**:
   - Connect both Xbox and Host Server via **Cat6 Gigabit Ethernet** to eliminate Wi-Fi latency and frame drops.
