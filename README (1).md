# HUNAR — Skill Certification for Every Worker

> *She has cooked for 200 weddings. That is a skill. Give it a certificate.*

[![Technovation Girls](https://img.shields.io/badge/Technovation%20Girls-2025--2026-blueviolet?style=flat-square)](https://technovationchallenge.org)
[![SDG 8](https://img.shields.io/badge/SDG%208-Decent%20Work-A21942?style=flat-square)](https://sdgs.un.org/goals/goal8)
[![SDG 10](https://img.shields.io/badge/SDG%2010-Reduced%20Inequalities-DD1367?style=flat-square)](https://sdgs.un.org/goals/goal10)
[![SDG 5](https://img.shields.io/badge/SDG%205-Gender%20Equality-FF3A21?style=flat-square)](https://sdgs.un.org/goals/goal5)
[![Flutter](https://img.shields.io/badge/Built%20with-Flutter-02569B?style=flat-square&logo=flutter)](https://flutter.dev)

---

## The Problem

India has 100 million informal workers — cooks, tailors, weavers, caregivers, security guards — with decades of real skill and no credential to prove it.

No certification system was ever designed for them. The ones that exist require written tests, physical travel, and weeks of waiting. Workers fail not because they lack skill — but because the system was never built for them.

**The credential gap is not a competence failure. It is a design failure.**

---

## The Solution

HUNAR certifies workers through three layers — all on any basic Android phone, in four minutes, at zero cost to the worker:

| Layer | What happens |
|---|---|
| **Voice** | App reads questions aloud. Worker speaks answers. No reading required. |
| **Video demonstration** | Worker records themselves performing their skill. AI evaluates technique. |
| **Employer feedback** | Employer records a 30-second voice comment. No typing needed. |

Google Gemini evaluates all three together and generates a detailed score breakdown across criteria like Technique, Timing, Ingredient Handling, and Hygiene.

Result: a QR-verified digital certificate the worker owns permanently — shareable on WhatsApp to any employer instantly.

---

## Features

- **Multi-lingual** — Hindi, English, Rajasthani, Bhojpuri, and more
- **Voice-first** — flutter_tts reads everything aloud, literacy not required
- **14 professions** — Cook, Tailor, Caregiver, Weaver, Construction, Painter, Teacher, Cleaner, and more
- **AI Analysis** — Detailed scoring across Technique, Timing, Hygiene, Ingredient Handling, Presentation
- **Marketplace** — Employers browse and filter verified workers
- **Two-tier certification** — Basic (3 tests) and Advanced (6 tests)
- **Progress tracking** — Visual journey with 4 milestones
- **WhatsApp sharing** — Certificate shareable directly via share_plus
- **Demo mode** — 11 pre-loaded demo workers for judges to test

---

## Getting Started

```bash
git clone https://github.com/heerforit/HUNAR.git
cd HUNAR
flutter pub get
flutter run -d <device-id>
flutter build apk --release
```

Requirements: Flutter SDK 3.7.2+, Dart 3+, Android SDK 21+

Demo login: +919876543210 to +919876543220, password: demo123

---

## Tech Stack

| Technology | Purpose |
|---|---|
| Flutter + Dart | Cross-platform mobile app |
| flutter_tts | Text-to-speech for voice-first accessibility |
| camera + video_player | Video demonstration recording |
| record + audioplayers | Voice answer capture |
| shared_preferences | Local storage across screens |
| share_plus | WhatsApp certificate sharing |
| Google Gemini AI | Skill evaluation and scoring |

---

## Business Model

| Stream | Amount | Who pays |
|---|---|---|
| PMKVY government reimbursement | Rs.40-120 per assessment | Government of India |
| Employer placement fee | Rs.500 per worker placed | Gig platforms |
| Institution subscription | Rs.2,000/month | NGOs and training centres |

**Worker pays: Rs.0. Always.**

---

## User Research — Kota, Rajasthan, April 2026

Four people. Four skills. One identical answer when asked if they had a certificate: **No.**

- Hostel Warden — Cook and beauty worker — 15 years — zero certificates
- Mess Cook — Professional cooking — 10+ years — zero certificates  
- Security Guard — Security services — 20 years — zero certificates
- Gym Trainer — Fitness expertise — 8 years — zero certificates

---

## SDGs Addressed

- SDG 8 — Decent Work and Economic Growth
- SDG 10 — Reduced Inequalities
- SDG 5 — Gender Equality (80% of informal workers are women)

---

## About

Built by **Heer**, Class 11, Kota, Rajasthan for Technovation Girls 2025-2026 and Global Appathon 2026.

Mentor: Raghunandan Gupta, Senior Computer Scientist, Adobe Systems.

*Invisible expertise becomes economic power.*
