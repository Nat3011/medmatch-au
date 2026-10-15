# 20 fictional paired medical-document scenarios

**Synthetic test fixtures — NOT real medical records. Not medical advice.**

Each scenario has a Source A and Source B record. Separate PDF versions of all 40 records are provided in the companion downloadable test pack.

## C01 — Discontinued medicine remains active

### Source document A (fictional)
Patient: Alex Example (fictional)  
Document date: 14 October 2026

**Recorded medication:** Lisinopril 10 mg orally once daily — ACTIVE

### Source document B (fictional)
Patient: Alex Example (fictional)  
Document date: 15 October 2026

**Recorded medication:** Lisinopril 10 mg orally once daily — CEASED after discharge review

**Expected finding:** Flag for review — status_conflict  
**Reviewer context:** Flag status conflict; confirm current plan  
**Caution:** Older GP record may be stale

---

## C02 — Microgram versus milligram error

### Source document A (fictional)
Patient: Alex Example (fictional)  
Document date: 14 October 2026

**Recorded medication:** Levothyroxine 50 micrograms orally every morning

### Source document B (fictional)
Patient: Alex Example (fictional)  
Document date: 15 October 2026

**Recorded medication:** Levothyroxine 50 mg orally every morning

**Expected finding:** Flag for review — unit_mismatch  
**Reviewer context:** Urgent verification of 1000-fold unit discrepancy  
**Caution:** Do not infer intended instruction

---

## C03 — Frequency differs

### Source document A (fictional)
Patient: Alex Example (fictional)  
Document date: 14 October 2026

**Recorded medication:** Metformin 500 mg orally twice daily

### Source document B (fictional)
Patient: Alex Example (fictional)  
Document date: 15 October 2026

**Recorded medication:** Metformin 500 mg orally three times daily

**Expected finding:** Flag for review — frequency_mismatch  
**Reviewer context:** Verify intended frequency  
**Caution:** Document chronology matters

---

## C04 — Combination inhaler ingredient overlap

### Source document A (fictional)
Patient: Alex Example (fictional)  
Document date: 14 October 2026

**Recorded medication:** Symbicort budesonide/formoterol 200/6 micrograms, 2 inhalations twice daily

### Source document B (fictional)
Patient: Alex Example (fictional)  
Document date: 15 October 2026

**Recorded medication:** Budesonide 200 micrograms, 2 inhalations twice daily; also active

**Expected finding:** Flag for review — ingredient_overlap  
**Reviewer context:** Review possible overlapping budesonide exposure  
**Caution:** Different products: Symbicort also contains formoterol

---

## C05 — Different tablet strength

### Source document A (fictional)
Patient: Alex Example (fictional)  
Document date: 14 October 2026

**Recorded medication:** Amlodipine 5 mg tablet, one daily

### Source document B (fictional)
Patient: Alex Example (fictional)  
Document date: 15 October 2026

**Recorded medication:** Amlodipine 10 mg tablet, one daily

**Expected finding:** Flag for review — strength_mismatch  
**Reviewer context:** Check current strength  
**Caution:** May be legitimate titration

---

## C06 — Route differs

### Source document A (fictional)
Patient: Alex Example (fictional)  
Document date: 14 October 2026

**Recorded medication:** Ondansetron 4 mg orally every 8 hours as required

### Source document B (fictional)
Patient: Alex Example (fictional)  
Document date: 15 October 2026

**Recorded medication:** Ondansetron 4 mg intravenously every 8 hours as required

**Expected finding:** Flag for review — route_mismatch  
**Reviewer context:** Verify route and setting  
**Caution:** Inpatient and outpatient contexts differ

---

## C07 — Immediate versus modified release

### Source document A (fictional)
Patient: Alex Example (fictional)  
Document date: 14 October 2026

**Recorded medication:** Metoprolol tartrate 50 mg twice daily

### Source document B (fictional)
Patient: Alex Example (fictional)  
Document date: 15 October 2026

**Recorded medication:** Metoprolol succinate modified-release 50 mg once daily

**Expected finding:** Flag for review — formulation_mismatch  
**Reviewer context:** Check formulation and frequency  
**Caution:** Not interchangeable by name alone

---

## C08 — Anticoagulant missing from second list

### Source document A (fictional)
Patient: Alex Example (fictional)  
Document date: 14 October 2026

**Recorded medication:** Apixaban 5 mg twice daily, current

### Source document B (fictional)
Patient: Alex Example (fictional)  
Document date: 15 October 2026

**Recorded medication:** No apixaban recorded in the current list

**Expected finding:** Flag for review — omission  
**Reviewer context:** Verify apparent omission  
**Caution:** Missing entry does not prove cessation

---

## C09 — Allergy and medication record conflict

### Source document A (fictional)
Patient: Alex Example (fictional)  
Document date: 14 October 2026

**Recorded medication:** Allergies: amoxicillin — rash documented

### Source document B (fictional)
Patient: Alex Example (fictional)  
Document date: 15 October 2026

**Recorded medication:** Amoxicillin 500 mg orally three times daily active; allergy section blank

**Expected finding:** Flag for review — allergy_conflict  
**Reviewer context:** Escalate potential allergy record conflict for review  
**Caution:** Clinical history requires verification

---

## C10 — PRN versus scheduled

### Source document A (fictional)
Patient: Alex Example (fictional)  
Document date: 14 October 2026

**Recorded medication:** Salbutamol 100 micrograms, 2 puffs as needed

### Source document B (fictional)
Patient: Alex Example (fictional)  
Document date: 15 October 2026

**Recorded medication:** Salbutamol 100 micrograms, 2 puffs four times daily

