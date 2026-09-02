# 🍉 AirMouse — Fruit Ninja (Gyro Sword Edition)

A browser-based Fruit Ninja experience where you wield your **smartphone like a real katana sword** using its built-in **Gyroscope & Accelerometer** over local WiFi. 

Point, tilt, and swing your phone through the air to slice juicy fruits in real-time on your PC screen!

---

## ⚡ Quick Start

```bash
# 1. Install dependencies
npm install

# 2. Launch the server
node server.js
```

The terminal will display:
```
🍉  AirMouse — Fruit Ninja
────────────────────────────────
  Game   → http://localhost:3000
  Phone  → http://<your-ip>:3000/controller
────────────────────────────────
```

---

## 🗡️ How to Play with Phone Gyro

1. **Open the Game on PC**: Visit `http://localhost:3000` in your PC browser.
2. **Scan the QR Code**: Scan the QR code shown on your PC screen with your phone camera (or open `http://<pc-ip>:3000/controller` on your mobile browser).
3. **Activate Motion Controls**:
   - On **iOS (Safari)**: Tap the **"Activate Gyroscope"** button when prompted to grant motion sensor permissions.
   - On **Android (Chrome)**: Motion sensors activate automatically.
4. **Hold & Aim**:
   - Hold your phone naturally facing your PC screen.
   - Tilt your phone left/right/up/down to aim the **laser crosshair** at fruits.
   - Tap **"🎯 Re-Center Aim"** anytime to reset the neutral center point to your current holding angle.
5. **Draw Blade & Slice**:
   - **Hold to Slice (Default)**: Hold your thumb down on the phone screen to ignite the Katana energy blade and slash fruits! Release to aim without cutting bombs.
   - **Always On**: Keeps the blade continuously drawn for nonstop slicing.
   - **Swing Velocity**: Physically swing your phone like a sword — high-speed motion automatically triggers slicing slashes!
6. **Start / Restart**: Tap **"▶️ Start / Play"** directly on your phone controller to launch or restart the game.

---

## 🖱️ PC Direct Play (Fallback)

You can also play directly on PC using your mouse or trackpad:
- Click and drag across fruits to slice them.
- Avoid slicing black bombs!

---

## 🌐 Finding Your PC's Local IP Manually

If you need to enter the URL manually on your phone:

| Operating System | Command | Notes |
|---|---|---|
| **macOS** | `ipconfig getifaddr en0` | Usually `192.168.x.x` or `172.20.x.x` |
| **Windows** | `ipconfig` | Look for "IPv4 Address" under Wi-Fi |
| **Linux** | `hostname -I` | First IP in the list |

> ⚠️ **Important**: Your phone and PC must be connected to the **same Wi-Fi network**.

---

## 🎮 Features

- 📱 **Real-Time Gyroscope Aiming**: 60fps low-latency motion streaming via WebSockets.
- ⚔️ **Katana Energy Blade**: Laser reticle for precision aiming + flaming energy blade when slicing.
- 🎯 **One-Tap Re-Calibration**: Instant zero-offset calibration for any seating or standing angle.
- 🍉 **Juicy Physics & Slicing**: Slices fruits along the exact cut angle, scattering realistic halves, juice splatter, and wall stains.
- 💣 **Bombs & Shockwaves**: Dangerous bombs with burning fuses and screen-clearing explosion effects.
- 🔥 **Combo System**: Slice 3+ fruits in a single swipe for combo fanfare and bonus multipliers.
- 🔊 **Zero-Asset Web Audio Synth**: Custom synthesized slice swooshes, splats, bomb explosions, and combo chords.
- 📱 **Haptic Feedback**: Physical vibrations on your phone during slices, swings, and pairing.
- 🏆 **High Score Tracking**: Automatically saved to your local browser storage.

---

## 📁 Project Structure

```
AirMouse/
├── server.js              # Express + Socket.io relay server
├── public/
│   ├── game.html          # PC game (HTML5 Canvas + Gyro interpolation)
│   └── controller.html    # Mobile Gyroscope sword controller (iOS & Android)
├── package.json
└── README.md
```

---

## 🔧 Troubleshooting

- **No motion on iOS?** Ensure you tapped "Activate Gyroscope" on the controller page and allowed motion permissions.
- **Phone cannot reach the PC?** Verify both devices are connected to the same Wi-Fi and that port `3000` is allowed in your PC's firewall.
- **Aim drifted?** Simply tap the **"🎯 Re-Center Aim"** button on your phone while pointing at the screen center.
