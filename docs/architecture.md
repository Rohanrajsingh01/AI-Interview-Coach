# Architecture

> High-level proposed architecture for the AI Video Interview Coach. Implementation-specific design decisions (e.g. whether the seven components are deployed as one service or several) are deferred until implementation. This document is updated only when those decisions are actually made.

## Layers

```
Frontend (React + TypeScript + Tailwind, planned)
        ↕
Backend / API (FastAPI, Python, planned)
        ↓
Specialised AI Components (seven logical components)
        ↓
Storage (PostgreSQL + local / S3-compatible media storage)
```

The seven AI components are **logical specialised components**, not necessarily seven separate deployable microservices. They will live inside the backend as discrete modules calling shared utilities until implementation proves otherwise.

## Specialised Components (Logical)

| # | Component | Responsibility |
| --- | --- | --- |
| 1 | Resume & Role-Matching | Parse CV, extract profile, rank relevant CS domains. |
| 2 | Preparatory Material | Surface practice questions and model answers. |
| 3 | Interview Flow / Question-Selection | Compose three-phase interview with domain-aware selection. |
| 4 | Content Scoring | Rubric-based content score (0–100) with feedback. |
| 5 | Voice Delivery | Transcription + pace / filler / pause metrics. |
| 6 | Body Language | Eye-contact %, posture stability, observable visual cues. |
| 7 | Reporting | Combined session report + historical record. |

## Recording Service

The browser captures synchronised audio + video via the **MediaRecorder API** and `getUserMedia`. The recording produces files usable by downstream analysis (transcription, voice metrics, body-language metrics).

## Data

- **Structured data.** PostgreSQL — candidates, interview sessions, question bank, per-component scores, session history.
- **Media.** Local storage by default; S3-compatible storage is a later option.

## Constraints

- **Local-first.** No required cloud account to run the project locally.
- **No participant data in Git.** Personal CVs, audio, video, faces, and transcripts tied to individuals are **never** committed. Public validation datasets (e.g. CMU-MOSEI, CMU-MOSI, POM, RAVDESS) are referenced by name and license only.

## Open Decisions (Tracked, Not Yet Made)

- Whether the backend is a single deployable service or split across services.
- Whether the LLM access is API-based or local.
- Whether media storage remains local-only or moves to S3-compatible storage.
- Whether a database other than PostgreSQL is needed for any workload.