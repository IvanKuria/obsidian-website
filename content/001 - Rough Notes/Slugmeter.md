---
title: "Slugmeter"
type: project
tags:
  - project
---

**Related:** [[Projects MOC]]

# SlugMeter -- Newspaper Interview Talking Points

  

## The Origin Story

  

- Got a $48 parking ticket (P5 VC 22500A -- parked within intersection). Deserved it.

- Went to the AIMS (Automated Issuance Management System) portal to pay it.

- The portal has zero authentication -- you type in a citation number and get everything: location, time, violation, fine, vehicle make/model/color. No proof of ownership required.

- Citation numbers are sequential: `26SC100001` = year 2026, device SC1, sequence 00001. Just increment the last digits to enumerate every ticket ever issued.

- No rate limiting, no CAPTCHA, no bot detection. The system is wide open.

- Wrote a scraper that evening, left it running overnight, had 200K+ citations by morning.

  

## What SlugMeter Actually Is

  

- A real-time parking citation tracker for Santa Cruz with 218,000+ citations from 2019--2026.

- **Live map**: new citations appear within minutes of being issued via WebSocket push.

- **Dashboard**: filterable by device and time period, shows hourly/daily distributions, top violations, revenue.

- **Citation search**: searchable, sortable archive of every citation with CSV bulk export.

- **Insights page**: 6 analytical tabs -- Revenue, Enforcement Patterns, Street Rankings, Equity Analysis, Anomaly Detection, Community contributions.

- **Risk Calculator**: select any street and see a danger heatmap (day x hour), percentile rank vs all other streets.

- **Safe Parking Score**: for any given day/hour, shows which locations are safest to park.

  

## Key Technical Details

  

- **Data source**: City of Santa Cruz public AIMS portal. Public record under the California Public Records Act (CPRA).

- **Citation number format**: `{2-digit year}SC{device number}{5-digit sequence}`. Example: `26SC300042` = 42nd citation from device SC3 in 2026.

- **8 enforcement devices**: SC1 through SC8. These are hardware units, not individual officers. SC8 alone accounts for ~25% of all tickets -- likely a vehicle-mounted License Plate Recognition (LPR) system.

- **Scraping rate**: ~8 seconds per citation (2 HTTP requests: search page + detail page). Slow, but steady and respectful of city infrastructure.

- **No PII stored**: License plates and VINs are stripped before anything enters the database. Only public data: location, time, violation type, fine amount, vehicle make/model/color.

- **Geocoding**: ~89% of citations are geocoded using Nominatim (free, open-source). The remaining ~11% reference parking lot space numbers (e.g., "LOT 3 SPACE #3042") that can't be placed on a map. They're still in all aggregate stats, just not on the map.

  

## Tech Stack

  

| Layer | Tool |

|-------|------|

| Frontend | Next.js 15 (React) |

| Database | Supabase (PostgreSQL) |

| Real-time | WebSockets |

| Maps | MapLibre GL |

| Charts | Recharts |

| Geocoding | Nominatim (OpenStreetMap) |

| Hosting | Vercel |

| Styling | Tailwind CSS v4 |

  

## Interesting Findings from the Data

  

- **SC8 is the busiest device** (~25% of all tickets). Its volume and never-stopping pattern suggest it's an LPR mounted on a vehicle, not a handheld unit.

- **Anomaly detection** surfaces statistical outliers: days where a device wrote way more tickets than average (z-score > 2), "meter trap" locations that generate citations every single day, record days city-wide, and peak hours where enforcement concentrates.

- **Equity analysis**: choropleth map overlaying citation density against census tract income data. Includes a scatter plot with Pearson correlation to show whether lower-income areas get disproportionately ticketed.

- **Community contribution**: a Reddit user (camojorts) took the bulk CSV export, built a hex-binned density map using Folium with log10 scaling and per-weekday toggles. It's embedded on the Insights page.

  

## Security Recommendations for the City

  

These are on the about page. Straightforward fixes:

  

1. **Use non-sequential citation IDs** -- random or UUID-based IDs would make bulk enumeration infeasible.

2. **Require proof of ownership** -- ask for the license plate or VIN alongside the citation number.

3. **Implement rate limiting** -- even 10 lookups/minute per IP would make scraping orders of magnitude slower.

4. **Add CAPTCHA or bot detection** -- prevents automated scripts from querying the system.

5. **Separate public and private data** -- the API returns vehicle details in the same response as citation metadata. Split them.

  

None of these are exotic. Most modern citation portals already do several of them.

  

## Numbers to Cite

  

- **218,000+** total citations in the database

- **2019--2026** time span covered

- **8** enforcement devices

- **56** backfill jobs (8 devices x 7 years)

- **~89%** geocoded and mapped

- **$48** -- the ticket that started it all