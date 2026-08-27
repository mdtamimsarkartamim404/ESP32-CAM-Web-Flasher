# 📷 ESP32-CAM Web Flasher

<p align="center">

  <img src="https://img.shields.io/badge/ESP32--CAM-Web%20Flasher-blue?style=for-the-badge&logo=espressif" alt="ESP32-CAM Web Flasher">

  <img src="https://img.shields.io/badge/Browser-Flashing-success?style=for-the-badge&logo=googlechrome" alt="Browser Flashing">

  <img src="https://img.shields.io/badge/Web%20Serial-Required-orange?style=for-the-badge" alt="Web Serial">

</p>

<p align="center">

<b>🚀 Flash your AI Thinker ESP32-CAM directly from your web browser.</b>

</p>

<p align="center">

  <a href="https://mdtamimsarkartamim404.github.io/ESP32-CAM-Web-Flasher/">
    <img src="https://img.shields.io/badge/🌐%20LIVE%20DEMO-Open%20Flasher-00C853?style=for-the-badge" alt="Live Demo">
  </a>

  <a href="https://github.com/mdtamimsarkartamim404/ESP32-CAM-Web-Flasher">
    <img src="https://img.shields.io/badge/GitHub-Repository-181717?style=for-the-badge&logo=github" alt="GitHub">
  </a>

</p>

---

## ✨ Overview

**ESP32-CAM-Web-Flasher** is a lightweight browser-based firmware flashing interface designed for the **AI Thinker ESP32-CAM**.

Instead of installing Arduino IDE or using a command-line flashing tool every time, this project provides a simple web interface where you can connect your ESP32-CAM through USB-TTL and flash the prepared firmware directly from a supported browser.

The project uses **ESP Web Tools** to communicate with the ESP32 through the browser.

### 🎯 Main Goal

> Make ESP32-CAM firmware installation as simple as
> **Connect → Install → Select Port → Flash → Run**

---

## 🚀 Features

| Feature                            | Status |
| ---------------------------------- | ------ |
| 🌐 Browser-based flashing          | ✅      |
| 🔌 USB-TTL support                 | ✅      |
| 📷 AI Thinker ESP32-CAM            | ✅      |
| 📸 OV2640 camera                   | ✅      |
| ⚡ ESP32 target                     | ✅      |
| 🧹 Automatic flash erase           | ✅      |
| 📦 Pre-built firmware              | ✅      |
| 🖥️ Web-based interface            | ✅      |
| 📱 Responsive layout               | ✅      |
| 🔒 No server required for flashing | ✅      |
| 🛠️ GitHub Pages compatible        | ✅      |
| 🌍 Internet-accessible web flasher | ✅      |

---

# 🎨 Interface

The web interface is intentionally simple so that beginners can understand the flashing process without dealing with complicated tools.

### Main interface

```text
┌──────────────────────────────────────────────┐
│                                              │
│                     📷                       │
│                                              │
│            ESP32-CAM Web Flasher             │
│                                              │
│     Flash your AI Thinker ESP32-CAM          │
│             from your browser                │
│                                              │
│  ┌────────────────────────────────────────┐  │
│  │       AI Thinker ESP32-CAM             │  │
│  │                                        │  │
│  │  📷 Camera: OV2640                     │  │
│  │  📐 Resolution: 240 × 240              │  │
│  │  ⚡ Chip: ESP32                        │  │
│  └────────────────────────────────────────┘  │
│                                              │
│             [ Install Firmware ]             │
│                                              │
│  ──────────────────────────────────────────  │
│                                              │
│                 How to Flash                 │
│                                              │
│  1. Connect USB-TTL                          │
│  2. GPIO 0 → GND                             │
│  3. Click Install                            │
│  4. Select COM Port                          │
│  5. Flash Firmware                           │
│  6. Remove GPIO 0 → GND and Reset            │
│                                              │
└──────────────────────────────────────────────┘
```

The current interface uses the `esp-web-install-button` component from **ESP Web Tools 10.1.0** and loads the flashing configuration from `manifest.json`.

---

# 🧩 How It Works

```text
             🌐 Web Browser
                   │
                   │ Web Serial
                   ▼
          ┌─────────────────┐
          │ ESP Web Tools   │
          └────────┬────────┘
                   │
                   │ USB
                   ▼
             🔌 USB-TTL
                   │
                   │ Serial
                   ▼
          📷 AI Thinker
           ESP32-CAM
                   │
                   ▼
          ⚡ ESP32 Bootloader
                   │
                   ▼
          📦 Firmware Flash
                   │
                   ▼
             🚀 ESP32-CAM
```

