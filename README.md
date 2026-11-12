# Aotearoa’s Power Stations ⚡

**An interactive map of electricity generation across New Zealand**  
*#30DayMapChallenge 2026 — Day 12: Power*

🌐 **[Explore the live map](https://mvanenter.github.io/Day12_Power_V2/)**

This project explores **where electricity is generated in Aotearoa New Zealand**, the mix of generation technologies, and the differences between the North and South Islands. It combines mapped power stations and high-voltage transmission lines in a browser-based map, with interactive filtering and a summary of the official generation-investment pipeline.

The map is primarily an **OpenStreetMap (OSM)-based inventory**. It is **not a complete official register** of every operating station and should not be treated as real-time generation or demand data.

## What you can explore

- **Generation by fuel:** toggle hydro, wind, geothermal, thermal, gas, solar and other stations.
- **Station capacity:** circle sizes are scaled by mapped installed capacity (MW); select a circle to see further details, including operator and commissioning year *where available*.
- **Transmission network:** independently show or hide mapped **220 kV**, **110 kV** and **HVDC** routes.
- **Island comparison:** compare mapped capacity and station counts in the North and South Islands.
- **Station search:** find a mapped station or operator and zoom to its location.
- **Responsive layout:** use the layer panel and the collapsible generation overview on desktop or mobile.
- **Future-generation context:** review a *historical* Electricity Authority pipeline snapshot, with a link to the latest official dashboard.

## How to use the map

1. Open **[the interactive website](https://mvanenter.github.io/Day12_Power_V2/)**.
2. Use **Map layers** to switch generation types and transmission routes on or off.
3. Click or tap a station circle to inspect its available attributes.
4. Open **Generation overview** for capacity summaries, island comparisons and search.
5. Pan and zoom to investigate particular regions. On smaller screens, collapse the overview to give the map more space.

The totals and comparisons relate to **stations represented in this map**, not necessarily the entire New Zealand generation fleet. Installed capacity (MW) is also different from electricity actually generated over time (MWh/GWh).

## Data and sources

| Source | Used for | Important note |
|---|---|---|
| [OpenStreetMap contributors](https://www.openstreetmap.org/) | Primary station locations, technology and tagged capacity; high-voltage lines | Open Database License (ODbL); mapped coverage and tags can be incomplete |
| [Natural Earth](https://www.naturalearthdata.com/) | Coastline / geographical context | Cartographic background |
| [Wikipedia — List of power stations in New Zealand](https://en.wikipedia.org/wiki/List_of_power_stations_in_New_Zealand) | Selected capacity cross-checks and enrichment | Wikipedia content has separate attribution and licence requirements |
| [Genesis Energy](https://www.genesisenergy.co.nz/) and [Contact Energy](https://contact.co.nz/) | Selected station-capacity checks | Operator-published values may differ from OSM tags |
| [Electricity Authority — Generation investment pipeline](https://www.ea.govt.nz/data-and-insights/charts-and-dashboards/generation-investment-pipeline/) | Context on proposed generation | This is separate from the operating station layer |
| [Electricity Authority — Existing generation fleet](https://www.emi.ea.govt.nz/Wholesale/Datasets/Generation/GenerationFleet/Existing) | Further official reference / validation | Not a wholesale replacement for the OSM base layer |
| [MBIE — Electricity statistics](https://www.mbie.govt.nz/building-and-energy/energy-and-natural-resources/energy-statistics-and-modelling/energy-statistics/electricity-statistics) | National context and cross-checking | National statistics are not directly equivalent to the mapped inventory |

The sidebar presents an **October 2025** Electricity Authority pipeline snapshot of **288 projects / 44.3 GW** of proposed capacity. These figures are historical, represent proposals rather than operating plants, and **are not added** to mapped operating capacity. For current information, use the official pipeline dashboard linked above.

### What is *not* shown

- All lower-voltage and embedded network connections; displayed transmission routes are primarily mapped lines at **110 kV and above**.
- Guaranteed complete coverage of small solar, wind, hydro or other generation facilities.
- Live electricity dispatch, demand, generation output or storage levels.
- Individual proposed projects unless a separate, verified coordinate dataset has been provided.

**Data-quality caution:** Coordinates, capacity, classifications, names and dates reflect source availability. Missing commissioning dates or operators should not be interpreted as zero or unknown ownership. Some station capacities may differ from official operator ratings. Transmission gaps on this map do not necessarily indicate missing physical connections.

## Built with

- **Leaflet.js** — interactive web mapping
- **HTML, CSS and JavaScript** — user interface and responsive controls
- **PapaParse** — parsing the station dataset embedded in the map page
- **GeoJSON** — geographical data representation
- **GitHub Pages** — static web hosting

The site runs in the browser; no account or user data upload is required.

## Project files

```text
Day12_Power_V2/
├── index.html                 # Public interactive map
├── data/
│   └── planned_projects.geojson  # Optional verified proposed-project points (currently empty)
├── stations.csv               # Station dataset retained in the repository
├── nz.geojson                # New Zealand geography retained in the repository
├── export.geojson            # Additional source export retained in the repository
└── README.md
```

The published page contains its core map information within `index.html`. It optionally requests `data/planned_projects.geojson` when served through GitHub Pages. That file has no verified features at present; the map therefore presents the pipeline as contextual statistics rather than invented points.

## Run locally

You can open `index.html` in a browser to explore the embedded station map. For full testing of optional file-loaded layers, serve the repository through a local web server:

```bash
python -m http.server 8000
```

Then open `http://localhost:8000/`.

## About this project

Created by **Melanie van Enter** for the **#30DayMapChallenge 2026 — Day 12: Power**. The goal was to use an interactive, spatial view to communicate New Zealand’s electricity generation geography while remaining transparent about underlying data limitations.

**Feedback and suggestions** are welcome through the repository’s [Issues](https://github.com/mvanenter/Day12_Power_V2/issues) page.

## Attribution

Map and application: **Melanie van Enter**. Base data: **© OpenStreetMap contributors (ODbL)**; coastline: **Natural Earth**. Selected station facts were cross-checked against the sources identified above. Please respect the original sources’ attribution and reuse terms if reusing the data or map.

