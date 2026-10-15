# MedMatch AU blueprint

Owner: Nat3011. Initial scope: synthetic-data-only document consistency review.

## Pipeline
1. Upload two or more PDF or image documents.
2. Parse text and use OCR for scanned documents, retaining source references.
3. Extract medicine, ingredient, brand, form, strength, dose, route, frequency, status and document date into validated structured records.
4. Normalise identity using Australian Medicines Terminology where access allows, and link to TGA/ARTG and PBS reference data.
5. Compare records with deterministic rules, including chronological context and brand aliases.
6. Present differences with source evidence; user can confirm, dismiss or mark uncertain.
7. Export a review report.

## Stack
Next.js frontend, Python FastAPI backend, structured AI extraction, OCR fallback, rules engine. Secure deployment with server-side credentials.

## Test cases
Apixaban documented at two different doses; metformin XR at two frequencies; ramipril listed ceased versus current. Amlodipine is consistent. Eliquis and apixaban refer to the same active ingredient. Earlier pharmacy dispensing is historical evidence, not definitive proof of current treatment.

## Safeguards
This prototype is not for clinical decisions. Use fictional documents only until clinical, privacy, security and Australian regulatory reviews are complete. Do not store personal medical data or credentials in GitHub.
