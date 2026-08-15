# Product Backlog

The single source of truth for FYDP D1 product planning.

## Status Legend

| Status | Meaning |
| --- | --- |
| **Backlog** | Not yet started; awaits grooming. |
| **Ready** | Meets the Definition of Ready; can be pulled into a sprint. |
| **In Progress** | Active work in the current sprint. |
| **Completed** | Meets the Definition of Done and is merged. |
| **Blocked** | Cannot progress; see comments. |

## Priority Legend

| Code | Meaning |
| --- | --- |
| **P0** | Critical — blocks core demo / supervisor review. |
| **P1** | High — needed for a complete end-to-end demo. |
| **P2** | Medium — important for final quality. |
| **P3** | Low — cut first if scope is at risk. |

## Definition of Ready

A story is **Ready** when *all* of the following are true:

1. User value is clear (written as a user story).
2. Scope is clear.
3. Acceptance criteria are testable.
4. Priority is assigned (P0–P3).
5. Dependencies are identified by story ID.
6. Owner is assigned.
7. Story fits within a single 2-week sprint.
8. Any required research or design decisions are resolved or have a documented plan.

## Epics

| ID | Epic | Priority | Lead | Depends On |
| --- | --- | --- | --- | --- |
| E1 | Candidate Profile & Resume Intake | P0 | Komal Zahid | — |
| E2 | Preparatory Material | P1 | Komal Zahid | E1 |
| E3 | Mock Interview Engine | P0 | Rohan Raj Singh | E1, E2 |
| E4 | Recording Pipeline | P0 | Rohan Raj Singh | E3 |
| E5 | Multi-Dimensional Evaluation | P0 | Komal (content), Sofia (voice), Memoona (body) | E3, E4 |
| E6 | Reporting & Session History | P1 | Rohan Raj Singh | E5 |
| E7 | Cross-Cutting Foundations | P1 | Rohan Raj Singh | All |

---

## User Stories

### E1 — Candidate Profile & Resume Intake

#### S-001 — Candidate Account
- **As a** candidate, **I want to** register an account **so that** I can save my profile and interview history.
- **Priority:** P0
- **Acceptance criteria**
  - User can sign up with email + password.
  - User can log in and log out.
  - Session is persisted across page refreshes.
- **Dependencies:** —
- **Owner:** Rohan Raj Singh
- **Planned sprint:** Sprint 3
- **Status:** Backlog

#### S-002 — CV Upload
- **As a** candidate, **I want to** upload my CV (PDF or DOCX) **so that** the system can extract my skills and background.
- **Priority:** P0
- **Acceptance criteria**
  - User can select a PDF or DOCX file from the file picker.
  - System rejects unsupported file types with a clear error.
  - Upload progress is shown.
  - Extracted text and structured fields are stored.
  - Errors during parsing are shown to the user.
- **Dependencies:** S-001
- **Owner:** Komal Zahid
- **Planned sprint:** Sprint 4
- **Status:** Backlog

#### S-003 — Target Role / Job Description Intake
- **As a** candidate, **I want to** enter a target role or paste a job description **so that** the system can match me against relevant domains.
- **Priority:** P0
- **Acceptance criteria**
  - User can select a predefined role from a dropdown.
  - User can paste a free-form job description.
  - Selected/pasted input is stored with the candidate profile.
- **Dependencies:** S-001
- **Owner:** Komal Zahid
- **Planned sprint:** Sprint 4
- **Status:** Backlog

#### S-004 — CV Parsing
- **As a** candidate, **I want** the system to extract my skills, education, and experience from my CV **so that** my profile is structured.
- **Priority:** P0
- **Acceptance criteria**
  - CV text is extracted (PDF/DOCX).
  - Structured fields are produced (skills list, education entries, experience entries).
  - Extraction failures produce a clear, non-blocking error.
- **Dependencies:** S-002
- **Owner:** Komal Zahid
- **Planned sprint:** Sprint 5
- **Status:** Backlog

#### S-005 — Domain Matching & Ranking
- **As a** candidate, **I want to** see which CS domains are most relevant to my CV and target role **so that** I know where to focus my preparation.
- **Priority:** P0
- **Acceptance criteria**
  - System returns a ranked list of relevant CS domains.
  - Each domain has a relevance score (0–1).
  - The ranked list is shown on the candidate dashboard.
- **Dependencies:** S-002, S-003
- **Owner:** Komal Zahid
- **Planned sprint:** Sprint 6
- **Status:** Backlog

