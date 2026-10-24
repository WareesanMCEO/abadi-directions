PUSARA ABADI — BLOCK DIRECTIONS
GitHub Pages deployment files

UPLOAD BOTH FILES INTO THE SAME FOLDER:
1. index.html
2. P10 MAP.png

For a GitHub Pages site using the repository root, place both files at
its root. If the site uses /docs, place both files inside /docs.
Do not rename the image unless you also update the reference in index.html.

HOW IT WORKS
- Main page includes optional Route Guidance and View Cemetery Map buttons.
- The attached original noticeboard map is displayed unchanged in a
  zoomable viewer. The office's 'YOU ARE HERE' marker stays unchanged.
- When a visitor taps a block, the browser asks for location permission
  if automatic GPS was selected.
- Clearly inside the conservative northern cemetery screening zone:
  directions run to the original destination coordinate, omitting A/B.
- Clearly outside that zone: directions pass Point A, then Point B.
- Uncertain or unavailable GPS: visitor chooses Inside / Outside /
  Shrouding Station N-1-15 manually.
- Shrouding Station manual origin uses the original N-1-15 coordinate.
- Return to Wareesan Office: directions via Point C, then Point D.
- Google Maps chooses/presents travel modes; none is forced by this index.
- GPS is not saved or tracked by this website. A clicked direction link
  passes the starting location to Google Maps when device GPS is available.

ORIGINAL COORDINATES
All 12 destinations and Points A, B, C and D are taken verbatim from the
uploaded original index.html, including trailing zeroes and decimal places.

IMPORTANT FIELD-TEST BEFORE PUBLIC USE
Automatic inside/outside detection uses CONSERVATIVE PROVISIONAL GPS screening
rectangles configured in index.html as INNER_ZONE and OUTER_ZONE. These are
NOT official or surveyed cemetery boundaries. They are a pragmatic, cautious
starting approximation derived from the supplied map and existing locations.
Staff should verify phone-GPS detection at real sites before publishing for
public use, particularly:
  - Wareesan Office and the two entry traffic lights
  - Principal Blocks 23, 25, N-1-1 and N-1-4
  - Supplementary Block 17 and N-1-3
  - Shrouding Station N-1-15
  - Other blocks such as N-1-13 and N-1-17
  - External blocks S-1-3 and S-1-8
  - GPS denied, disabled, inaccurate and slow
Near boundaries and with poor GPS readings, the directory intentionally asks
visitors to select their starting area rather than risk the wrong routing.

GOOGLE MAPS LIMITATIONS
- The selected block's coordinates can be exact, but Google Maps may not
  recognise every internal cemetery road, especially for walking.
- Google Maps may ask for a starting location if its own location access
  is unavailable, even after a manual Inside or Outside choice.
- Points A/B and C/D are included as waypoints in the specified order,
  subject to Google Maps platform capability and routing behaviour.

TECHNICAL NOTES
- Static HTML + plain JavaScript; no paid Google Maps API key or backend.
- GitHub Pages serves HTTPS, required for the browser Geolocation API.
- No location analytics, cookies, local storage, or third-party scripts.
