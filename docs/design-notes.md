# Design notes

## Board split

Four parts, mirroring the stock Picofly so the risky nets stay short:

1. **Main board** — RP2040, QSPI flash, 12 MHz crystal, glitch MOSFET driver, debug pads,
   status LED. Sits flat on the SoC shield beside the fan.
2. **eMMC tail** — A, C, D, B to the eMMC area; ground to the shield.
3. **3.3 V tail** — supply tap.
4. **CPU tail** — glitch switches at SP1/SP2, on the SoC rail capacitors.

Tails plug into the main board on small FPC connectors (like Picofly's CPU cable) so a torn
tail is a cheap part, not a scrapped board.

## v0 → v1

Same outline. v1 adds, on pads left empty in v0:

- Low-ESR capacitance on the CPU and GPU rails, **regulator side only**.
- Resistor dividers from each rail into an RP2040 ADC.
- Two NTC thermistors (SoC shield, regulator area) into the ADC.
- A fan header the RP2040 can drive.

## Constraints

- **Glitch vs capacitance.** Extra capacitance near the SoC absorbs the glitch pulse. Keep
  the MOSFET and its loop short at the SoC caps; put reinforcement at the MAX77812 output.
  Make the v1 caps DNP-able to compare success rate with and without.
- **Height.** The flex sits under the RF shield and heatsink. Measure the real gap on the
  console first; thinnest flex the fab offers, no tall parts over the SoC.
- **Thermal.** Cut-out so the main board does not block shield-to-heatsink contact.
- **Wider CPU tail** than the stock thin flex, for a sharper glitch pulse.

## What needs the console in hand

Outline and shield clearance, exact tap positions and tail lengths, fan-connector location.

## What does not

Schematic v0, firmware additions, and reading the exact nets off the μSoldering Lite netlist.
