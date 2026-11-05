# Resistor Color-Code Volume Control

A single-file, zero-dependency web page that turns the classic resistor color code into a working volume knob.

## What it does

- Pick two digit bands and a multiplier band — the breadboard resistor repaints itself and the readout line shows the real resistance (±5%), the voltage reaching the speaker, and the resulting volume as a percentage.
- **▶ Play my set** — plays a little melody built from your band choices, and the dials stay live: twist any band while it plays and the volume follows in real time.
- An animated rainbow meter keeps score, complete with a careening cat companion and stars.
- The full 12-row color chart highlights whichever bands you currently have selected.
- Follows your system's light / dark theme automatically.

## Try it now

**Live page:** https://hotwings06.github.io/project-paradox/

Or open `index.html` in any modern browser — no build step, no dependencies, no server required.

## Tech notes

- Pure HTML + CSS + vanilla JavaScript in one file (~12 KB).
- Sound is generated locally with the Web Audio API (triangle wave + gain envelope), so the volume percentage you dial is the volume you hear.
- Resistance → loudness mapping: `R = (band 1 × 10 + band 2) × multiplier`, `volume = 10,000 / (10,000 + R)` — small resistors get loud, big ones dial the gain down toward silence, just like the real voltage-divider physics it's modeled on.
