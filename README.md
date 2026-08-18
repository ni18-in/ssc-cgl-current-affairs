# SSC CGL Daily Current Affairs & Quiz Hub

A static, lightweight, and high-performance repository providing **Bilingual (Hindi & English)** Daily Current Affairs Quizzes and historical archives for **SSC CGL Prep**.

---

## 🌟 Features

- **🌐 100% Bilingual Support**: Every question, option, and step-by-step explanation is provided in both **English** and **Hindi (हिन्दी)**.
- **🎯 SSC CGL Syllabus Aligned**: Curated specifically for SSC CGL Tier 1 & Tier 2 General Awareness (National, Economy & Banking, Science & Tech, Defence, Sports, Schemes, Appointments, Awards, Environment).
- **⚡ Offline-First API Endpoint**: Hosted via GitHub Pages, serving static, CDN-cached JSON files for mobile synchronization.
- **🤖 Automated Daily Rollover**: GitHub Actions workflow automatically schedules, validates, and rolls over daily quizzes at 06:30 IST.
- **📱 Web Viewer & Quiz Runner**: Modern, responsive Web UI with live language switching (English, Hindi, Bilingual), instant grading, and detailed explanations.

---

## 📁 Repository Structure

```text
current-affairs/
├── .github/
│   └── workflows/
│       ├── daily-update.yml       # Daily automated quiz rollover action
│       └── pr-auto-merge.yml      # PR auto-merge bot
├── data/
│   ├── current.json               # Today's active quiz (bilingual)
│   ├── metadata.json              # Available archive dates & app configuration
│   └── archive/
│       ├── 2026-07-21.json        # Historical quiz snapshots
│       ├── 2026-07-20.json
│       ├── 2026-07-19.json
│       └── 2026-07-18.json
├── index.html                     # Web archive viewer & interactive quiz runner
└── README.md                      # Documentation
```

---

## 📋 JSON Schema (Bilingual)

### `data/current.json` / `data/archive/<YYYY-MM-DD>.json`
```json
{
  "date": "2026-07-21",
  "topic": "SSC CGL Daily Current Affairs",
  "source": "PIB / The Hindu / Economic Times / Indian Express / GKToday",
  "lastUpdated": "2026-07-21T06:30:00+05:30",
  "version": 1,
  "totalQuestions": 10,
  "quiz": [
    {
      "id": "ca_20260721_01",
      "question": {
        "en": "Which portal was launched by the Union Ministry of Law and Justice...",
        "hi": "केंद्रीय विधि एवं न्याय मंत्रालय द्वारा कौन सा पोर्टल लॉन्च किया गया..."
      },
      "options": [
        { "en": "Option A", "hi": "विकल्प क" },
        { "en": "Option B", "hi": "विकल्प ख" },
        { "en": "Option C", "hi": "विकल्प ग" },
        { "en": "Option D", "hi": "विकल्प घ" }
      ],
      "correctAnswer": 2,
      "explanation": {
        "en": "Detailed step-by-step explanation...",
        "hi": "विस्तृत व्याख्या..."
      },
      "category": "Polity & Governance",
      "difficulty": "medium",
      "sourceUrl": "https://pib.gov.in"
    }
  ]
}
```

### `data/metadata.json`
```json
{
  "appConfig": {
    "maxArchiveDays": 30,
    "forceUpdateAfter": "2026-07-22T06:00:00+05:30",
    "currentAffairsTopicId": "current_affairs"
  },
  "availableDates": [
    "2026-07-21",
    "2026-07-20",
    "2026-07-19",
    "2026-07-18"
  ],
  "dateRange": {
    "earliest": "2026-07-18",
    "latest": "2026-07-21"
  },
  "totalArchivedQuizzes": 4
}
```

---

## 🚀 GitHub Pages Setup

1. In GitHub Repository Settings, navigate to **Pages**.
2. Select **Deploy from a branch** under Source..
3. Choose branch `main` (or `master`) and directory `/ (root)`.
4. The live site will be accessible at:
   `https://<username>.github.io/<repo-name>/`
   - Interactive Web Portal: `https://<username>.github.io/<repo-name>/`
   - Metadata Endpoint: `https://<username>.github.io/<repo-name>/data/metadata.json`
   - Current Quiz: `https://<username>.github.io/<repo-name>/data/current.json`
