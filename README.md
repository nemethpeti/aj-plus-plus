# AJ++

A Chrome extension that adds missing quality-of-life features to the
[AJ Investment Research](https://www.ajinvestmentresearch.com/) site and its
dashboard.

> Unofficial community project — not affiliated with AJ Investment Research.
> It only rearranges what your own logged-in browser already displays; it does
> not scrape, store, or transmit any data.

The dashboard table is not part of the main page: it is a Plotly Dash app
embedded as an iframe from `https://consolidated.ajinvestmentresearch.com/`,
so the sorting content script targets that origin with `all_frames: true`.
A second, CSS-only content script runs on the main site.

## Features

1. **Sort by ranking** — click either "Ranking" column header.
   - 1st click: ascending (rank 1 at top)
   - 2nd click: descending
   - 3rd click: back to the original (alphabetical) order

2. **Sort by upside** — click either "1-Year Target Price" column header to
   sort by the upside/downside % shown next to the target price
   (▲ = positive, ▼ = negative).
   - 1st click: highest upside at top
   - 2nd click: lowest first
   - 3rd click: back to the original order

An ▲/▼ indicator on the header shows the active sort column and direction.

3. **Hide the announcement bar** — the pink Ghost announcement bar pinned to the
   top of every page is hidden, reclaiming ~70px of vertical space. It sits in
   normal document flow, so the page simply closes the gap.

   Note: that bar also carries the site's anti-fraud notice (AJ Investment
   Research communicates only via its private X account or its research email,
   and never requests funds). Delete `hide-announcement-bar.css` from the
   manifest if you would rather keep seeing it.

## Install (unpacked)

1. Open `chrome://extensions`
2. Enable **Developer mode** (top right)
3. Click **Load unpacked** and select the `extension/` folder
4. Reload the dashboard page

After editing files, click the reload icon on the extension card and refresh the page.

## Files

- `extension/manifest.json` — MV3 manifest
- `extension/dashboard-sort.js` — content script (sorting)
- `extension/dashboard-sort.css` — header hover/sort indicator styles
- `extension/hide-announcement-bar.css` — hides the site-wide announcement bar

## License

MIT
