# KizamuBeam Virtual Machine

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="docs/brand/kizamubeam-logo-dark.png">
    <img src="docs/brand/kizamubeam-logo.png" alt="KizamuBeam" width="520">
  </picture>
</p>

<p align="center">
  <b>Virtuelle Lasermaschine (GRBL 1.1 / FluidNC 3.7 / Ruida DSP) zum Testen von Laser-Jobs ohne Hardware.</b>
</p>

<p align="center">
  <a href="https://github.com/KizamuBeam/kizamubeam-vm/releases"><b>Herunterladen</b></a> ·
  <a href="https://github.com/KizamuBeam/kizamubeam">KizamuBeam</a> ·
  <a href="https://kizamubeam.github.io/kizamubeam/#vm">Website</a> ·
  <a href="https://kizamubeam.github.io/kizamubeam/docs/de/">Handbuch</a> ·
  <a href="https://discord.gg/SSr8VHh7EJ">Discord</a> ·
  <a href="README.md">English</a>
</p>

KizamuBeam Virtual Machine ist eine eigenständige virtuelle Lasermaschine mit Echtzeit-Bahnplanung, 2D- und 3D-Vorschau, Material-Abbrand, Teile-Erkennung und virtueller HTTP/MJPEG-Kamera.

Entwickelt als Ergänzung zu [KizamuBeam](https://github.com/KizamuBeam/kizamubeam), lässt sie sich ebenso mit LightBurn, RDWorks, MeerK40t oder Rayforge verbinden.

## Funktionen

- **GRBL 1.1 & FluidNC 3.7** über Telnet (Standardport `2323`) und WebSocket (`8181`)
- **Ruida DSP (RDC6442S)** über UDP (Datenport `50200`, Tastenport `50207`, inkl. Dateispeicher auf dem Controller)
- **Echtzeit-Bahnplaner** mit Beschleunigung, Kurvengeschwindigkeit (`Junction Deviation`), Empfangspuffer, Statusberichten (`MPos`/`WPos`, `WCO`, `Ov`, `Bf`, `A`), Homing, Joggen, Soft-/Hard-Limits und Laser-Modus (`$32`, `M3`/`M4`)
- **2D- und 3D-Arbeitsfläche** mit 21 Materialvorlagen, Echtzeit-Brennspuren, Schnittdurchbruch und Entnahme ausgeschnittener Teile
- **Virtuelle Kamera** (MJPEG-Stream und Einzelbild über HTTP, am Laserkopf oder fest über dem Bett, mit einstellbarer Linsenverzeichnung)
- **Headless-Modus** ohne Fenster: `kizamubeam-vm --headless` (`--help` zeigt alle Optionen)

## Entwicklung & Tests

```bash
npm install
npm run build        # TypeScript-Prüfung und Frontend-Build
npm test             # Brandkarten-, Teile- und Rust-Steuerungstests
npm run dev          # Tauri-App im Entwicklungsmodus starten
npm run tauri:build  # Installationspakete bauen
npm run headless     # Steuerung ohne Fenster starten
```

## Lizenz

GPL-3.0-or-later — siehe [LICENSE](LICENSE).