---

### E2 — Preparatory Material

#### S-006 — Browse Practice Questions
- **As a** candidate, **I want to** browse practice questions filtered by domain **so that** I can prepare for matched domains.
- **Priority:** P1
- **Acceptance criteria**
  - Question bank is browsable by domain and difficulty.
  - Question list shows question text, difficulty, and tags.
  - Empty-state behaviour is graceful.
- **Dependencies:** S-005
- **Owner:** Komal Zahid
- **Planned sprint:** Sprint 7
- **Status:** Backlog

#### S-007 — Model Answer View
- **As a** candidate, **I want to** read model answers and explanations for a practice question **so that** I understand what a strong answer looks like.
- **Priority:** P1
- **Acceptance criteria**
  - Each question has a model-answer and explanation view.
  - Expected concepts are listed.
- **Dependencies:** S-006
- **Owner:** Komal Zahid
- **Planned sprint:** Sprint 7
- **Status:** Backlog

#### S-008 — Mark Practice Question Done
- **As a** candidate, **I want to** mark a practice question as "done" **so that** I can track which questions I have already covered.
- **Priority:** P2
- **Acceptance criteria**
  - User can mark a question as done from the question detail view.
  - Marked-done state persists across sessions.
- **Dependencies:** S-006
- **Owner:** Rohan Raj Singh
- **Planned sprint:** Sprint 8
- **Status:** Backlog

---

### E3 — Mock Interview Engine

#### S-009 — Start a Mock Interview
- **As a** candidate, **I want to** start a mock interview **so that** I can practise answering real-style questions.
- **Priority:** P0
- **Acceptance criteria**
  - User can start a new mock interview from the dashboard.
  - The session is created with status "in progress".
  - The first question is shown.
- **Dependencies:** S-005
- **Owner:** Rohan Raj Singh
- **Planned sprint:** Sprint 8
- **Status:** Backlog

#### S-010 — Three-Phase Interview Flow
- **As a** candidate, **I want** the mock interview to follow opening → core → closing phases **so that** it feels like a real interview.
- **Priority:** P0
- **Acceptance criteria**
  - Phase indicator is visible.
  - Phase transition happens after the configured number of questions.
- **Dependencies:** S-009
- **Owner:** Rohan Raj Singh
- **Planned sprint:** Sprint 8
- **Status:** Backlog

#### S-011 — Domain-Aware Question Selection
- **As a** candidate, **I want** questions to be selected from my matched domains **so that** the interview is personalised.
- **Priority:** P0
- **Acceptance criteria**
  - Core-phase questions are drawn from the candidate's matched domains.
  - Question selection is logged for traceability.
- **Dependencies:** S-009
- **Owner:** Rohan Raj Singh
- **Planned sprint:** Sprint 8
- **Status:** Backlog

#### S-012 — End / Cancel a Session Early
- **As a** candidate, **I want to** end or cancel a mock interview early **so that** I am not forced to complete a session.
- **Priority:** P1
- **Acceptance criteria**
  - User can end a session from any phase.
  - Partial session results are still saved (best effort).
- **Dependencies:** S-009
- **Owner:** Rohan Raj Singh
- **Planned sprint:** Sprint 9
- **Status:** Backlog

---

### E4 — Recording Pipeline

#### S-013 — Camera & Microphone Permission
- **As a** candidate, **I want** the system to request camera and microphone access **so that** the interview can be recorded.
- **Priority:** P0
- **Acceptance criteria**
  - Browser permission prompt is shown.
  - User is told why access is requested.
  - Permission denial produces a clear error.
- **Dependencies:** S-009
- **Owner:** Rohan Raj Singh
- **Planned sprint:** Sprint 9
- **Status:** Backlog

#### S-014 — Synchronised Audio + Video Recording
- **As a** candidate, **I want** my audio and video to be recorded together for each answer **so that** all three evaluation dimensions operate on the same session.
- **Priority:** P0
- **Acceptance criteria**
  - Recording starts when the user presses record.
  - Recording stops cleanly at the end of an answer.
  - Audio and video files share a common session id.
- **Dependencies:** S-013
- **Owner:** Rohan Raj Singh
- **Planned sprint:** Sprint 9
- **Status:** Backlog

