## CMS vs Back Office Reconciliation - v1.0.0

A single-page web app that reconciles a CMS (master) Excel file against a
Back Office Excel file and produces a final Excel report.

### Features
- Upload the CMS file and the Back Office file separately
- Choose the worksheet, header row, and key, date and amount columns for each file
- Optional scope filter (for example TRANSACTION NAME = bKash Cash In)
- Matching on key (such as approval code), same calendar date, and amount
- Statuses: MATCHED, CMS_ONLY, BACKOFFICE_ONLY, AMOUNT_MISMATCH,
  DATE_MISMATCH, DUPLICATE, REVIEW_REQUIRED
- Configurable date-mismatch tolerance (default 60 minutes) for midnight posting differences
- Integrity check: final output rows always equal CMS rows
- Dashboard with summary cards and the list of CMS transactions missing in Back Office, with evidence
- Excel report with colour-coded statuses, frozen headers and filters

### Excel sheets
RECONCILIATION_SUMMARY, CMS_MISSING_IN_BACKOFFICE, BACKOFFICE_ONLY,
MATCHED_TRANSACTIONS (optional), AMOUNT_MISMATCH, DATE_MISMATCH,
DUPLICATES, REVIEW_REQUIRED, FULL_RECONCILIATION

### Privacy
All processing happens in your browser. Files are never uploaded to any server.

### Notes
- Libraries (SheetJS, ExcelJS) are loaded from cdnjs, so an internet connection is required
- Large files (50k+ rows) can take about a minute to build the Excel report; use desktop Chrome or Edge

### Deploy
Drag the folder to Netlify Drop, or run `npx vercel --prod`. No build step is needed.

Design By DaudBD.com