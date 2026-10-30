CLAMS v0.11.1 — XO Brief movement matrix — 29 October 2026

Vehicle requirements and TDA now populate a combined panel directly below the map in the visible XO Brief grid. The panel shows the selected vehicle profile, required trucks/trailers, gross load, DODIC/quantity/package allocation, and saved route distance, drive, halt and total minutes. It uses the existing saved plan and respects the brief document/unit scope. Commander attention is retained beside the e581 status. The full-screen layout fits its header, KPIs, map and matrix within the screen; smaller layouts place the matrix immediately after the map. Map fitting reserves room for unit labels and full route/radius extents.

PowerPoint includes a combined movement overview slide, with route imagery above vehicle and TDA tables. Detailed route and load slides remain available. Stale routes, partial loads and missing selections stay visible as such. The matrix displays scoped loads and route legs; it does not invent vehicle-to-route assignments.

Verified: real full-screen layout at 1600x1000 and compact 1090x562, responsive map/matrix order, AB86 13,600 rounds = 17 packages / 1,322.6 lb / 1 truck, TDA drive+halt totals, unit/document scopes, stale/empty states, and actual combined PPTX slide with imagery and both tables. Existing stock and planning data are preserved.

CLAMS v0.11.0 — Logistics additions — 29 October 2026

Open index.html, or deploy this folder at the GitHub Pages root.
Existing browser workspace, roles, e581s, caches and balances are preserved.
Use the same browser and website address to retain the existing workspace.

What's new
- Import e581: drop one PDF into the drop zone or click to browse. Excel/CSV and image upload choices removed. PDF parsing and manual review remain.
- e581 register: BAO can add/correct a lot after import under Admin / lot numbers. History records the old/new lot; counts and cache allocations are preserved. One lot per line.
- Documents / Inventory: select entire e581, main site or cache, enter physical counts, then Capture inventory / Print / PDF. Report lists DODIC, nomenclature, quantity, lot and line NEW with a grand total. Missing NEW is flagged as incomplete; zero is not substituted. Dated snapshots are included in CLAMS backups. This does not automatically post count changes; use On-Hand for balance adjustments.
- TDA: select two known locations. Get road estimate requests a route from public OSRM using only the two coordinates, after the user presses that button. The road trace, distance, driving minutes, planned halt and leg breakdown are saved. No live traffic, convoy delay or vehicle-clearance model. Manual/offline mode accepts a verified road distance and planning speed and draws a dashed endpoint connector, clearly labeled as not a road trace. Changed/missing endpoints mark a saved route stale.
- Vehicle requirements: select e581 lines and movement quantities; choose a CLVYB package/load pattern, truck, optional companion trailer, pallet/package mode, stacking layers and reserved payload. Optional verified cargo-capacity overrides are supported. Missing packaging, classification, fit or quantities produce partial results. Requirements are for one lift with one vehicle type. Counts are not reduced by planning a movement.
- XO Brief / Print / PowerPoint: scoped TDA routes and vehicle allocation tables are included. Colored routes are included in full-map imagery exports; map fitting includes route geometry as well as all node/ring extents. Existing NEW, Table G-1 brass and map features retained.

Reference implementation
GroundFleet and LoadCore are copied unchanged from SCAM5B/clv-yellow-book snapshot a1743e7af17744f33c17d59e9f84537e1087eb59. Embedded CAPULDI: 16,660 records from the same CLVYB package data. Missing values remain missing. Vehicle source links are shown in the app. Packaging gross weight is distinct from storage NEW/QD/MCE; storage NEW is not substituted as transport NEW.
OSRM API documentation: https://github.com/Project-OSRM/osrm-backend/blob/master/docs/http.md
Source CLVYB: https://github.com/SCAM5B/clv-yellow-book

Validation
Both real TAMIS DA 581 fixtures passed (W506V162960001 and W90FZM62891023); blank issued/lot fields preserved. PDF drag/drop, BAO lot audit and cache propagation, inventory counts/PDF, unresolved NEW, vehicle allocation and capacity overrides, route success/failure, route capture, persistence and actual PPTX output checked. Existing NEW/brass/posture/PDF regression checks passed. Real routing checked with public Berlin sample coordinates. No real e581 fixture or user workspace is packaged.

Previous release notes follow.

CLAMS v0.10.6 — Table G-1 reference update

Open index.html in a current browser or deploy this folder to GitHub Pages. The standalone distribution is CLAMS_v0.10.6_Table_G1.html. Existing maps, Excel imports and other external resources retain their internet requirements. PDF.js and its worker are embedded.