#### S-015 — Secure Local-First Storage of Recordings
- **As a** candidate, **I want** my recordings to be stored securely **so that** they are available for evaluation but not exposed to other users.
- **Priority:** P0
- **Acceptance criteria**
  - Recordings are stored locally by default.
  - Only the candidate and the evaluation pipeline can access them.
  - No recording URL is publicly guessable.
- **Dependencies:** S-014
- **Owner:** Rohan Raj Singh
- **Planned sprint:** Sprint 10
- **Status:** Backlog

#### S-016 — Recording Indicator
- **As a** candidate, **I want to** see a recording indicator while my answer is being recorded **so that** I know the system is capturing.
- **Priority:** P1
- **Acceptance criteria**
  - A visible recording indicator (timer / dot) is shown during recording.
  - The indicator disappears when recording stops.
- **Dependencies:** S-014
- **Owner:** Rohan Raj Singh
- **Planned sprint:** Sprint 10
- **Status:** Backlog

---

### E5 — Multi-Dimensional Evaluation

#### S-017 — Automatic Transcription
- **As a** candidate, **I want** my answers to be transcribed automatically **so that** the content and voice analyses can read them.
- **Priority:** P0
- **Acceptance criteria**
  - Audio is transcribed using Whisper / faster-whisper.
  - Transcript includes timestamps per segment.
  - Transcription failures are logged and surfaced.
- **Dependencies:** S-014
- **Owner:** Sofia Jameel
- **Planned sprint:** Sprint 11
- **Status:** Backlog

#### S-018 — Content Score
- **As a** candidate, **I want** my answer to receive a content score (0–100) **so that** I can see how well I answered.
- **Priority:** P0
- **Acceptance criteria**
  - Content score is computed from the transcript and the question rubric.
  - Per-criterion feedback is produced (relevance, structure, technical correctness; STAR for behavioural).
  - Score and feedback appear in the session report.
- **Dependencies:** S-017, S-009
- **Owner:** Komal Zahid
- **Planned sprint:** Sprint 12
- **Status:** Backlog

#### S-019 — Voice-Delivery Score
- **As a** candidate, **I want** my answer to receive a voice-delivery score (0–100) **so that** I can see how my pace and fillers affected my delivery.
- **Priority:** P0
- **Acceptance criteria**
  - Voice-delivery score is computed (pace, filler-word count, pause ratio).
  - Per-metric breakdown is shown in the report.
- **Dependencies:** S-017
- **Owner:** Sofia Jameel
- **Planned sprint:** Sprint 12
- **Status:** Backlog

#### S-020 — Body-Language Score
- **As a** candidate, **I want** my answer to receive a body-language score (0–100) **so that** I can see how my on-camera behaviour was perceived.
- **Priority:** P0
- **Acceptance criteria**
  - Eye-contact percentage is computed from video frames.
  - Posture-stability index is computed from video frames.
  - Body-language score is shown with per-metric breakdown.
  - No inference of inner states (confidence, honesty, personality).
- **Dependencies:** S-014
- **Owner:** Memoona Kaleem
- **Planned sprint:** Sprint 12
- **Status:** Backlog

#### S-021 — Per-Criterion Feedback
- **As a** candidate, **I want** each rubric criterion to have its own feedback sentence **so that** I know what to improve.
- **Priority:** P1
- **Acceptance criteria**
  - For each score, at least one actionable feedback sentence is provided.
- **Dependencies:** S-018, S-019, S-020
- **Owner:** Dimension leads
- **Planned sprint:** Sprint 13
- **Status:** Backlog

#### S-022 — Filler Words Highlighted in Transcript
- **As a** candidate, **I want** my filler words to be highlighted in context **so that** I can reduce them in future interviews.
- **Priority:** P1
- **Acceptance criteria**
  - Filler words are highlighted in the transcript view.
  - A total filler count is reported.
- **Dependencies:** S-019
- **Owner:** Sofia Jameel
- **Planned sprint:** Sprint 13
- **Status:** Backlog

#### S-023 — Eye-Contact Timeline
- **As a** candidate, **I want** my eye-contact timeline to be shown **so that** I can see where I looked away during the answer.
- **Priority:** P2
- **Acceptance criteria**
  - Per-second eye-contact percentage is shown.
  - Total eye-contact percentage is reported.
- **Dependencies:** S-020
- **Owner:** Memoona Kaleem
- **Planned sprint:** Sprint 13
- **Status:** Backlog

#### S-024 — Posture Timeline
- **As a** candidate, **I want** my posture timeline to be shown **so that** I can see when my posture changed.
- **Priority:** P2
- **Acceptance criteria**
  - Per-second posture stability is shown.
  - Total posture-stability index is reported.
