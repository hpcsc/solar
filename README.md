# Solar battery size calculator

An interactive calculator for estimating the solar battery size a home needs, tailored to Australia.

**Live site:** https://solar.pnguyen.au

## What it does

Given a few details about your home, it estimates the battery capacity (kWh, Ah @ 48V) you should buy, using:

```
battery size = (daily load to cover × days of cover) ÷ (depth of discharge × round-trip efficiency)
```

- **Self-consumption mode** — sizes the battery to shift your solar into the evening (night load only).
- **Outage backup mode** — sizes the battery to run the whole home for a chosen number of days with no sun.

## Australia-specific defaults

- Peak sun hours (summer/winter) for the 8 capital cities
- 48V battery voltage
- Lithium 90% depth of discharge, 85% round-trip efficiency
- 16 kWh/day average household usage, 60% night energy share

## Features

- Household presets (apartment / 3-4 bed / aircon-heavy) with fine-tuning sliders
- Raw capacity vs usable energy breakdown
- Interactive energy-flow diagram (day/night, summer/winter)
- Seasonal "can your panels refill it" check with grid import estimate
- Collapsible advanced settings (chemistry, efficiency, voltage, panel array)

## Tech

Single static `index.html` — plain HTML/CSS with [Alpine.js](https://alpinejs.dev) via CDN. No build step.

Deployed to GitHub Pages via GitHub Actions (`.github/workflows/pages.yml`).

## Development

```sh
# serve locally
python3 -m http.server 8000
```

Open http://localhost:8000 and edit `index.html`.

## Disclaimer

This is an estimate for planning, not a professional design. Confirm sizing with a CEC-accredited installer.
