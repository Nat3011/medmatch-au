# MedMatch AU

Synthetic-data-only proof of concept for Australian medication document inconsistency review.

**Owner:** Nat3011. **Stage:** Initial working browser demo; not a clinical system.

## Demo

Open `index.html` in a browser. It displays a fictional comparison of a hospital discharge summary and GP medication list with three deliberate discrepancies. Review controls work locally in the browser; the demo does not upload or interpret documents.

## What the intended application will do

1. Accept 2+ synthetic or appropriately de-identified medical documents.
2. Extract medication name, strength, administered dose, frequency, route, formulation, temporal status and evidence locations.
3. Normalise Australian brands and ingredients using appropriately licensed Australian Medicines Terminology (AMT), with TGA/ARTG and PBS as supplementary references.
4. Compare instructions using explicit rules informed by source dates and document types.
5. Surface evidence-linked discrepancies for human confirmation and export.

## Files

- `index.html`: self-contained interactive *synthetic* review demo.
- `BLUEPRINT.md`: proposed architecture, safety gates and implementation phases.
- `tests/expected_findings.json`: three expected findings and three important non-findings.

## Safety and next build

No patient records, model keys or secrets belong in this repository. Do not use this demo to make treatment decisions. The live upload/OCR/AI pipeline, approved medication terminology integration, authentication and secured hosting are **not yet implemented**.

Next step: Next.js frontend, FastAPI backend, PDF/OCR extraction, structured model extraction, deterministic discrepancy engine, and synthetic validation tests. Human clinical evaluation, privacy assessment, and Australian regulatory assessment are required before processing identifiable patient data.