**Expected finding:** Flag for review — prn_vs_scheduled  
**Reviewer context:** Review intended instructions  
**Caution:** Plans may be context-specific

---

## C11 — Brand and generic duplicate

### Source document A (fictional)
Patient: Alex Example (fictional)  
Document date: 14 October 2026

**Recorded medication:** Panadol (paracetamol) 500 mg, 2 tablets as needed

### Source document B (fictional)
Patient: Alex Example (fictional)  
Document date: 15 October 2026

**Recorded medication:** Paracetamol 500 mg, 2 tablets as needed listed separately

**Expected finding:** Flag for review — brand_generic_duplicate  
**Reviewer context:** Review whether this is one medicine recorded twice  
**Caution:** Entries do not prove both were taken

---

## C12 — Insulin dose unit confusion

### Source document A (fictional)
Patient: Alex Example (fictional)  
Document date: 14 October 2026

**Recorded medication:** Insulin glargine 20 units subcutaneously each evening

### Source document B (fictional)
Patient: Alex Example (fictional)  
Document date: 15 October 2026

**Recorded medication:** Insulin glargine 20 mL subcutaneously each evening

**Expected finding:** Flag for review — dose_unit_mismatch  
**Reviewer context:** Urgently verify incompatible dose units  
**Caution:** Never infer correction

---

## C13 — Duration conflict

### Source document A (fictional)
Patient: Alex Example (fictional)  
Document date: 14 October 2026

**Recorded medication:** Cephalexin 500 mg four times daily for 5 days

### Source document B (fictional)
Patient: Alex Example (fictional)  
Document date: 15 October 2026

**Recorded medication:** Cephalexin 500 mg four times daily for 10 days

**Expected finding:** Flag for review — duration_conflict  
**Reviewer context:** Verify intended course length  
**Caution:** Later note may supersede earlier note

---

## C14 — Weekly versus daily

### Source document A (fictional)
Patient: Alex Example (fictional)  
Document date: 14 October 2026

**Recorded medication:** Alendronate 70 mg every Monday

### Source document B (fictional)
Patient: Alex Example (fictional)  
Document date: 15 October 2026

**Recorded medication:** Alendronate 70 mg every day

**Expected finding:** Flag for review — schedule_mismatch  
**Reviewer context:** Urgently review frequency  
**Caution:** Weekly and daily schedules differ greatly

---

## C15 — Stop date disagreement

### Source document A (fictional)
Patient: Alex Example (fictional)  
Document date: 14 October 2026

**Recorded medication:** Prednisolone 5 mg daily, stop 18 October 2026

### Source document B (fictional)
Patient: Alex Example (fictional)  
Document date: 15 October 2026

**Recorded medication:** Prednisolone 5 mg daily, stop 25 October 2026

**Expected finding:** Flag for review — stop_date_conflict  
**Reviewer context:** Verify whether treatment was intentionally extended  
**Caution:** Date and rationale matter

---

## C16 — Dose missing from one record

### Source document A (fictional)
Patient: Alex Example (fictional)  
Document date: 14 October 2026

**Recorded medication:** Warfarin: according to attached anticoagulation schedule

### Source document B (fictional)
Patient: Alex Example (fictional)  
Document date: 15 October 2026

**Recorded medication:** Warfarin every evening; no dose or attached schedule

**Expected finding:** Flag for review — missing_dose  
**Reviewer context:** Request authoritative dosing schedule  
**Caution:** Never fabricate warfarin dose

---

## C17 — Brand equivalence non-finding

### Source document A (fictional)
Patient: Alex Example (fictional)  
Document date: 14 October 2026

**Recorded medication:** Eliquis 5 mg twice daily

### Source document B (fictional)
Patient: Alex Example (fictional)  
Document date: 15 October 2026

**Recorded medication:** Apixaban 5 mg twice daily

**Expected finding:** Do not flag as unresolved conflict — brand_alias  
**Reviewer context:** Do not flag dose mismatch  
**Caution:** Eliquis is an apixaban brand

---

## C18 — Historical titration non-finding

### Source document A (fictional)
Patient: Alex Example (fictional)  
Document date: 14 October 2026

**Recorded medication:** Ramipril 2.5 mg daily on 1 October 2026

### Source document B (fictional)
Patient: Alex Example (fictional)  
Document date: 15 October 2026

**Recorded medication:** Ramipril 5 mg daily; documented cardiology titration on 14 October 2026

**Expected finding:** Do not flag as unresolved conflict — chronology_context  
**Reviewer context:** Mark as potentially resolved historical change  
**Caution:** Chronology explains dose change

---

## C19 — Timing difference

### Source document A (fictional)
Patient: Alex Example (fictional)  
Document date: 14 October 2026

**Recorded medication:** Atorvastatin 40 mg every morning

### Source document B (fictional)
Patient: Alex Example (fictional)  
Document date: 15 October 2026

**Recorded medication:** Atorvastatin 40 mg every evening

**Expected finding:** Flag for review — timing_mismatch  
**Reviewer context:** Clarify differing instructions  
**Caution:** Clinical significance is not established

---

## C20 — Tablet fraction different

### Source document A (fictional)
Patient: Alex Example (fictional)  
Document date: 14 October 2026

**Recorded medication:** Furosemide 40 mg tablet: take half each morning

### Source document B (fictional)
Patient: Alex Example (fictional)  
Document date: 15 October 2026

**Recorded medication:** Furosemide 40 mg tablet: take one each morning

**Expected finding:** Flag for review — tablet_count_mismatch  
**Reviewer context:** Compare administered doses 20 mg and 40 mg  
**Caution:** Strength is not the same as administered dose

---

