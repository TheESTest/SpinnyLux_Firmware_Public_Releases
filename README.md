# SpinnyLux firmware releases

Firmware for the control board of the SpinnyLux motorized lens filter
(Cinelux). This repository holds binaries only; the SpinnyLux app looks here
for updates.

## What a release contains

Each release under **Releases** has two files:

| File | What it is |
|---|---|
| `spinnylux-control-<version>.bin` | The control board's application image (ESP32-S3). |
| `manifest.json` | The version, compatible boards, size and SHA-256 of that image. |

The newest release's manifest is always at
<https://github.com/TheESTest/SpinnyLux_Firmware_Public_Releases/releases/latest/download/manifest.json>.

## manifest.json

```json
{
  "schema": 1,
  "product": "SpinnyLux",
  "target": "control",
  "version": "1.1.0",
  "date": "2026-10-28",
  "boards": ["A", "B"],
  "protocol": 1,
  "file": "spinnylux-control-1.1.0.bin",
  "url": "https://github.com/TheESTest/SpinnyLux_Firmware_Public_Releases/releases/download/v1.1.0/spinnylux-control-1.1.0.bin",
  "size": 599600,
  "sha256": "fa166b7a45a2755227972dd9d8bc5b457d59f738a1259f718a0639af24faea45",
  "notes": "Supports control board rev B: ..."
}
```

| Field | Meaning |
|---|---|
| `schema` | Manifest format version, 1. |
| `target` | Which board the image is for: `control`. |
| `version` | Firmware version, as the unit reports it (INFO `fw`). |
| `boards` | Control board revisions it runs on. |
| `protocol` | Bluetooth protocol version it speaks (INFO `proto`). |
| `file`, `url`, `size`, `sha256` | The image to download, and how to check it before installing. |
| `notes` | One line for the update prompt. |
