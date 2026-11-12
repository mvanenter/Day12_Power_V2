# Aotearoa’s power stations — GitHub Pages

This is a static Leaflet page. Deploy `index.html` and the `data` folder at the same relative paths in your GitHub Pages repository. No user uploads are needed.

## What changed

The proposed-generation panel no longer displays a broken, disabled “Show proposed projects” switch when there are no verified mapped projects. Instead, it displays the **Electricity Authority's October 2025 historical snapshot (288 proposed projects, 44.3 GW)** and a working link to the Authority's regularly updated official pipeline dashboard. Source: https://www.ea.govt.nz/news/eye-on-electricity/new-generation-projects-flowing-through-the-investment-pipeline/

**Important:** the historic summary is not a current project inventory, and its proposed capacity is not added to your existing OSM capacity totals. The online official dashboard is the place to inspect more current pipeline information.

The optional map toggle appears **only if** `data/planned_projects.geojson` contains georeferenced, verifiable proposals. The bundled GeoJSON deliberately contains zero features; no coordinates have been fabricated. The map remains useful without that optional layer.

## Publish verified proposed sites later

Create WGS84 GeoJSON Point features in `data/planned_projects.geojson`, each with `name`, `capacity_mw`, `technology`, `status`, `source_url` (HTTPS), and `source_date` properties. Use only positions supported by evidence and permission for reuse. Once uploaded to GitHub Pages, the optional layer automatically becomes available without code changes.

## Preview

You may open `index.html` directly for its embedded OSM station map and source links. The optional GeoJSON fetch only runs when served over HTTP(S). To test it locally, serve this folder with `python -m http.server 8000`, then open http://localhost:8000/.
