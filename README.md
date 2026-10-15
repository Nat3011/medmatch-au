# MedMatch AU — Regional medication document intelligence (prototype V4)

**GitHub owner:** Nat3011

## Website
https://nat3011.github.io/medmatch-au/

## Redesigned user journey
1. **Home:** welcoming healthcare landing page, concise infographics and browser-session stats.
2. **Scan documents:** drag in one or more fictional PDFs, images or TXT records; no manual hospital or category dropdowns.
3. **Automatic recognition:** extract text and infer the hospital (for the 15 known fictional facility names), category, and document date from content. Unrecognised sources are labelled as such rather than invented.
4. **Processing:** show genuine parsing/OCR and heuristic checking stages, including failures.
5. **Review centre:** view evidence-linked potential inconsistencies, reviewer status, and a downloadable JSON report.
6. **Hospital leaderboard:** rank 15 invented Victorian facilities on a **transparent simulated** quality score. Weights: documentation completeness 40%, review closure 35%, workflow timeliness 25%. The historical inputs are fictitious.
7. **Regional analytics:** show actual browser-session counts separately from simulated regional quality measurements.
8. **Test case library:** select from **50 paired scenarios** stored in `tests/fifty_cases.json`; each contains two fictional documents with facility headers, dates, patient identifiers, and a separate expected-findings field.

## Run and test
- Open the GitHub Pages site, or serve the repository root through `python3 -m http.server 8000`.
- Choose **Test case library**, select a case and click **Process these documents**.
- Watch automatic facility and document-type recognition; view extracted medication mismatches and inspect review recommendations.
- In **Scan documents**, upload the paired fictional PDF files from the companion ZIP or upload your own safely de-identified test fixtures.
- Note: PDFs use PDF.js and scanned documents use Tesseract.js loaded from CDNs. Offline mode is not supported.
- All application state lives in the browser session and is lost on reload. There is no database or background hospital feed.

## Important limitations
**This is not a production clinical model.** Detection is heuristic/rule-based with a small medicine vocabulary, not a trained LLM doing clinical reasoning. It can miss dose formulation details, allergy interpretation, combination therapies, subtle chronology and numerous edge cases. The 50-case answer key represents testing expectations rather than measured performance.

Australian Medicines Terminology, PBS and TGA are explained on the About page but have **not been integrated as live data validation services**. PBS subsidy data and TGA registration alone cannot establish a correct patient-specific prescription.

Do not upload identifiable patient records or interpret results as clinical advice. Browser OCR/PDF libraries come from third-party CDNs. Proper privacy, cybersecurity, regulatory, terminology licensing and clinician validation are needed before real use.

## Files
- `index.html`: current UI.
- `command.css`: current responsive layout and dashboards.
- `command.js`: automatic classification, in-browser extraction/comparison, session metrics and review workflow.
- `tests/fifty_cases.json`: 50 synthetic cases with 100 text document fixtures.
- `tests/twenty_cases.json`: legacy 20-case benchmark.
- A companion ZIP downloadable from the project conversation contains **100 individual PDFs**, an answer key and case metadata.
- Previous `portal.js`, `portal.css`, `app.js`, `styles.css` are historical and not loaded.

## Recommended next phase
Create a secured backend with OCR quality evaluation, model-based structured document classification/extraction, terminology services (AMT), source provenance, identity verification, audit logs, versioned medication reconciliation, test harness across the 50 cases, and expert-reviewed sensitivity/precision measurement. The hospital score should only use agreed, validated quality metrics and appropriate case-mix adjustments before it is treated as comparative performance evidence.
