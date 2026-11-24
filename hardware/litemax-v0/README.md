# LiteMax v0 (KiCad)

Modchip-only board, same circuit as a stock Picofly, as our own flex.

KiCad project files land here once the schematic is drawn. Planned parts:

| Ref | Part | Note |
| --- | --- | --- |
| U1 | RP2040 (QFN-56) | Controller |
| U2 | W25Q16/W25Q32 QSPI flash | Firmware |
| Y1 | 12 MHz crystal + load caps | RP2040 clock |
| Q1 | low-Rds(on) N-MOSFET | Glitch switch (×2: SP1, SP2) |
| — | 0402 decoupling, series R on eMMC | ~20 |
| J1–J4 | FPC connectors | eMMC, 3V3, CPU tails |
| TP | SWD + UART pads, status LED | Bring-up |

Confirm the circuit against the open Picofly design before routing.