- **Dependencies:** S-020
- **Owner:** Memoona Kaleem
- **Planned sprint:** Sprint 14
- **Status:** Backlog

---

### E6 — Reporting & Session History

#### S-025 — Combined Session Report
- **As a** candidate, **I want to** see a combined session report after the interview **so that** I understand my overall performance.
- **Priority:** P0
- **Acceptance criteria**
  - Report shows content, voice-delivery, and body-language scores.
  - Per-dimension feedback is included.
  - Report is reachable from the session detail page.
- **Dependencies:** S-018, S-019, S-020
- **Owner:** Rohan Raj Singh
- **Planned sprint:** Sprint 13
- **Status:** Backlog

#### S-026 — Past Sessions List
- **As a** candidate, **I want to** see my past sessions **so that** I can track my progress over time.
- **Priority:** P1
- **Acceptance criteria**
  - Past sessions list is shown on the dashboard.
  - Each session has timestamp, overall score, and domains covered.
- **Dependencies:** S-025
- **Owner:** Rohan Raj Singh
- **Planned sprint:** Sprint 14
- **Status:** Backlog

#### S-027 — Score-Over-Time Chart
- **As a** candidate, **I want** a score-over-time chart **so that** I can see my improvement visually.
- **Priority:** P1
- **Acceptance criteria**
  - A bar chart shows overall session scores over time.
  - Empty-history state is graceful.
- **Dependencies:** S-026
- **Owner:** Rohan Raj Singh
- **Planned sprint:** Sprint 14
- **Status:** Backlog

---

### E7 — Cross-Cutting Foundations

#### S-028 — Documented Backend API Contract
- **As a** developer, **I want** a documented backend API contract **so that** the frontend and AI modules can integrate consistently.
- **Priority:** P1
- **Acceptance criteria**
  - OpenAPI (or equivalent) schema is checked in.
  - Endpoints cover: auth, resume upload, role/JD intake, interview lifecycle, recordings, evaluations, history.
- **Dependencies:** —
- **Owner:** Rohan Raj Singh
- **Planned sprint:** Sprint 5
- **Status:** Backlog

#### S-029 — Environment Variable Template
- **As a** developer, **I want** environment-variable templates **so that** local setup is consistent across the team.
- **Priority:** P1
- **Acceptance criteria**
  - `.env.example` lists every variable the backend needs.
  - Local `.env` is git-ignored.
- **Dependencies:** —
- **Owner:** Rohan Raj Singh
- **Planned sprint:** Sprint 1
- **Status:** Backlog
- **Notes:** A future revision of `.env.example` will follow a technology-stack decision.

#### S-030 — CI Pipeline
- **As a** developer, **I want** a CI pipeline **so that** linting and tests run on every push.
- **Priority:** P2
- **Acceptance criteria**
  - Workflow runs on PR and main pushes.
  - Frontend lint, backend lint, backend tests run.
- **Dependencies:** S-028
- **Owner:** Rohan Raj Singh
- **Planned sprint:** Sprint 7
- **Status:** Backlog

#### S-031 — Question-Bank Schema
- **As the** team, **I want** a shared question-bank schema **so that** questions from different domains are stored consistently.
- **Priority:** P1
- **Acceptance criteria**
  - Schema documents: Question ID, Domain, Category, Difficulty, Question, Model Answer, Explanation, Expected Concepts, Tags.
  - Initial seed data is committed as JSON.
- **Dependencies:** —
- **Owner:** Komal Zahid
- **Planned sprint:** Sprint 6
- **Status:** Backlog

---

## Sprint 1 Snapshot

- **Goal.** Establish the project foundation and D1 planning artefacts; do not claim any AI feature as implemented.
- **Done to date.**
  - Initial repository foundation (commit `7670b89`): README, license (later removed), `.gitignore`, module placeholder READMEs, docs subfolder placeholders.
  - D1 planning artefacts first cut (commit `63927e8`): product vision, scope, epics, backlog, DoR, DoD, Sprint 1 plan.
  - Cleanup (commit `7caefe0`): removed placeholder READMEs and the Sprint 1 plan document.
  - Consolidation to the minimum repo (this commit): four target docs only.
- **In progress.** This commit and the D1 supervisor walkthrough.
- **Out of Sprint 1.** No application code, no AI evaluation logic, no recording, no deployment, no CI workflow file.