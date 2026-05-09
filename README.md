# OHMNI — PCB Design Copilot

A design-forward concept UI for PCB analysis. Paste a bill of
materials, get DRC/ERC heuristics, IPC-7351 footprint suggestions,
and an interactive photolithography sandbox.

**🔗 Live demo:** https://kdspacex75.github.io/ohmni/

![hero](screenshots/hero.png)

## What it does

- **BOM parser** — reads R/C/L/U/Q/D refdes, package codes
  (0402, QFN, BGA…), and part-number families (ESP32, STM32,
  NEO-M9N, Lattice ECP, ICM-20948), classifies into typed components.
- **Rule engine** — ~10 design-rule heuristics: decoupling cap
  ratio, I²C pull-ups, MCU reset network, GNSS LNA chain, patch
  antenna keepouts, BGA escape stackup, FPGA multi-decade decoupling,
  crystal load caps, ESD protection, mixed-passive consistency.
- **Footprint suggestions** — SVG package thumbnails for 0402–1206
  passives, QFN, BGA, SOT-23, patch antenna, crystal can.
- **Photolithography lab** — interactive sandbox with 5 exposure
  sources (i-line, KrF, ArF, EUV, e-beam). Live readouts for
  wavelength, min feature size, depth of focus, dose, throughput.
  Wafer yield visualization and process-node compatibility (180nm → 3nm).
- **Health gauge** — 0-100 score with verdict line ("READY FOR FAB"
  → "DO NOT FABRICATE") based on issue severity weights.

## Try the example flow

1. Click "GNSS rover with patch antenna" under TRY
2. Hit ANALYZE
3. Scroll the photolithography lab → toggle Experimental Mode

## Stack

Vanilla HTML / CSS / JS · single file · zero runtime dependencies.
Custom SVG illustrations for every visual element. Fonts via Google
Fonts (Anton, JetBrains Mono, DM Sans, Fraunces).

## Honest scope

This is a **frontend prototype** built solo as a UX exploration
of how AI-era PCB design tools could feel. The analysis layer is
heuristic — regex parsing + a hand-written rule set — not a real
EDA verifier. The lithography numbers are physically reasonable
lookup values, not a simulator.

## What I'd build next

- KiCad `.kicad_sch` / `.net` file upload + real netlist parsing
- Microstrip impedance solver (Saturn PCB equations)
- Gerber render preview for uploaded designs
- LLM-backed conversational tutor for the "Learn the Why" panel
- Test suite: deliberately broken schematics + accuracy benchmark

## License

MIT — see [LICENSE](LICENSE).
