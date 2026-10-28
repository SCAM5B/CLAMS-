CLAMS v0.10.1 Smart e581 Importer

Open CLAMS_v0.10.1_Smart_e581_Importer.html in a current browser, or deploy index.html from the GitHub Pages zip.

Import > Image/PDF automatically extracts supported text-based DA Form 581 JUN 2021 landscape forms by block and table-column coordinates. The bundled PDF.js engine reads locally; PDF data is not sent to a parsing service. Scanned PDFs and other form layouts require manual review; this release does not include OCR. Confidence is rule-based extraction evidence, not a probability. Always compare the staged review with the source.

The supplied test PDF passed assertions for document number, ASP and identifier, request-from and UIC, RDD, allocation period, DODAAC, TAMIS control, training dates, DODIC, nomenclature, requested quantity, TEC, action code, substitutes and interchangeable DODIC. NSN, UI, issued/received, lot, and CC were verified blank. CLVYB NSNs are selectable suggestions; source NSN remains blank until selected.

Requested quantity never becomes physical inventory automatically. Save request review keeps a local review without adding stock; Restore saved review reloads it. To activate inventory, enter confirmed issued quantity, select an appropriate CLVYB NSN, and supply the existing location/MGRS requirements. Metadata, source extraction evidence, and line fields are retained in the saved document and JSON backup.

Excel/CSV ingestion scans every worksheet and row for header aliases, skips title/merged blank rows, accepts repeated headers, and distinguishes requested and issued quantities. Import separate e581 documents separately. Ambiguous or unlabeled quantity columns are not assumed issued.

The v0.10 baseline remains intact: operating roles, CLVYB data, counts, nodes/caches, maps and overlays, working-copy forms, brass planning, backup/restore, closeout, and presentation/PowerPoint export. Existing browser storage key is retained. Back up your workspace before switching release files or hosting origins; local browser storage is tied to origin.

Validation: actual PDF parser assertions; spreadsheet fixtures covering multiple sheets, title rows, aliases, repeated headers and blank receipts; JavaScript syntax checks; Chrome standalone upload; CLVYB suggestions; saved review; receipt guard; confirmed receipt and metadata persistence; demo and document/paperwork/presentation screen smoke checks. PowerPoint export and all map integrations were not exhaustively retested.

PDF parser is embedded, including its worker. Existing v0.10 external dependencies (Excel library, maps/MGRS, fonts) retain their internet requirements. This is a standalone HTML file, not a guarantee of all features working offline.

GitHub Pages package intentionally excludes the real PDF, extracted test results, and personal operational data. Publish only the package contents. Enable GitHub Pages for the branch/folder containing index.html. No repository was created or published by this update.

PDF.js is licensed under Apache License 2.0; see PDFJS-LICENSE.txt. Existing library notices remain embedded in the application.