The browser communicates with the ESP32 through the serial interface. The ESP32 must be placed into programming mode before flashing.

---

# 🔧 Hardware Required

You need:

* 📷 AI Thinker ESP32-CAM
* 🔌 USB-to-TTL / FTDI adapter
* 🔗 Jumper wires
* 💻 Windows / Linux / macOS computer
* 🌐 Supported browser

### USB-TTL Connections

| USB-TTL | ESP32-CAM |
| ------- | --------- |
| 5V      | 5V        |
| GND     | GND       |
| TX      | U0R / RX  |
| RX      | U0T / TX  |

### Programming Mode

Connect:

```text
GPIO 0 ───── GND
```

Then reset/power the ESP32-CAM.

After flashing:

```text
GPIO 0 ───── ✕
```

Remove the GPIO 0 → GND connection and reset the board.

---

# 🌐 Browser Requirements

The flasher requires browser serial communication.

### Recommended

* ✅ Google Chrome
* ✅ Microsoft Edge

### Web Serial

The browser must support the **Web Serial API**.

The project itself also displays a warning recommending Chrome or Edge because Web Serial is required.

---

# ⚡ Quick Start

## 1️⃣ Open the Web Flasher

Open the live website:

**ESP32-CAM Web Flasher**

```text
https://mdtamimsarkartamim404.github.io/ESP32-CAM-Web-Flasher/
```

---

## 2️⃣ Connect ESP32-CAM

Connect your USB-TTL adapter:

```text
USB-TTL
   │
   ├── 5V  ──→ ESP32-CAM 5V
   ├── GND ──→ GND
   ├── TX  ──→ RX
   └── RX  ──→ TX
```

---

## 3️⃣ Enter Programming Mode

Connect:

```text
GPIO 0 → GND
```

Then press RESET or reconnect power.

---

## 4️⃣ Click Install

Click:

```text
Install
```

The browser will open the serial-port selection dialog.

---

## 5️⃣ Select COM Port

Select your ESP32-CAM USB-TTL COM port.

Example:

```text
COM3
COM5
COM7
COM12
```

Click:

```text
Connect
```

---

## 6️⃣ Flash Firmware

The browser will erase and write the configured firmware.

Wait until the process finishes.

Do **not** disconnect the board while flashing.

---

## 7️⃣ Exit Programming Mode

After flashing:

```text
GPIO 0 → GND
```

connectionটি remove করুন.

Then press:

```text
RESET
```

The ESP32-CAM should boot normally.

---

# 📦 Firmware Configuration

The project uses a `manifest.json` file to tell ESP Web Tools which firmware to flash.

Current configuration targets:

```text
Chip Family:
ESP32
```

Firmware:

```text
firmware/esp32cam-full.bin
```

Flash offset:

```text
0
```

The manifest also enables:

```json
"new_install_prompt_erase": true
```

which requests an erase before a new installation.

---

# 📁 Project Structure

```text
ESP32-CAM-Web-Flasher/
│
├── ESP32-CAM-Web-Flasher/
│   │
│   ├── index.html
│   ├── manifest.json
│   │
│   └── firmware/
│       ├── boot_app0.bin
│       ├── build.options.json
│       ├── flash_args
│       ├── partitions.csv
│       ├── sdkconfig
│       ├── sketch_aug26a.ino.bin
│       ├── sketch_aug26a.ino.bootloader.bin
│       ├── sketch_aug26a.ino.elf
│       ├── sketch_aug26a.ino.map
│       ├── sketch_aug26a.ino.merged.bin
│       └── sketch_aug26a.ino.partitions.bin
│
└── README.md
```

The current repository contains the web interface and a firmware directory with the generated ESP32 build artifacts.

---

# 🧠 Important Files

## `index.html`

The main web interface.

It contains:

* ESP32-CAM information
* Install button
* Flashing instructions
* Browser warning
* Responsive styling
* ESP Web Tools integration

The current page identifies the board as **AI Thinker ESP32-CAM**, with **OV2640**, **240×240**, and **ESP32**.

---

## `manifest.json`

Controls which firmware ESP Web Tools installs.

Example structure:

```json
{
  "name": "ESP32-CAM Control Panel",
  "version": "1.0.0",
  "new_install_prompt_erase": true,
  "builds": [
    {
      "chipFamily": "ESP32",
      "parts": [
        {
          "path": "./firmware/esp32cam-full.bin",
          "offset": 0
        }
      ]
    }
  ]
}
```

---

# 🛠️ Custom Firmware

You can replace the firmware with your own compiled ESP32-CAM firmware.

For example:

```text
firmware/
└── esp32cam-full.bin
```

Then update:

```json
"path": "./firmware/esp32cam-full.bin"
```

Make sure the firmware file is actually available at that path.

---

# 🌍 GitHub Pages Deployment

This project is suitable for static hosting because the web interface consists of HTML/CSS/JavaScript and firmware assets.

## Step 1 — Repository

Create or use:

```text
ESP32-CAM-Web-Flasher
```

## Step 2 — Upload files

Keep the structure:

```text
ESP32-CAM-Web-Flasher/
└── ESP32-CAM-Web-Flasher/
    ├── index.html
    ├── manifest.json
    └── firmware/
        └── firmware.bin
```

## Step 3 — Enable GitHub Pages

Go to:

```text
Repository
→ Settings
→ Pages
```

Select:

```text
Deploy from a branch
```

Choose:

```text
main
/
```

Then save.

---

# ⚠️ Important GitHub Pages Path

If your GitHub Pages URL is:

```text
https://USERNAME.github.io/ESP32-CAM-Web-Flasher/
```

then make sure your `manifest.json` path is accessible relative to the HTML page.

For example:

```text
index.html
manifest.json
firmware/
└── esp32cam-full.bin
```

The manifest should use:

```json
"path": "./firmware/esp32cam-full.bin"
```

Relative paths are recommended for GitHub Pages deployments because they prevent the browser from trying to access local `file://` paths.

---

# 🔐 Security & Privacy

This project does not require a traditional backend server to perform the flashing operation.

The firmware is downloaded by the browser from the configured repository path and written to the connected ESP32 through the browser's supported serial interface.

### Important

Only flash firmware that you trust.

Firmware has full control over the ESP32 hardware once installed.

---

# 🧯 Troubleshooting

## ❌ Install button does not work

Try:

* Google Chrome
* Microsoft Edge
* HTTPS website
* USB-TTL connected correctly
* Correct COM port
* GPIO 0 connected to GND

---

## ❌ COM port is not visible

Check:

```text
Device Manager
→ Ports (COM & LPT)
```

Install the appropriate USB-TTL driver if necessary.

Common USB-to-serial chips include:

```text
CH340
CP210x
FT232
```

---

## ❌ Failed to connect to ESP32

Make sure:

```text
GPIO 0 → GND
```

Then:

```text
Press RESET
```

Try flashing again.

---

## ❌ Flash starts but fails

Check:

1. USB cable
2. USB-TTL power
3. TX/RX wiring
4. GPIO 0 connection
5. Stable 5V supply
6. Correct firmware
7. Correct COM port

Avoid disconnecting the board during flashing.

---

## ❌ ESP32-CAM does not boot after flashing

Remove:

```text
GPIO 0 → GND
```

Then press:

```text
RESET
```

The board needs GPIO 0 released from GND to boot normally.

---

# 📸 Supported Board

Current project configuration is designed around:

```text
Board:
AI Thinker ESP32-CAM

MCU:
ESP32

Camera:
OV2640

Configured Resolution:
240 × 240
```

These values are also shown directly in the current web interface.

---

# 🔄 Flashing Workflow

```text
          START
            │
            ▼
     Connect ESP32-CAM
            │
            ▼
       Connect USB-TTL
            │
            ▼
      GPIO 0 → GND
            │
            ▼
       Reset ESP32-CAM
            │
            ▼
     Open Web Flasher
            │
            ▼
       Click Install
            │
            ▼
      Select COM Port
            │
            ▼
      Erase & Flash
            │
            ▼
       Flash Complete
            │
            ▼
      Remove GPIO 0
            │
            ▼
          Reset
            │
            ▼
       🚀 ESP32-CAM
          Running
```

---

# 💡 Why Web Flasher?

Traditional method:

```text
Arduino IDE
     ↓
Install board package
     ↓
Install libraries
     ↓
Open source code
     ↓
Compile
     ↓
Select COM port
     ↓
Upload
```

Web Flasher:

```text
Open Website
     ↓
Connect Board
     ↓
Install
     ↓
Select COM Port
     ↓
Flash
```

### Result

**Much easier for end users.**

---

# 🧑‍💻 For Developers

The project can be customized easily.

You can modify:

```text
index.html
```

to change:

* 🎨 UI design
* ✨ Animations
* 📷 Board information
* 📖 Instructions
* 🔘 Buttons
* 🌙 Dark mode
* 📱 Mobile layout

You can modify:

```text
manifest.json
```

to change:

* Firmware name
* Firmware path
* Chip family
* Flash configuration
* Version
* Erase behavior

---

# 🎨 Suggested Future UI

