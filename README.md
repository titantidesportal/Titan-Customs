# Titan Customs
### Titan Tides Logistics

A single-page web application for estimating South African customs charges on imported motor vehicles.

---

## Features

- **Live exchange rates** via ExchangeRate-API (GBP, EUR, USD, JPY, AUD, ZAR)
- **Schedule 1** — Customs duty (configurable rate, default 25%)
- **Schedule 1(2B)** — Ad Valorem (Luxury Tax) on a sliding scale, capped at 35%
- **Schedule 1(3)** — CO₂ Emissions Levy (R100/g/km over 120 g/km)
- **Customs VAT** at 15%
- **Rebate support:**
  - Full duty rebate (Permit 460.17/87.03 – Schedule 4, C&E Act 1964)
  - 5% rebate for vehicles older than 20 years
  - 25% rebate for vehicles older than 40 years (if criteria met)
- **With vs. Without Rebate** comparison
- **Print / Save PDF** built in

---

## Getting Started

This is a pure HTML/CSS/JS app — no build step required.

### Run locally
```bash
# Clone the repo
git clone https://github.com/YOUR_USERNAME/titan-customs.git
cd titan-customs

# Open in browser (any of these work)
open index.html
python3 -m http.server 8080   # then visit http://localhost:8080
```

### Deploy to GitHub Pages
1. Push to GitHub
2. Go to **Settings → Pages**
3. Set source to `main` branch, `/ (root)`
4. Your app will be live at `https://YOUR_USERNAME.github.io/titan-customs/`

---

## File Structure

```
titan-customs/
├── index.html      # The entire app (self-contained)
├── logo.jpg        # Titan Tides Logistics logo
└── README.md
```

---

## Customs Calculation Logic

Based on SARS Schedule methodology:

```
Customs Duty      = C/V × Duty Rate %
Ad Valorem (B)    = (C/V + Duty) × 1.15
Ad Valorem Rate   = min(0.0003 × B − 0.75, 0.35)
Ad Valorem Tax    = B × Ad Valorem Rate × (1 − Rebate%)
Emissions Levy    = max(0, CO₂ g/km − 120) × R100
VAT Base          = (C/V × 1.1) + Duty + Ad Valorem + Emissions
Customs VAT       = VAT Base × 15%
Total Customs     = Duty + Ad Valorem + Emissions + VAT
```

> **Note:** SARS calculates final charges using the official Shipped On Board (SOB) date exchange rate. This tool provides estimates only.

---

## License

Proprietary — © 2026 Titan Tides Logistics. All rights reserved.
