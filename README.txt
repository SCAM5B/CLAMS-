CLAMS v0.10.5 — Table G-1 reference update

Open index.html in a current browser or deploy this folder to GitHub Pages. The standalone distribution is CLAMS_v0.10.5_Table_G1.html. Existing maps, Excel imports and other external resources retain their internet requirements. PDF.js and its worker are embedded.

DA PAM 700-16, 23 June 2021, Table G-1, printed page 126 / PDF page 131 is the brass/case weight reference. All 20 rows are included with their published decimal precision. Specific case types and materials take precedence over generic caliber rules and older DODIC factors. The official 9 mm value is 0.009 lb/case; it replaces the earlier user-supplied 0.0009. Marking 5.56 mm rounds use 0.0253. Ordinary brass 5.56 mm is 0.0135; brass 7.62 mm is 0.026; brass .50 cal is 0.121; steel .50 cal is 0.111.

The app matches nomenclature to the chart. Ambiguous .22, 20 mm and unspecified 12-gage case types require a case-type selection. Choose the Table G-1 case type in the importer or in the existing document's casing-reference section. Selections are saved in the document and JSON backup. Unknown casings remain unresolved or can use a documented local residue-chart entry. No subtype is inferred from an unrelated caliber.

Full-issue estimates multiply the original issued quantity by the factor. Estimated expended-case weight multiplies max(issued minus physical on-hand, 0) by the factor. Returns and count corrections can affect that consumption estimate. Exact calculated values are retained; no local turn-in rounding policy is imposed automatically.

The CLVYB Revision 21 NEWQD/MCE snapshot and retained legacy records remain available. NEW resolves at DODIC level before NSN selection only when all associated records agree on the same positive value. Conflicting/missing variants require an exact match. AB86 resolves at 0.0079 lb/item. Source NSN, lot and issued/received blanks stay blank. Refresh from CLVYB source is available in reference settings; the saved snapshot remains available offline. Storage NEWQD/MCE is not relabeled as transportation NEW.

The Smart e581 Importer reads text-based and interactive DA 581 PDFs, plus flexible Excel/CSV headers across sheets and title rows. Scanned PDFs/unsupported layouts require manual review. Saved request review is separate from physical inventory, which requires a confirmed issued quantity.

Map markers use unit names. Presentation includes per-e581 and per-line remaining/estimated consumed bars, critical-stock alerts (default 25%, configurable), and PowerPoint balance slides. These are RSR/CSR-style balance indicators; supply rates are not inferred without time and demand data. Existing counts, caches, forms, closeout, roles, backups and briefing features are retained. Back up browser data before moving hosting origins.

Validation: all 20 Table G-1 rows, 9 mm correction, marking/steel exceptions, ambiguous types, explicit subtype selection and wrong-caliber rejection; both real PDF formats; source blanks; NEW consensus/conflict; caliber precedence; stock bars; saved-workspace reload; map labels; and actual PPTX export. The real e581 PDFs and operational records are excluded from this package.

PDF.js: Apache License 2.0, see PDFJS-LICENSE.txt. Existing library notices remain embedded.
