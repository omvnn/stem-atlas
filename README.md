# STEM Atlas — Math + Physics Academy

![Status](https://img.shields.io/badge/status-live-brightgreen) ![Hosting](https://img.shields.io/badge/hosting-GitHub%20Pages-blue) ![Stack](https://img.shields.io/badge/stack-HTML%20CSS%20JavaScript-orange) ![Progress](https://img.shields.io/badge/storage-browser%20local-blueviolet)

**[Open the academy](https://omvnn.github.io/stem-atlas/)** — no download or account needed.

## Background, goals and scope
Built for a beginner who wants simple explanations and a path toward mathematics and physics used in technology and engineering. The original standalone artifact is preserved as `index.html`.

Includes **143 mini-lessons** (84 Math, 59 Physics), **161 practice questions**, Starter/Core/Advanced/Research stages, randomized exams, four interactive labs, formulas, notes, bookmarks and progress backups. These are introductions and self-study assessments, not accredited exams or complete university courses.

## Getting started
Open the live site, choose **Start learning** or **Learn**, read the analogy and worked example, and answer the practice question. Use **Exams** for a randomized assessment; 70% is the practice pass threshold. **Labs** lets you change inputs and observe formula results.

For development, clone this repository and open `index.html`, or serve the folder with `python -m http.server 8000`. No package installation, build, API keys or database is needed.

## Architecture and data model
A single HTML file contains responsive CSS, curriculum data and vanilla JavaScript. GitHub Pages serves it over HTTPS from `main` / root. Updating `index.html` on main triggers publication.

- `STEM_DATA.topics`: lesson ID, subject, module, stage, analogy, explanation, formula, worked example, application, question, options, correct-answer index and feedback.
- `STEM_DATA.extra`: 18 additional assessment items; `sources`: further-learning links.
- Browser storage key `stemAtlasProgress`: passed quizzes, read checkpoints, notes, favorites and up to 120 exam records.
- Progress export/import uses a JSON backup. Exam sessions are temporary; completed history is saved locally.

## Security, privacy and limits
No login, backend, analytics integration, external scripts or application secrets. Study data stays in the browser; it does not sync between phones and computers. Export before changing devices or clearing browser storage. Hosting providers receive ordinary web requests, and external resources open their own sites.

Answers are in the public source, so exams are practice only. The site can keep working after loading, but offline reopening is not guaranteed: there is no service worker. Curriculum accuracy and accessibility have not received an exhaustive independent audit.

## QA evidence — 16 October 2026
Manual browser checks on the deployed website:
- Public HTTPS page loads and displays 143 lessons / 161 questions.
- Lesson practice displays correct-answer feedback and records mastery.
- A complete 10-question exam supports answering, navigation, submission, scoring and answer review; a final-source phone test returned 4/10 (40%), matching its review.
- Progress and completed exam counts survive navigation/reload.
- Desktop dashboard inspected; 390 × 844 phone viewport uses bottom navigation and stacked cards without horizontal page overflow on checked views.
- Mechanics slider: increasing mass from 5 to 6 kg at 3 m/s² updates force from 15 to 18 N.
- Final checked browser console reported no errors.

These are representative smoke checks, not tests of every lesson, timed expiry, backup restore, every browser or physical phone. A separate command-line HTTP check was unavailable due to local network restrictions; browser verification succeeded.

## Current progress and roadmap
| Label | Work |
| --- | --- |
| Completed | Original source recovered, public repository created, GitHub Pages enabled, representative lessons/exams/labs and responsive layouts verified |
| Pending | Full curriculum review, broader browser/device testing, timed-expiry and backup-restore coverage |
| Gated | Accounts, cross-device sync, paid services or custom domains require a separate scope decision |
| Blocked | No blocker for the published static academy |

## Decisions and changelog
- **2026-10-16:** Published the existing standalone academy using GitHub Pages; preserved the original UTF-8 mathematical notation after correcting a transfer encoding issue.
- Chose a public repository and GitHub-hosted domain to avoid paid hosting, custom-domain purchases and backend secrets.
- Retained browser-local progress and the original curriculum rather than adding new services.
