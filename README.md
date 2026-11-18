# KizamuBeam Virtual Machine

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="docs/brand/kizamubeam-logo-dark.png">
    <img src="docs/brand/kizamubeam-logo.png" alt="KizamuBeam" width="520">
  </picture>
</p>

<p align="center">
  <b>Virtual laser machine (GRBL 1.1 / FluidNC 3.7 / Ruida DSP) for testing laser jobs without hardware.</b>
</p>

<p align="center">
  <a href="https://github.com/KizamuBeam/kizamubeam-vm/releases"><b>Download</b></a> ·
  <a href="https://github.com/KizamuBeam/kizamubeam">KizamuBeam</a> ·
  <a href="https://kizamubeam.github.io/kizamubeam/en/#vm">Website</a> ·
  <a href="https://kizamubeam.github.io/kizamubeam/docs/">Manual</a> ·
  <a href="https://discord.gg/SSr8VHh7EJ">Discord</a> ·
  <a href="README.de.md">Deutsch</a>
</p>

KizamuBeam Virtual Machine is a standalone desktop and headless laser machine emulator with real-time motion planning, 2D and 3D views, real-time material burning, cut-out part detection, and a virtual HTTP/MJPEG camera.

Designed as the companion emulator for [KizamuBeam](https://github.com/KizamuBeam/kizamubeam), it also works with LightBurn, RDWorks, MeerK40t, and Rayforge.

## Features

- **GRBL 1.1 & FluidNC 3.7** over Telnet (default port `2323`) and WebSocket (`8181`)
- **Ruida DSP (RDC6442S)** over UDP (data port `50200`, keypad port `50207`, including controller file storage)
- **Real-time motion planner** with acceleration, cornering speed (`Junction Deviation`), receive buffer, status reports (`MPos`/`WPos`, `WCO`, `Ov`, `Bf`, `A`), homing, jogging, soft/hard limits, and laser mode (`$32`, `M3`/`M4`)
- **2D and 3D workspace** with 21 material looks, real-time burn marks, cut-through simulation, and interactive part removal and inspection
- **Virtual camera** (MJPEG stream and single snapshot over HTTP, mounted on the laser head or fixed above the bed, with configurable barrel distortion)
- **Headless mode** without a window: `kizamubeam-vm --headless` (`--help` lists all options)

## Development & Tests

```bash
npm install
npm run build        # TypeScript check and frontend build
npm test             # Burn map, cut-out detection, and Rust controller tests
npm run dev          # Start the Tauri desktop app in development mode
npm run tauri:build  # Build installer packages
npm run headless     # Run the controller without a GUI window
```

## License

GPL-3.0-or-later — see [LICENSE](LICENSE).
