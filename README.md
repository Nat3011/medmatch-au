# MedMatch AU — Regional medication document quality prototype

**Owner:** Nat3011. **Demo network:** 15 entirely fictional facilities across five Victorian regions.

## Open the website
If GitHub Pages is enabled: https://nat3011.github.io/medmatch-au/

## Current browser application

- Clean clinical landing page explaining the patient document journey.
- Document intake for 2–8 **synthetic** PDF, TXT, PNG or JPG records (up to 12 MB each), with a facility selector.
- Browser-side PDF text parsing using PDF.js and scanned-document/image OCR fallback using Tesseract.js. These libraries are loaded from CDNs; internet connectivity is required.
- Actual processing stages reflect ingestion, extraction, comparison and result preparation. Processing failures are reported, not disguised as success.
- Rule-based matching of a *limited demonstration vocabulary* of medicine names and brands, doses/units, frequency, route, status and potential omissions.
- Evidence linked to extracted document statements, reviewer actions (confirmed/dismissed/uncertain), JSON report export.
- Session-level dashboards showing counts of processed documents, detected flags and reviewed findings.
- Separate fictional regional dashboard with 15 mock facilities and **explicitly invented** historical KPI values.
- 20 fictional test cases in `tests/twenty_cases.json`.

### Try the upload functionality
1. Open **Document intake**.
2. Select a fictional facility and choose at least two **fictional** PDF/TXT/image records for one case.
3. Select **Extract & compare documents**. If OCR is needed, it will run in-browser when the library is available.
4. Follow the Processing page, then open **Clinical review** to view potential differences and original extracted statements.
5. Review and export the session report; view updates in **Quality analytics**.

For quick setup, choose a predefined example and run it using the same rule engine.

### Tested extraction behaviour
A structured-text smoke test found exactly three discrepancies from a paired fictional set: lisinopril active/ceased; levothyroxine 50 mcg/50 mg; metformin twice/three times daily. Amlodipine remained consistent. This is a developer smoke test, **not** clinical validation or an end-to-end scanned-PDF test.

## What's not implemented
- No production backend, database, secure user identity, or automated routing of real hospital messages.
- No LLM interpretation, clinical-context inference or certified medicine reconciliation.
- No live AMT/PBS/TGA API lookup. PBS is a subsidy listing, ARTG describes approved products, and AMT supports normalised identity; **none is a standalone patient-specific dosing standard**.
- No verified detection sensitivity, precision or clinical accuracy rate. Regional 92% score and facility metrics are synthetic illustration.
- Rules may miss entries in unusual layouts, falsely flag changes, or confuse dose strength with administered dose; OCR quality varies.

## Safety
The app is **for fictional/safely de-identified training documents only**. Never upload real identifiable health information to this public GitHub Pages demo. Extraction runs in the browser but third-party CDN libraries are fetched. The prototype cannot determine correct treatment or medication safety. Every finding requires qualified review. No uploaded document content is persisted in GitHub or a backend, and session metrics clear when the page reloads.

## Suggested real-world architecture
Private authenticated app; hardened document ingestion; encrypted storage with deletion policies; OCR and schema-validated multimodal model extraction; AMT terminology integration under NCTS terms; official PBS/TGA product lookups; chronological cross-document rules; evidence provenance; reviewer audit trails; security, privacy and TGA medical software regulatory assessment.

Static front end: `index.html`, `portal.css`, `portal.js`. Previous `app.js` and `styles.css` are retained for history but are no longer loaded.

