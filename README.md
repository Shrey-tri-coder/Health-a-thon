# Healtheon

Clinician-facing consultation-readiness tool for oncologists (Health-a-thon 2026, Cancer Care · NCG). It gives a doctor a short, chronological, non-diagnostic brief of a patient's records before each consultation.

## Architecture
One central database per hospital, one backend, three apps (Patient, Staff, Doctor).
- Records are tagged by document type, date and time at upload (no AI sorting).
- AI (RAG) is used only to summarise a patient's stored records on request.
- Patient ID plus optional ABHA ID field. No Aadhaar data stored.

## Prototype status
`mvp/index.html` is a single-file clickable demo with fabricated data. It shows the patient symptom form, staff/lab upload, QR-style lookup, the three visit types (New, Follow-up, Hospital Transfer) and report search. The brief is rule-based; the LLM call is not wired in. Hospital-transfer history is simulated and stands in for ABDM exchange.

## Run
Open `mvp/index.html` in a browser.

## Planned stack (month build)
FastAPI + PostgreSQL, object storage for files, Tesseract OCR, embeddings + vector search for retrieval, one LLM API call for summarisation, React web app (html5-qrcode for scanning).

## Repo layout
```
mvp/index.html
docs/supporting_doc.md
docs/video_script.md
```

## Scope
Not diagnosis, treatment advice, risk scoring or data interpretation. A human clinician reads the brief and decides.
