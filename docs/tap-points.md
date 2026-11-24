# Tap points (Switch Lite HDH-001)

Every net here is **provisional** until confirmed against the μSoldering Lite netlist and
measured on the real board. The names come from the stock Picofly install (photos in the
project files, `switch-lite-max/picofly-ref/`), not yet from the netlist.

## From the stock Picofly

| Pad | Picofly role (provisional) | Confirm against netlist | Measured |
| --- | --- | --- | --- |
| 3V3 | Always-on 3.3 V supply for the chip | Which rail / source component | TODO |
| GND | Ground (to SoC shield) | — | TODO |
| A | eMMC line | eMMC CMD or DAT0? | TODO |
| C | eMMC line | eMMC CLK? | TODO |
| D | eMMC line | eMMC data | TODO |
| B | eMMC / reset related | role | TODO |
| SP1 | Glitch switch, CPU rail cap | which cap, which rail node | TODO |
| SP2 | Glitch switch, CPU rail cap | which cap, which rail node | TODO |

## To locate for v1

| Signal | Why | Source | Found? |
| --- | --- | --- | --- |
| MAX77812 CPU rail output node | Rail reinforcement + sense | netlist | TODO |
| MAX77812 GPU rail output node | Rail reinforcement + sense | netlist | TODO |
| Fan connector pinout | Fan header | netlist / board | TODO |
| Existing bulk capacitance on CPU/GPU rails | Size the reinforcement | netlist / measure | TODO |

## Notes

- The glitch parts sit on the CPU flex at the SoC capacitors in the stock install. They
  stay there; rail reinforcement goes on the regulator side so it does not damp the glitch.
- The stock main board sits flat on the SoC shield next to the fan. That is the area the
  daughterboard can occupy, bounded by the fan.
