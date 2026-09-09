TONGA KEY STATISTICS — DATA-DRIVEN VERSION

WHAT CHANGED
------------
The visual page no longer hardcodes the statistics.
index.html reads all cards and chart values from data.json.

FILES
-----
index.html   - layout, styling and rendering logic
data.json    - all values, periods, card labels and chart data

HOW UPDATES WORK
----------------
Change a value in data.json and reload the page.
The corresponding card/chart changes automatically.

Example:
"label": "Annual inflation",
"value": "9.3%",
"period": "July 2026"

When a new official CPI figure is published, only edit those fields.

REMOTE / LIVE DATA
------------------
The page supports a remote JSON data feed.

Normal use:
https://YOUR-SITE/index.html

Remote data use:
https://YOUR-SITE/index.html?data=https://YOUR-DATA-SOURCE/tonga.json

This means index.html can stay unchanged while a script, ArcGIS service,
GitHub-hosted JSON, or another approved data service updates the JSON file.

IMPORTANT
---------
This version is DATA-DRIVEN, not yet FULLY AUTOMATED.
For full automation, each official Tonga source needs an update method:
- API / ArcGIS Feature Service where available
- downloadable CSV/JSON where available
- scheduled extraction/validation for webpages or PDFs where no feed exists

Recommended rollout:
1. Host this version.
2. Use one central JSON file as the source of truth.
3. Automate the easiest official feeds first (e.g. regularly published structured data).
4. Keep PDF-only indicators human-verified until a robust extraction workflow is approved.

Embedding in Experience Builder:
- Add an Embed widget.
- Paste the hosted HTTPS URL for index.html.
- Set width to 100%.
