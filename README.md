# PHASE 10 EXHUMATION PROGRAMME — Cemetery Directions

A mobile-friendly bilingual English/Malay directory for the Phase 10 Exhumation Programme, covering Principal and Supplementary Blocks and the Shrouding Station at Pusara Abadi, two Reinterment Blocks at Pusara Aman, and Wareesan Office.

## Files — keep these at the repository root

```
index.html        # Main webpage; includes a self-contained, embedded full-resolution PNG map
P10 MAP.png       # Original unmodified map image; also acts as an image fallback and full-size link
PUSARA_ABADI_GEOFENCE.geojson  # Reference copy of the provisional GPS polygon
README.md         # Deployment, routing and operational notes
```

There is **no build process, API key, database or framework**. All HTML, CSS, JavaScript and the PNG image data needed for the main page are embedded in `index.html`. The separate `P10 MAP.png` is included for viewing the full-size original image and for browser fallback. `PUSARA_ABADI_GEOFENCE.geojson` is a reference copy; the geofence coordinates are also embedded in `index.html` so GPS classification does not depend on loading an extra file. **Do not rename `P10 MAP.png`** unless you also update the HTML fallback and full-size-image link. The PNG embedded in the HTML is an exact byte copy of the supplied image, not a reconstructed map.

## Publish on GitHub Pages

1. Create a GitHub repository and upload `index.html`, `P10 MAP.png`, `PUSARA_ABADI_GEOFENCE.geojson` and `README.md` directly into the repository **root** (not a subfolder).
2. Commit the files to the `main` branch.
3. Open **Settings → Pages** for that repository.
4. Under **Build and deployment**, choose **Deploy from a branch**, branch `main`, and folder `/(root)`; then save.
5. Open the URL displayed by GitHub Pages. For an ordinary project repository this normally looks like `https://USERNAME.github.io/REPOSITORY/`.
6. Test the website **on a real mobile phone** at the cemetery before giving the URL to visitors.

Do not upload only the ZIP as a file to the repository: extract it and upload the individual files from its root.

**Publication reminder:** A publicly accessible GitHub Pages website publishes the locations and operational details written in this directory. Obtain any required organisational approval before publication.

## Categories and destinations

- **Principal Blocks — Pusara Abadi:** 23, 24, 25, 26, N-429, N-1-1 and N-1-2.
- **Supplementary Blocks — Pusara Abadi:** 17, N-1-3 and N-1-4.
- **Shrouding Station — Pusara Abadi:** Block N-1-15.
- **Reinterment — Pusara Aman:** Block S-1-3 and Block S-1-8.
- **Wareesan Office:** selectable destination and fixed starting point.

The user interface is bilingual English/Malay and works on desktop and mobile. **English is displayed in UPPERCASE; Malay is displayed in sentence case and italics**, preserving proper nouns, geographical names and acronyms. The original Phase 10 map image is preserved unmodified, including the labels printed in that image.

## Final interface colour scheme (approved)

The four cemetery categories use a **distinct dark-to-light green progression**, in the order shown on the website. The headings are a single bilingual label (English UPPERCASE; Malay in sentence case and *italics*) in neutral charcoal `#27312D`. Within the buttons, English is visually uppercase and Malay is italicised in sentence case.

| Function / category | Button background | Lettering |
|---|---|---|
| Principal Blocks | Deep forest green `#143E2C` | White `#FFFFFF` |
| Supplementary Blocks | Forest green `#286347` | White `#FFFFFF` |
| Shrouding Station | Medium green `#3E805D` | White `#FFFFFF` |
| Reinterment — Pusara Aman | Light sage green `#A9D4B8` | Dark forest `#173E2B`, not white |
| Wareesan Office | Slate grey `#475569` | White `#FFFFFF` |
| Route Guidance & View Cemetery Map | White `#FFFFFF`; dark green `#143E2C` outline | Dark green `#143E2C` |

The warm off-white page background is `#F4F1E8`. This is a visual category hierarchy, **not an operational severity or priority rating**. The original PNG map retains its own printed legend and colours and is not recoloured.

## Starting Point options

1. **Detect my location automatically (GPS)** — requests device location and classifies it using the provisional GPS geofence traced from the supplied KML. GPS permission and a secure context (e.g. GitHub Pages HTTPS) are required.
2. **Outside Pusara Abadi / Near Wareesan Office** — selects the outside *routing rule*, but does not assume the visitor is physically at the office. Google Maps may determine or request the origin.
3. **Already inside Pusara Abadi** — selects internal/exit rules; Google Maps may determine or request the actual origin.
4. **I am at Shrouding Station (N-1-15)** — specifies the station's fixed coordinates as origin and treats it as inside Pusara Abadi.
5. **I am at Wareesan Office** — specifies office coordinates `1.3732278,103.6943606` as origin and treats it as outside Pusara Abadi. **Select only when actually at the office.**

If GPS fails or has insufficient accuracy, the directory offers a manual starting-point selection. GPS classifications use the user-drawn provisional polygon, not a surveyed cemetery boundary, and must be checked in the field. If phone accuracy overlaps the boundary (or is worse than 100 m), the directory asks for manual confirmation.

## Routing rules (operational waypoints)

