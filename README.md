# HUNAR — Skill Certification for Every Worker

> *She has cooked for 200 weddings. That is a skill. Give it a certificate.*

[![Technovation Girls](https://img.shields.io/badge/Technovation%20Girls-2025--2026-blueviolet?style=flat-square)](https://technovationchallenge.org)
[![Global Appathon](https://img.shields.io/badge/Global%20Appathon-2026-orange?style=flat-square)](https://globalappathon.org)
[![SDG 8](https://img.shields.io/badge/SDG%208-Decent%20Work-A21942?style=flat-square)](https://sdgs.un.org/goals/goal8)
[![SDG 10](https://img.shields.io/badge/SDG%2010-Reduced%20Inequalities-DD1367?style=flat-square)](https://sdgs.un.org/goals/goal10)
[![SDG 5](https://img.shields.io/badge/SDG%205-Gender%20Equality-FF3A21?style=flat-square)](https://sdgs.un.org/goals/goal5)
[![Flutter](https://img.shields.io/badge/Built%20with-Flutter-02569B?style=flat-square&logo=flutter)](https://flutter.dev)
[![MIT App Inventor](https://img.shields.io/badge/Started%20with-MIT%20App%20Inventor-1a4731?style=flat-square)](https://appinventor.mit.edu)

**Live site:** https://heerforit.github.io/HUNAR

---

## The Problem

India has 100 million informal workers — cooks, tailors, weavers, caregivers, security guards — with decades of real skill and no credential to prove it.

No certification system was ever designed for them.

The ones that exist require written tests, physical travel, and weeks of waiting. Workers fail not because they lack skill — but because the system was never built for them.

I found this problem fifty metres from my hostel room in Kota. My warden has cooked professionally for fifteen years. She has never received a single certificate for any of it.

**The credential gap is not a competence failure. It is a design failure.**

---

## The Solution

HUNAR certifies workers through three layers — on any basic Android phone, in four minutes, at zero cost to the worker:

| Layer | What happens |
|---|---|
| **Voice** | App reads questions aloud. Worker speaks answers. No reading required. |
| **Video demonstration** | Worker records herself performing her skill. AI evaluates technique. |
| **Employer feedback** | Employer records a 30-second voice comment. No typing needed. |

Google Gemini evaluates all three together and generates a score breakdown across criteria including Technique, Timing, Hygiene, Ingredient Handling, and Presentation.

Result: a QR-verified digital certificate the worker owns permanently — shareable on WhatsApp to any employer instantly.

---

## User Research — Kota, Rajasthan, April 2026

| Person | Skill | Experience | Certificate |
|---|---|---|---|
| Hostel Warden | Cook + Beauty worker | 15 years | None |
| Mess Cook | Professional cooking | 10+ years | None |
| Security Guard | Security services | 20 years | None |
| Gym Trainer | Fitness expertise | 8 years | None |

Four people. Four different skills. One identical answer when asked if they had a certificate for their work:

**No.**

That answer is why HUNAR exists.

---

## Development Journey

This project went through two complete versions based on real user feedback. Both versions are preserved in this repository to show the iteration process.

### Version 1 — MIT App Inventor (March 2026)

**File:** `Hunar3.aia`

Built the initial prototype using MIT App Inventor — a block-based visual programming environment. The goal was to prove the concept worked before investing in a full production build.

**What it had:**
- 5 screens — language selection, skill selection, voice assessment, processing, certificate
- `TextToSpeech` component reads questions aloud in worker's language
- `SpeechRecognizer` captures spoken answers — no typing required
- `TinyDB` with shared namespace `HUNARdb` persists data across all 5 screens
- `Sharing` component sends certificate via WhatsApp
- Questions loaded dynamically based on skill — one assessment screen handles all 5 skills

**What changed after testing with my warden:**
- She kept looking at the question text even though the app was reading it aloud → made question text smaller, microphone button much larger
- She did not understand "Level 2" → added the word "Proficient" next to the number

**Shortcomings identified:**
- Questions were in English only — contradicted the multilingual design principle
- Any spoken answer scored a point — no real AI evaluation of answer quality
- Certificate was text only — no actual QR code generation
- Limited to 5 skill categories

**Decision:** These shortcomings were too fundamental to patch. Rebuilt from scratch in Flutter.

---

### Version 2 — Flutter + Dart + AI (April 2026)

**File:** `Hunar (3).zip`

Complete rebuild in Flutter for production quality, addressing every shortcoming identified in V1.

**What was added:**
- Video demonstration assessment — worker records herself working on camera
- Google Gemini AI evaluates video across 7 criteria with percentage scores
- Employer voice feedback — 30-second recorded comment, no typing
- 14 profession categories (up from 5)
- Two-tier certification — Basic (3 tests) and Advanced (6 tests)
- Employer marketplace — browse, filter, and contact verified workers
- Full multi-lingual support via `LocalizationService`
- `flutter_tts` for voice-first accessibility
- `shared_preferences` replaces TinyDB for cross-screen persistence
- `share_plus` for WhatsApp certificate sharing
- Demo mode with 11 pre-loaded workers for judges

**AI Analysis output (real result):**

| Criterion | Score |
|---|---|
| Technique | 87% |
| Timing | 93% |
| Ingredient Handling | 96% |
| Hygiene | 70% |
| Video Quality | 75% |
| Presentation | 75% |
| Face Detection | 85% |
| **Overall** | **83/100** |

---

## Tech Stack

### Version 1 — MIT App Inventor
| Component | Purpose |
|---|---|
| TextToSpeech | Reads questions aloud in worker's language |
| SpeechRecognizer | Captures spoken answers |
| TinyDB (HUNARdb namespace) | Shared data across 5 screens |
| Clock | 3-second processing screen timer |
| Sharing | WhatsApp certificate sharing |

### Version 2 — Flutter
| Technology | Purpose |
|---|---|
| Flutter + Dart | Cross-platform mobile app |
| flutter_tts | Text-to-speech accessibility |
| camera + video_player | Video demonstration recording |
| record + audioplayers | Voice answer capture |
| shared_preferences | Cross-screen data persistence |
| share_plus | WhatsApp certificate sharing |
| Google Gemini AI | 7-criteria skill scoring |
| permission_handler | Camera, microphone, storage |

---

## Getting Started — Flutter Version

```bash
git clone https://github.com/heerforit/HUNAR.git
cd HUNAR
unzip "Hunar (3).zip"
cd "Hunar (2)/Hunar"
flutter pub get
flutter run -d <device-id>
flutter build apk --release
```

**Requirements:** Flutter SDK 3.7.2+, Dart 3+, Android SDK 21+

**Demo login:** +919876543210 through +919876543220, password: `demo123`

---

## Getting Started — App Inventor Version

1. Go to [ai2.appinventor.mit.edu](https://ai2.appinventor.mit.edu)
2. Projects → Import project (.aia) → select `Hunar3.aia`
3. Connect → AI Companion → scan QR code with MIT AI2 Companion app on Android

---

## Project Structure — Flutter Version

```
lib/
├── main.dart
├── models/
│   ├── user.dart
│   ├── professions.dart
│   └── challenges.dart
├── screens/
│   ├── landing_page.dart
│   ├── signup_screen.dart
│   ├── login_screen.dart
│   ├── profession_selection_screen.dart
│   ├── challenge_screen.dart
│   ├── video_recording_screen.dart
│   ├── analysis_screen.dart         ← AI scoring results
│   ├── profile_screen.dart          ← Verified certificate
│   ├── marketplace_screen.dart      ← Employer browsing
│   └── worker_detail_screen.dart
├── services/
│   ├── localization_service.dart    ← 5 Indian languages
│   ├── tts_service.dart             ← Text-to-speech
│   └── app_data.dart
├── widgets/
└── utils/
```

---

## Business Model

HUNAR earns from employers and government — never from workers.

| Stream | Amount | Who pays | Why |
|---|---|---|---|
| PMKVY government reimbursement | Rs.40–120 per assessment | Government of India | Rs.12,000 crore already allocated for informal worker certification |
| Employer placement fee | Rs.500 per worker placed | Gig platforms | Pre-verified workers reduce complaint rates and onboarding cost |
| Institution subscription | Rs.2,000/month | NGOs and training centres | Proof of impact for donors |

**Worker pays: Rs.0. Always.**

Break-even: 500 assessments per month. Gross margin: ~95%.

---

## Ethical Commitments

1. Voice recordings deleted within 72 hours of assessment
2. AI defaults to higher score in ambiguous cases — worker never penalised
3. Voice consent required before every session in worker's language
4. Worker told what the certificate means and how to delete their record
5. AI evaluates technique only — not camera quality, environment, or presentation quality

---

## SDG Alignment

| SDG | How HUNAR addresses it |
|---|---|
| **SDG 8 — Decent Work** | Creates economic credentials for workers excluded from formal employment systems |
| **SDG 10 — Reduced Inequalities** | The credential gap compounds every other inequality informal workers face. HUNAR closes it. |
| **SDG 5 — Gender Equality** | 80% of informal domestic and care workers are women. HUNAR gives them economic power from expertise they already have. |

---

## Competitions

- **Technovation Girls 2025–2026** — Senior Division
- **Global Appathon 2026** — MIT App Inventor Foundation — Youth Individual (13–17)

---

## Acknowledgements

**Raghunandan Gupta** — Senior Computer Scientist, Adobe Systems, Noida. Business mentorship, revenue model validation, go-to-market feedback. Former Technovation Girls judge.

**Hostel Warden, Kota** — Primary user research participant. Her fifteen years of professional cooking and beauty work with zero credentials directly shaped every design decision in both versions of HUNAR.

**Mess Cook, Security Guard, Gym Trainer, Kota** — User research participants. Confirmed the credential gap across four different skill categories.

---

## About the Creator

**Heer** — Class 11 student, Kota, Rajasthan, India

Built HUNAR while preparing for JEE, living in a hostel fifty metres away from the woman the app was designed for.

---

*Invisible expertise becomes economic power.*

*This is HUNAR.*
