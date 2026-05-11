# Daily Irrigation Planner

A browser-based irrigation scheduling tool for Kansas center pivot farmers, built on the FAO-56 soil water balance model.

## What it does

- Fetches daily weather data from the [Kansas Mesonet](https://mesonet.k-state.edu/) for the selected station
- Estimates reference evapotranspiration (ETo) using a calibrated OLS model (solar radiation, VPD, wind speed) with Hargreaves as fallback
- Simulates daily soil water balance from planting to harvest using crop-specific Kc curves, SCS curve number runoff, and dynamic root growth
- Schedules center pivot irrigation based on Management Allowed Depletion (MAD) or refill-to-FC strategies
- Provides an AI summary of the season outlook via Claude Haiku 4.5 (DigitalOcean serverless proxy)

## Crops supported

Corn, Soybean, Grain Sorghum, Winter Wheat, Sunflower — with Kansas-specific planting dates and FAO-56 Kc parameters.

## Usage

Open `index.html` in a browser. No installation or build step required — all dependencies are loaded from CDN.

1. Select a Mesonet station and crop
2. Adjust soil, root depth, and center pivot settings as needed
3. Click **Generate Schedule**
4. Review the soil water balance chart and daily table
5. Click **✦ AI Summary** for a plain-language outlook (requires the serverless proxy)

## License

MIT