| Starting area | Destination | Waypoints sent to Google Maps |
|---|---|---|
| Outside Pusara Abadi (including Wareesan Office) | Principal/Supplementary/Shrouding Station | **Point A then Point B** |
| Inside Pusara Abadi (including Shrouding Station) | Principal/Supplementary/Shrouding Station | None (direct) |
| Inside Pusara Abadi (including Shrouding Station) | Wareesan Office | **Point C then Point D** |
| Inside Pusara Abadi (including Shrouding Station) | Reinterment Block S-1-3 / S-1-8 | **Point C then Point D** |
| Outside Pusara Abadi (including Wareesan Office) | Reinterment Block S-1-3 / S-1-8 | None (direct) |
| Outside Pusara Abadi | Wareesan Office | None (direct) |

**Waypoint coordinates (do not change without operational verification):**

- A — 1st traffic light: `1.3710219,103.685368`
- B — 2nd traffic light: `1.3824528,103.6841783`
- C — 1st bus stop: `1.373591,103.685493`
- D — 2nd bus stop: `1.370355,103.688004`

Reinterment coordinates:

- Block S-1-3: `1.370752,103.6928`
- Block S-1-8: `1.369471,103.691438`

The supplied waypoint sequence is included in Google Maps links. **The final revision applies the approved four-shade green palette and fixes the bilingual route-reminder display. All existing destination and waypoint coordinates and A/B/C/D route conditions remain unchanged.** **It does not guarantee a permitted or navigable route**: Google Maps can change road selections and may not know internal cemetery roads or restrictions. Check routes and suitable gate/road access in the field. Visitors should obey road signs, staff instructions and current road closures. Travel mode is not forced.

## Cemetery Map button

- **Original Cemetery Map** — primary map view; shows your exact supplied 1463 × 2048 PNG embedded inside `index.html`, including when `index.html` is opened offline. Zoom and scroll are available. An **Open full-size PNG** link points to the separate bundled file. If the embedded image fails, the page tries the bundled PNG.
- **Coordinate Overview** — internal map built from the destinations' coordinates. It includes both reinterment points and filters for All Areas/Pusara Abadi/Pusara Aman, but is a schematic plot: *not* a road map or surveyed boundary.
- **Online Street Map** — OpenStreetMap-based viewer; requires internet. It is not guaranteed to show every internal cemetery access road.

**The previous three-view map design is deliberately retained:** The Online Street Map is the original simple OpenStreetMap iframe; there is no interactive marker clustering or geofence overlay. The polygon runs only in the background to classify the visitor's starting area.

**Important map distinction:** The original image says “YOU ARE HERE (MCEO)”; that label refers to a fixed mapped location, **not** a visitor's GPS position. The original image does not specifically mark S-1-3 and S-1-8. For those use the coordinate overview or Google Maps link.

## Editing and testing

All destination coordinates are stored in `LOCATIONS` and operational waypoints in `WAYPOINTS` near the start of the JavaScript in `index.html`. `classifyPosition(...)` uses the embedded `PUSARA_ABADI_BOUNDARY` polygon with a GPS accuracy buffer to determine inside, outside or uncertain; `routeType(...)` determines whether entry waypoints A/B, exit waypoints C/D, or direct routing apply; `buildMapsUrl(...)` builds the Google Maps link.

To update the actual original map in the future, replace `P10 MAP.png` **and also replace the image data embedded in `index.html`**; changing the separate file by itself does **not** update the embedded copy.

Open `index.html` locally to preview the page and original PNG without a server. Test GPS and Google Maps on the published HTTPS GitHub Pages website; local `file://` previews may not allow location detection. Directions and online street map require an internet connection.

Before public release, check each Google Maps route on actual devices and verify the A/B and C/D access rules, including the exit route to S-1-3 and S-1-8, with on-site operations personnel.

## Responsibility and limitations

This directory is an aid for navigation, not a surveyed map, official boundary certification, guarantee of road access, or substitute for on-site staff. Follow cemetery signs and operational directions if there is any inconsistency.

## Pusara Abadi GPS boundary (provisional)

The polygon was drawn by the user in Google My Maps and exported as a closed KML line. It was converted into a polygon with **19 distinct vertices** (20 coordinates including the repeated closing point). The embedded polygon and accompanying GeoJSON preserve the provided outline; **no existing destination or waypoint GPS coordinates were changed**.

Expected location check against the polygon:

- All 7 Principal Blocks, 3 Supplementary Blocks and Shrouding Station are inside.
- Wareesan Office and both Reinterment Blocks are outside.
- Other existing cemetery blocks (such as N-1-13, N-1-17 and N-1-20) are handled by GPS area, not by matching their names to the destination menu. These unlisted points have **not been independently verified** against the polygon because their GPS coordinates were not supplied.

GPS logic in `classifyPosition(...)`:

1. Ask the device for a fresh high-accuracy GPS reading through the browser's Geolocation API.
2. If the reported accuracy is greater than 100 m or location is unavailable, ask for manual selection.
3. Compute the approximate distance from the reading to the closest polygon edge. If the GPS accuracy radius (minimum 15 m for safety) touches an edge, ask the user to confirm **inside or outside** instead of guessing.
4. Otherwise, use a point-in-polygon test to classify the visitor as inside or outside Pusara Abadi and apply the existing A/B or C/D rules.

The geofence **does not add any buttons or visual polygon overlay to the Online Street Map**. To edit the geofence in future, update the embedded `PUSARA_ABADI_BOUNDARY` array in `index.html` and the GeoJSON reference file together. Editing only the GeoJSON will not alter the deployed website.

**Field checks required:** Confirm boundary behaviour at known blocks, perimeter roads, entrances and exits, including both sides of the boundary; the user's KML is a provisional operational reference rather than an official surveyed boundary. Staff and on-site signs take precedence over browser routing.
