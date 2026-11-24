# Firmware

The RP2040 runs the boot glitch first, then fan control and telemetry once the console is up.

## Base

The glitch is the Picofly firmware's job. Nintendo DMCA'd the original Picofly repositories
(144 repos removed in one 2024 takedown), so the firmware is **not committed here**. Supply
the glitch core from a copy you already hold, and keep this repo to our own additions:

- Post-boot loop: fan PWM, rail-voltage ADC logging, temperature reads.
- Debug: USB CDC or UART log, status LED.

Keep the glitch timing code untouched so v0 boots exactly like a stock Picofly; our code runs
only after boot.

## Build

RP2040 SDK. Details once the glitch core and pin map are in place.
