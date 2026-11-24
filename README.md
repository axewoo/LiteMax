# LiteMax

A custom "mega daughterboard" for the Nintendo Switch Lite (HDH-001): an integrated
modchip, reinforced CPU/GPU power delivery, rail and thermal telemetry, and fan control,
on one replaceable-tail flex. Part of an all-out Switch Lite build (8 GB RAM, 256 GB eMMC,
SUPER5 OLED screen, bigger battery, hall sticks, custom cooling).

This repo holds the board (KiCad) and firmware. The full build plan lives in the project
doc; `docs/` here holds the engineering notes.

## Status

Early design. No board has been fabricated yet. The base console (a Lite with a SUPER5
OLED screen and a Picofly already fitted) is on its way; physical layout waits for it.

## Versions

- **v0** — modchip only, same circuit as a stock Picofly, redrawn as our own flex. Proves
  the outline fits and boots as reliably as the stock chip.
- **v1** — adds CPU/GPU rail reinforcement (empty-able pads), rail-voltage and temperature
  sensing, and a fan header, on the same outline as v0.

## Layout

- `hardware/litemax-v0/` — KiCad project for the v0 board.
- `firmware/` — RP2040 firmware (glitch at boot, then fan + telemetry).
- `docs/` — tap-point map, design constraints, bring-up notes.

## Safety and legal

- The glitch firmware derives from the Picofly project, which Nintendo has targeted with
  DMCA takedowns. See `firmware/README.md` before adding any firmware here.
- This console is for offline / emuMMC use. The changed RAM and eMMC sizes show in
  telemetry.
