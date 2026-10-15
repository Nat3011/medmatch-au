# MedMatch AU — Version 2

A polished, mobile-responsive Australian medication-document consistency **synthetic demo**. Repository owner: **Nat3011**.

## Live site

If GitHub Pages is enabled (Settings → Pages → Deploy from a branch → main → /(root)):

https://nat3011.github.io/medmatch-au/

## Features

- Healthcare-themed landing page with custom vector graphics, four KPI cards and workflow infographic.
- Six navigation sections: Overview, Document workspace, Processing centre, Findings & review, Analytics dashboard and About & safety.
- Browser-based file selection and drag-and-drop staging. **Files are not read, transmitted, OCR-processed or analysed.**
- Explicitly simulated progress through intake, OCR, extraction, comparison and summary steps for the synthetic example case.
- Predefined discrepancy findings for apixaban dose, metformin XR frequency and ramipril status. Each finding displays the two source statements and suggested clinician verification steps.
- Clinician-review disposition buttons: Confirmed discrepancy, Dismissed and Uncertain. Review actions are stored in the current browser session only.
- Local download of a synthetic review summary; dashboard status reflects user review actions.
- Responsive UI in plain HTML, CSS and JavaScript; GitHub Pages compatible without a build step.

## How to test

1. Open the live site or open `index.html` locally.
2. Choose **Document workspace → Run synthetic example workflow**.
3. Watch the explicitly *illustrative* processing timeline, then open **Findings & review**.
4. Switch among the three findings, choose review statuses, and export review notes.
5. Open **Analytics dashboard** and confirm the reviewed count updates.
6. Optionally stage fictional files in the uploader and verify they are marked **Staged only · not processed**.

## Source data

See `samples/` for three fictional record examples in Markdown and `tests/expected_findings.json` for the intended findings and non-findings.

## Next implementation stage

Replace the simulated pipeline with a **real**, security-reviewed upload/OCR/structured extraction service and deterministic comparison engine. Proposed architecture: Next.js + FastAPI; Australian Medicines Terminology (subject to licensing) with TGA/ARTG and PBS as supplementary product reference context. Capture document evidence and date-specific status for every result.

## Safety notice

This is not a clinical device or clinical advice. No actual patient documents should be used. No OCR or LLM analysis currently occurs, and the statistics are synthetic-case indicators, not real usage analytics. Never use the demo to change medication. Clinical, privacy, security and regulatory evaluation must precede any patient-data deployment.
