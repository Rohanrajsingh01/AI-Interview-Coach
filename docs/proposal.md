# Project Proposal — AI Video Interview Coach

> FYDP Group BSEF23-01 · BS Software Engineering (2023–2027) · University of the Punjab, Lahore
> Supervisor: Dr. Madiha Khalid

## Project Overview

The **AI Video Interview Coach** is a resume- and job-specific AI-powered mock video interview platform for students and fresh graduates. It simulates realistic mock interviews and produces **structured, multi-dimensional feedback** along three measurable axes: **content**, **voice / delivery**, and **body language**.

## Problem Statement

Most interview-preparation tools available to students fall into two categories:

- **Static question banks** (LeetCode-style). Good for technical drilling, but no practice for *delivery* or *non-verbal communication*, and no measurable per-criterion feedback.
- **Generic AI chatbots.** Free-form feedback, no resume awareness, no real interview structure, no rubric.

Neither produces structured, multi-dimensional, repeatable practice. Students repeat the same weaknesses because no one tells them precisely *which* one needs work.

## Target Users

- **Primary.** Undergraduate and graduate students in CS / SE programmes, particularly BS-SE 7th–8th semester students and fresh graduates (0–2 years experience) preparing for their first technical interviews.
- **Secondary.** Early-career candidates (1–3 years experience) preparing for a new role.
- **Geography (initial).** Pakistan. The product is language-agnostic in design so it can extend later.

## Project Objectives

- Resume-aware, role-specific mock interviews.
- Synchronised audio + video recording during the session.
- Three-dimension evaluation (content, voice, body language).
- Rubric-based, explainable feedback (not a single opaque number).
- Per-candidate history with a score-over-time view.
- Internal evaluation with ~50–80 short mock-interview recordings from consenting teammates and classmates (supervisor-approved).

## Scope

### In Scope

- Candidate account / profile.
- CV upload (PDF / DOCX) and CV parsing to structured fields (skills, education, experience).
- Target-role or pasted job-description intake.
- Matching candidate profile to ranked CS domains.
- Domain-tagged question bank with three difficulty levels (Foundational / Intermediate / Advanced).
- Preparatory material view (browse practice questions and model answers filtered by matched domains).
- Three-phase mock interview: **opening → core → closing** (domain-aware selection).
- Synchronised audio + video capture via browser `MediaRecorder` / `getUserMedia`.
- Speech-to-text (Whisper / faster-whisper, planned).
- Voice-delivery metrics: pace (WPM), filler-word count, pause ratio.
- Content scoring with rubric feedback (relevance, structure, technical correctness; STAR for behavioural questions).
- Body-language metrics from video frames: eye-contact percentage, posture-stability index.
- Combined per-session report and per-candidate history with a score-over-time chart.
- Local-first development; privacy-sensitive handling of CVs, audio, and video.

### Out of Scope

- Recruitment platforms, applicant tracking, hiring pipelines, automated employment / hiring decisions.
- HR management or candidate–employer matching.
- Submission of job applications on behalf of candidates.
- Personality, psychometric, or psychological assessment.
- Lie detection, deception analysis, or truthfulness scoring.
- Medical or mental-health assessment.
- Guaranteed prediction of interview success.
- Multi-language support beyond English (until a later milestone).
- Enterprise features: SSO, multi-tenant, RBAC.
- Native mobile apps (web-first; responsive web only).

## High-Level Workflow

```
CV / Job Role
    ↓
Resume Parsing + Role Matching
    ↓
Relevant CS Domains
    ↓
Practice Questions + Model Answers
    ↓
Mock Interview (Opening → Core → Closing)
    ↓
Synchronised Audio + Video Recording
    ↓
Content + Voice + Body-Language Evaluation
    ↓
Combined Session Report
    ↓
History (Score-Over-Time)
```

## Seven Planned AI Components

These are **logical specialised components** of the proposed system, not necessarily seven separate deployable microservices. Implementation will confirm whether they live as one backend with internal modules or as separate services.

1. **Resume & Role-Matching** — parses CV (PDF/DOCX), extracts a structured profile, ranks relevant CS domains using embeddings + cosine similarity.
2. **Preparatory Material** — surfaces practice questions, model answers, and explanations from the structured question bank.
3. **Interview Flow / Question-Selection** — composes the three-phase interview using fixed-rule sequencing over matched-domain questions.
4. **Content Scoring** — produces a 0–100 content score with per-criterion feedback (zero-shot LLM rubric prompt).
5. **Voice Delivery** — transcribes recorded audio (Whisper / faster-whisper) and extracts pace, filler-word count, and pause metrics (librosa and related).
6. **Body Language** — extracts eye-contact percentage, posture-stability, and observable visual cues from video frames (MediaPipe Face Mesh / Pose, OpenCV).
7. **Reporting** — combines per-dimension scores into a session-level report and persists the historical record.

## Non-Goals (Explicit)

- The product does **not** infer inner states (emotion, honesty, confidence, personality).
- It is **not** a recruitment, ATS, or hiring-decision tool.