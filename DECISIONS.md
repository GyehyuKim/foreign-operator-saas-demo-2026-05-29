---
date: 2026-05-29
type: reference
tags: [40-dev-ai, 30-sbl]
---

# foreign-operator-saas-demo — decision log

This note archives the product and UX decisions made while shaping the demo.

## Why this project exists

- The demo is not a generic dashboard.
- It is a document-package generator for operators of foreigner-facing housing / lodging in Gyeonggi.
- The value proposition is to reduce repeated manual work around documents, routing, and support-center lookup.

## Key decisions

### 1) Use Gyeonggi public data as the main proof point
- The competition is hosted by Gyeonggi, so Gyeonggi public data gives the clearest evaluation fit.
- Public data is used as an input for routing, prioritization, and document recommendations — not as surveillance.

### 2) Shift away from "demand analysis" as the core story
- The first framing leaned too much toward demand scoring.
- The product direction was narrowed to:
  - document package generation
  - checklist / readiness tracking
  - jurisdiction and support-center guidance
  - contract / notice text customization

### 3) Add explicit execution flow
- Selection-only screens were rejected.
- The UI now needs a visible next action after selection, such as:
  - `실행안 생성`
  - `문서 패키지 만들기`
  - `맞춤 문구 적용`

### 4) Split the journey into tabs
- Tabs were added because the product has distinct jobs:
  - `문서 패키지`
  - `문구 맞춤`
  - `연계기관`
- This prevents the support / routing view from obscuring the primary story.

### 5) Explain why region is selected
- Region is not there to score users.
- Region exists so the system can fill in:
  - jurisdiction labels
  - support-center routing
  - address text in notices and contracts

### 6) Treat region and industry as different kinds of inputs
- Industry answers: what document package should be generated?
- Region answers: where should the document package be routed / localized?
- They should not appear as equal-weight filters.

### 7) Add customization for operators
- The user explicitly asked for the ability to tailor generated text.
- The demo now needs to support:
  - name changes
  - address changes
  - bank account fields
  - move-out / operational rules
  - tone presets

### 8) Keep the repo as the archive of record
- For this project, decisions and spec changes should live in GitHub.
- Local-only notes are not enough.
- Commit messages and markdown notes should preserve the path of the product decisions.

### 9) Support HTML and PDF export for the generated document
- The generated contract/document should be previewed in HTML first.
- Users should be able to:
  - save a self-contained HTML snapshot
  - open the browser print dialog to save as PDF
- Export controls should sit near the preview so the flow stays continuous.

## Current docs in the repo

- `spec.md` — current product spec
- `index.html` — interactive demo
- `DECISIONS.md` — this archive note

## Open decisions

- Should the default landing view open on `문서 패키지` or on the last persisted tab?
- Should the UX ask for industry first or region first?
- How much text customization should be exposed in v1 without making the UI heavy?
