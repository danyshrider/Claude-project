# Kasih & Kahwin — Malaysian Wedding Gallery

A gallery-style website for browsing and filtering Malaysian wedding packages.

## Features

- **Wedding categories** — Malay, Chinese, Indian, Peranakan, and Fusion weddings, selectable via tabs.
- **Filters**:
  - **Venue** — Around Kuala Lumpur, Selangor, Penang, Johor Bahru, Malacca, Langkawi, and more
  - **Theme** — Outdoor Wedding, Ballroom, Beach Wedding, Garden Party, Heritage Courtyard, etc.
  - **Budget** — RM ranges from below RM10,000 up to above RM100,000
  - **Pax** — intimate (≤100) to kenduri besar (600+)
  - **Services Included** — MUA, wedding dress & attire, photographer, R&B food stalls, pelamin, number of tables, and more (multi-select; results must include *all* checked services)
- Gallery cards with illustrated venue art, category tags, and service chips
- Click any card for a detail view with the full service list and an enquiry button
- Empty state and "clear all" when filters match nothing

## Running

No build step or server required — just open `index.html` in a browser.

## Customising

All package data lives in the `WEDDINGS` array in `index.html`. Add or edit
entries there (name, category, venue, theme, budget range, pax, services,
description) and the filters populate automatically. To use real photos,
replace the generated SVG art in each card with an `<img>` element.