Possible future improvements:

```text
✨ Animated ESP32-CAM illustration
🌌 Animated background
💫 Glowing buttons
📊 Flash progress visualization
🔌 Connection status
🟢 Device connected indicator
⚡ Flash speed
📈 Flash percentage
✅ Success animation
❌ Error animation
🔄 Reconnect button
📱 Better mobile UI
🌙 Light/Dark mode
```

---

# 🧪 Development Checklist

Before publishing a firmware update:

* [ ] Test firmware manually
* [ ] Verify ESP32-CAM boots
* [ ] Verify camera initializes
* [ ] Verify Wi-Fi
* [ ] Verify web server
* [ ] Verify stream
* [ ] Verify firmware `.bin`
* [ ] Verify manifest path
* [ ] Test Chrome
* [ ] Test Edge
* [ ] Test GitHub Pages
* [ ] Test fresh ESP32-CAM
* [ ] Test erase + flash
* [ ] Test reboot after flashing

---

# 📜 License

This project is provided for educational and development purposes.

If you add third-party libraries, firmware, or components, make sure you follow their respective licenses and attribution requirements.

The web flashing mechanism is based on the ESP Web Tools ecosystem.

---

# ⭐ Support the Project

If this project helps you:

### ⭐ Star the repository

```text
https://github.com/mdtamimsarkartamim404/ESP32-CAM-Web-Flasher
```

### 🍴 Fork it

Create your own version and improve the interface.

### 🐛 Report Issues

If you find a bug, open a GitHub Issue with:

```text
Browser:
Operating System:
ESP32-CAM Model:
USB-TTL Model:
COM Port:
Error Message:
Steps to Reproduce:
```

---

# 🤝 Contributing

Contributions are welcome.

Possible contribution areas:

* UI improvements
* Better animations
* Mobile optimization
* Firmware management
* Multiple firmware profiles
* Better error handling
* Documentation
* ESP32 board support

### Contribution Workflow

```bash
git clone https://github.com/mdtamimsarkartamim404/ESP32-CAM-Web-Flasher.git

cd ESP32-CAM-Web-Flasher

git checkout -b feature/my-improvement
```

Make your changes, test them, then create a Pull Request.

---

# 📊 Project Architecture

```text
                    ┌──────────────────────┐
                    │      GitHub Pages    │
                    │                      │
                    │      index.html      │
                    │          │           │
                    │          ▼           │
                    │    manifest.json     │
                    │          │           │
                    │          ▼           │
                    │      firmware/       │
                    │       *.bin          │
                    └──────────┬───────────┘
                               │
                               │ HTTPS
                               ▼
                    ┌──────────────────────┐
                    │    Web Browser       │
                    │                      │
                    │ Chrome / Edge        │
                    │ Web Serial API       │
                    └──────────┬───────────┘
                               │
                               │ USB Serial
                               ▼
                    ┌──────────────────────┐
                    │       USB-TTL        │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │    AI Thinker       │
                    │     ESP32-CAM       │
                    │                      │
                    │     ESP32 + OV2640  │
                    └──────────────────────┘
```

---

# 📌 Current Repository

**Repository:**
`mdtamimsarkartamim404/ESP32-CAM-Web-Flasher`

**Platform:** GitHub

**Target:** AI Thinker ESP32-CAM

**MCU:** ESP32

**Camera:** OV2640

**Flashing:** Browser-based

**Communication:** Web Serial

**Firmware:** Pre-built `.bin`

**Hosting:** GitHub Pages compatible

---

# 🚀 Project Status

```text
╔══════════════════════════════════════╗
║      ESP32-CAM WEB FLASHER           ║
╠══════════════════════════════════════╣
║                                      ║
║  🌐 Web Interface       ✅            ║
║  🔌 Browser Flashing    ✅            ║
║  📷 ESP32-CAM           ✅            ║
║  ⚡ ESP32 Firmware      ✅            ║
║  📦 Firmware Manifest   ✅            ║
║  📱 Responsive UI       ✅            ║
║                                      ║
║       🚀 READY TO FLASH              ║
║                                      ║
╚══════════════════════════════════════╝
```

---

## ❤️ Made for ESP32-CAM

Built with:

**HTML • CSS • JavaScript • ESP Web Tools • ESP32**

<p align="center">

### 📷 Connect. Flash. Build. 🚀

**ESP32-CAM-Web-Flasher**

</p>

---

<p align="center">

<b>Developed by Md. Tamim Sarkar Tamim</b>

</p>

<p align="center">

<a href="https://github.com/mdtamimsarkartamim404">
GitHub Profile
</a>

</p>
