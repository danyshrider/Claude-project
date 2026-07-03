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
- **Gmail login & view history** — sign in with your Google account; every wedding
  you open is saved to a per-account **View History** tab (most recent first, with
  view counts and timestamps), which persists across visits

## Gmail login setup

The site uses [Google Identity Services](https://developers.google.com/identity/gsi/web)
for real "Sign in with Google":

1. Go to [Google Cloud Console → APIs & Services → Credentials](https://console.cloud.google.com/apis/credentials)
2. Create an **OAuth 2.0 Client ID** of type **Web application**
3. Add your site's URL (e.g. `https://yourname.github.io`) to **Authorized JavaScript origins**
4. Paste the client ID into the `GOOGLE_CLIENT_ID` constant at the top of the
   `<script>` block in `index.html`

Until a client ID is configured (or when the page is opened from `file://`,
where Google sign-in isn't permitted), the site falls back to a **demo login**
that just asks for your Gmail address — handy for local testing.

View history is stored in the browser's `localStorage`, keyed per signed-in
email (`kk_history_<email>`), so each account gets its own history on that
device. There is no server; nothing leaves the browser.

## Running

No build step or server required — just open `index.html` in a browser.

## Customising

All package data lives in the `WEDDINGS` array in `index.html`. Add or edit
entries there (name, category, venue, theme, budget range, pax, services,
description) and the filters populate automatically. To use real photos,
replace the generated SVG art in each card with an `<img>` element.