DA PAM 700-16, 23 June 2021, Table G-1, printed page 126 / PDF page 131 is the brass/case weight reference. All 20 rows are included with their published decimal precision. Specific case types and materials take precedence over generic caliber rules and older DODIC factors. The official 9 mm value is 0.009 lb/case; it replaces the earlier user-supplied 0.0009. Marking 5.56 mm rounds use 0.0253. Ordinary brass 5.56 mm is 0.0135; brass 7.62 mm is 0.026; brass .50 cal is 0.121; steel .50 cal is 0.111.

The app matches nomenclature to the chart. Ambiguous .22, 20 mm and unspecified 12-gage case types require a case-type selection. Choose the Table G-1 case type in the importer or in the existing document's casing-reference section. Selections are saved in the document and JSON backup. Unknown casings remain unresolved or can use a documented local residue-chart entry. No subtype is inferred from an unrelated caliber.

Full-issue estimates multiply the original issued quantity by the factor. Estimated expended-case weight multiplies max(issued minus physical on-hand, 0) by the factor. Returns and count corrections can affect that consumption estimate. Exact calculated values are retained; no local turn-in rounding policy is imposed automatically.

The CLVYB Revision 21 NEWQD/MCE snapshot and retained legacy records remain available. NEW resolves at DODIC level before NSN selection only when all associated records agree on the same positive value. Conflicting/missing variants require an exact match. AB86 resolves at 0.0079 lb/item. Source NSN, lot and issued/received blanks stay blank. Refresh from CLVYB source is available in reference settings; the saved snapshot remains available offline. Storage NEWQD/MCE is not relabeled as transportation NEW.

The Smart e581 Importer reads text-based and interactive DA 581 PDFs, plus flexible Excel/CSV headers across sheets and title rows. Scanned PDFs/unsupported layouts require manual review. Saved request review is separate from physical inventory, which requires a confirmed issued quantity.

Map markers use unit names. Presentation includes per-e581 and per-line remaining/estimated consumed bars, critical-stock alerts (default 25%, configurable), and PowerPoint balance slides. These are RSR/CSR-style balance indicators; supply rates are not inferred without time and demand data. Existing counts, caches, forms, closeout, roles, backups and briefing features are retained. Back up browser data before moving hosting origins.

Validation: all 20 Table G-1 rows, 9 mm correction, marking/steel exceptions, ambiguous types, explicit subtype selection and wrong-caliber rejection; both real PDF formats; source blanks; NEW consensus/conflict; caliber precedence; stock bars; saved-workspace reload; map labels; and actual PPTX export. The real e581 PDFs and operational records are excluded from this package.

PDF.js: Apache License 2.0, see PDFJS-LICENSE.txt. Existing library notices remain embedded.

0.10.6 Presentation imagery and full-radius capture
The presentation map clears earlier empty placeholders before Leaflet initializes, defers hidden-container initialization, and refits after layout, fullscreen, scope changes and resizing. Every valid main-site and cache location is included, and framing includes complete radius extents rather than only marker centers. Missing coordinates are reported by name; valid zero coordinates and recoverable MGRS are supported. Rings use a vivid outline and fill: red blast, amber thermal/fire, blue approved override. No new radius is invented for items without a computed or approved distance.
Fit all resets the scene. Expand map opens the map across the window. Map image exports a 1920x1080 PNG of all in-scope locations and radius rings, including locations too far apart for readable individual rings in an overview. PowerPoint export adds the all-locations map plus an individual image slide for each radius-bearing location, with correctly scaled geographic rings. Existing paginated registers and source notes remain available. Print/PDF uses the same captured map image.
Leaflet and MGRS, including control icons, are embedded to avoid map-engine startup downloads. Satellite imagery remains internet-dependent. Export waits for imagery or produces a clearly labeled geographic plot with all nodes/rings when tiles are unavailable; partial imagery is labeled. Live maps report imagery loading/failure separately from missing coordinates.
Validation: three main sites, one cache, four rings, full ring framing in live and exported maps, map expansion, resizing, empty-to-populated recovery, scope changes, MGRS/zero coordinates, antimeridian, imagery failure, actual PowerPoint image slides, and real Esri imagery capture (40/40 tiles). Both e581 PDF formats, NEW calculations, all Table G-1 factors, saved-workspace reload and briefing export also passed regression checks. Synthetic map fixtures and operational source files are excluded from the deployment package.
Leaflet and MGRS notices: LEAFLET-LICENSE.txt and MGRS-LICENSE.txt.
