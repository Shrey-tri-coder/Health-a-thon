# Healtheon: supporting document

## Problem
Oncologists lose time before consultations assembling patient history from scattered records. Sources cited in the deck: Thieme (2023) on EHR burden in head and neck cancer care; DeepScribe on pre-visit preparation; Sylvester Cancer Center via ASCO on unreported symptoms; NCG EMR initiative, Bull WHO 2025 (DOI 10.2471/BLT.24.292230).

## Solution
Central database, backend, and three apps (Patient, Staff, Doctor). Documents are tagged by type, date and time at upload. The doctor scans a patient QR code and picks a visit type: New Patient (lab list), Follow-up (one-page brief since last visit) or Hospital Transfer (full chronological history).

## Components
- **Database:** per-hospital, patient folder holding symptoms, reports, scans, transcripts. Unique patient ID, optional ABHA ID, no Aadhaar.
- **Upload system:** choose type, enter date and time, file routes to the folder. Bluetooth scanner uploads for paper records.
- **RAG summarisation:** OCR on scanned files, retrieval by patient ID, LLM summary only on request.
- **Patient app:** appointments, records, symptom and missed-medication form in the preferred language, reminders.
- **Doctor app:** QR scan or ID entry, visit type, brief, report search.
- **Staff app:** department upload streams and session timings.

## One-month plan
- Week 1: schema, upload, patient form
- Week 2: doctor lookup, visit-type screen, new-patient view
- Week 3: OCR and RAG brief, seeded transfer data
- Week 4: three demo patient stories, testing, video

## Safety and scope
Assistive only. The brief states facts and counts, with no diagnosis, treatment recommendation, risk scoring or interpretation. A clinician stays in control.

## Limits
Prototype uses fabricated data. ABDM/ABHA exchange is simulated; real integration requires certification and belongs to an adopting institution. OCR accuracy on poor scans, language coverage of the symptom form and the data-protection setup (DPDP Act) need work before any pilot.
