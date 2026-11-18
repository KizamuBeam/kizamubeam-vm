# KizamuBeam Virtual Machine

Virtuelle Lasermaschine (GRBL 1.1 / FluidNC 3.7 / Ruida DSP RDC6442S) zum Testen von Laser-Jobs ohne Hardware, mit Echtzeit-Bahnplanung, 2D/3D-Vorschau, Material-Abbrand, Teile-Erkennung und virtueller HTTP/MJPEG-Kamera.

Ergänzung zu [KizamuBeam](https://github.com/KizamuBeam/kizamubeam), nutzbar auch mit LightBurn, RDWorks, MeerK40t oder Rayforge.

## Funktionen

- **GRBL 1.1 & FluidNC 3.7** über Telnet (Standardport `2323`) und WebSocket (`8181`)
- **Ruida DSP (RDC6442S)** über UDP (Datenport `50200`, Tastenport `50207`)
- **Echtzeit-Bahnplaner** mit Beschleunigung, Kurvengeschwindigkeit (`Junction Deviation`), Empfangspuffer, Statusberichten (`MPos`/`WPos`, `WCO`, `Ov`, `Bf`, `A`), Homing, Joggen, Soft-/Hard-Limits und Laser-Modus (`$32`, `M3`/`M4`)
- **2D- und 3D-Arbeitsfläche** mit Materialvorlagen, Echtzeit-Brennspuren, Schnittdurchbruch und Entnahme ausgeschnittener Teile
- **Virtuelle Kamera** (MJPEG-Stream und Einzelbild über HTTP, am Laserkopf oder fest über dem Bett)
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
