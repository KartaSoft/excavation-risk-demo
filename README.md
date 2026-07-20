# Excavation Risk Intelligence — Public Demo

A live map that scores every excavation locate ticket for a gas distribution
utility by two questions: how likely is this dig to damage buried gas pipe, and
how much would it matter if it did. This repository is a **public demonstration
built on entirely synthetic data** — there are no real tickets, excavators, pipe,
or utility anywhere in it.

**▶ Live demo:** https://imrebartos-kartasoft.github.io/excavation-risk-demo/

## What it shows

- A synthetic gas distribution network for **Columbus, Ohio** — mains following
  the street grid, service lines branching to buildings, coloured by pipe
  *vulnerability* (aging cast iron and bare steel run hot; modern polyethylene
  runs cool).
- One synthetic day of excavation tickets, each flagged **High / Moderate / Low**
  priority with separate likelihood and impact ratings.
- Click any ticket for the two headline indicators plus eight driver pills —
  excavator history, pipe vulnerability, work activity, locate quality, service
  disruption, critical facilities, business district, and transmission — each with
  a plain-language reason line, rendered exactly like the production product.
- A **Log Field Action** button that opens a demo-mode form. It validates input
  and shows a local confirmation only; nothing is submitted anywhere and no
  credentials are used.

## How the synthetic data is made

Street and building geometry is real, public **OpenStreetMap** data. Everything
else — pipe material, vintage, diameter, vulnerability scores, tickets,
excavator names, and all risk values — is generated from published industry
references and clearly-labelled engineering defaults:

- **PHMSA** gas distribution annual-report summaries (material and vintage mix).
- **Common Ground Alliance (CGA) DIRT** reports (damage-cause and work-type mix).
- General distribution-engineering rationale, with any unsourced figure
  hardcoded as a commented design default.

No proprietary or operator-supplied data is used anywhere. Excavator names are
invented from neutral patterns and match no real company.

## Contents

| Path | What it is |
|------|-----------|
| `docs/index.html` | Landing page (this site's home) |
| `docs/map.html` | Self-contained Leaflet map — all three layers and popups inlined, no login or token required |
| `docs/action_form.html` | Demo-mode "Log Field Action" form (local only) |
| `docs/flags.geojson` | Synthetic ticket points (60) |
| `docs/areas.geojson` | Synthetic dig-area / cohort polygons |
| `docs/segments.geojson` | Synthetic mains and service lines |

The map is fully self-contained: the GeoJSON is inlined, so an anonymous browser
with no login renders the map, all three layers, and working popups. The only
external dependency is the Leaflet library from a public CDN.

## Not affiliated

This demonstration is not affiliated with, and contains no data from, any
specific utility. All content is illustrative and synthetic.
