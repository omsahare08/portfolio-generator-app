# Portfolio Generator App

> Upload your resume → Get a beautiful, deployable portfolio website in seconds.

A full-stack mobile app built with **React Native** and **Node.js** that automatically parses your resume and generates a professional portfolio website — no manual entry required.

![Platform](https://img.shields.io/badge/platform-Android-green)
![React Native](https://img.shields.io/badge/React%20Native-0.73.6-blue)
![Node.js](https://img.shields.io/badge/Node.js-18%2B-brightgreen)
![License](https://img.shields.io/badge/license-MIT-blue)

---

## Features

- **Resume Parsing** — Upload PDF or DOCX, extract structured data automatically
- **Multiple Templates** — Modern, Minimal, and Creative styles
- **Live Preview** — See your portfolio before generating
- **One-tap Generation** — Generate and host instantly
- **Projects Section** — Extracts titles, descriptions, tools, and impact
- **Smart Link Detection** — Auto-detects GitHub, LinkedIn, live demo URLs
- **Cross-platform** — Android (iOS ready)
- **Dark UI** — Clean, modern dark-themed interface

---

## Tech Stack

### Mobile — React Native

| Package | Version | Purpose |
|---------|---------|---------|
| React Native | 0.73.6 | Mobile framework |
| React Navigation | 6.x | Screen navigation |
| Axios | 1.4.0 | API communication |
| React Native WebView | 13.6.4 | Portfolio preview |
| React Native Document Picker | 9.1.1 | Resume file picker |
| React Native Safe Area Context | 4.5.0 | Safe area handling |

### Backend — Node.js

| Package | Purpose |
|---------|---------|
| Express | REST API server |
| pdf-parse | PDF text extraction |
| mammoth | DOCX text extraction |
| Handlebars | HTML template rendering |
| multer | File upload handling |
| nodemon | Dev auto-reload |

---

##  Project Structure
```
PortfolioApp/
├── backend/
│   ├── src/
│   │   ├── controllers/
│   │   │   ├── resumeController.js
│   │   │   └── portfolioController.js
│   │   ├── services/
│   │   │   ├── resumeParser.js         # PDF/DOCX parsing engine
│   │   │   └── portfolioGenerator.js   # Handlebars renderer
│   │   ├── templates/
│   │   │   ├── modern.hbs
│   │   │   ├── minimal.hbs
│   │   │   └── creative.hbs
│   │   ├── middleware/
│   │   │   ├── upload.js
│   │   │   └── errorHandler.js
│   │   └── routes/
│   │       ├── resume.js
│   │       ├── portfolio.js
│   │       └── templates.js
│   ├── public/portfolios/              # Generated HTML portfolios
│   ├── uploads/                        # Temp resume uploads
│   └── package.json
│
└── PortfolioGeneratorApp/
    ├── src/
    │   ├── screens/
    │   │   ├── OnboardingScreen.js
    │   │   ├── ResumeUploadScreen.js
    │   │   ├── FormScreen.js
    │   │   ├── PreviewScreen.js
    │   │   └── DeployScreen.js
    │   ├── components/UI.js
    │   ├── navigation/
    │   └── services/api.js
    ├── android/
    ├── App.js
    └── package.json
```

---

## Getting Started

### Prerequisites

- Node.js 18+
- Java JDK 17 ([Temurin](https://adoptium.net/))
- Android Studio + SDK (API 21+)
- Android device or emulator
- Git

### 1. Clone
```bash
git clone https://github.com/yourusername/portfolio-generator-app.git
cd portfolio-generator-app
```

### 2. Start Backend
```bash
cd backend
npm install
npm run dev
```

Runs at `http://localhost:3000`

### 3. Run Mobile App
```bash
cd PortfolioGeneratorApp
npm install --legacy-peer-deps
```

**Physical device (USB):**
```bash
adb reverse tcp:3000 tcp:3000
npx react-native run-android
```

**Emulator:**
```bash
npx react-native run-android
```

>  Re-run `adb reverse tcp:3000 tcp:3000` every time you reconnect your phone.

---

##  API Reference

| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/api/resume/parse` | Parse a resume file |
| `GET` | `/api/templates` | List templates |
| `POST` | `/api/portfolio/preview` | HTML preview |
| `POST` | `/api/portfolio/generate` | Generate & save |
| `DELETE` | `/api/portfolio/:id` | Delete portfolio |
| `GET` | `/health` | Health check |

---

##  Templates

| Template | Style |
|----------|-------|
| **Modern** | Dark bg · Indigo accents · Project cards with Tools & Impact |
| **Minimal** | Clean white · Subtle typography |
| **Creative** | Bold · Colorful · Strong hierarchy |

---

##  Resume Tips for Best Parsing
```
PROJECTS
  My Project Name
  • Built a full-stack app to solve X problem
  Tech: React, Node.js, MongoDB
  Impact: Reduced setup time by 90%
  https://github.com/you/project

EXPERIENCE
  Software Engineer
  Company Name
  Jan 2022 – Present
  • Key achievement here

SKILLS
  React Native, Node.js, Python, MongoDB
```

Supported: **PDF** · **DOCX**

---

## Android Build Config
```
React Native:       0.73.6
Kotlin:             1.9.0
compileSdkVersion:  34
targetSdkVersion:   34
minSdkVersion:      21
Android Gradle:     8.3.2
Gradle Wrapper:     8.4
```

---

##  Troubleshooting

| Problem | Fix |
|---------|-----|
| Network Error on device | `adb reverse tcp:3000 tcp:3000` |
| Metro stale cache | `npx react-native start --reset-cache` |
| Gradle build fails | `cd android && gradlew.bat clean` |
| `adb` not found | Add SDK platform-tools to PATH |

---

## Contributing

1. Fork the repo
2. `git checkout -b feature/your-feature`
3. `git commit -m "feat: your feature"`
4. `git push origin feature/your-feature`
5. Open a Pull Request

---

##  License

MIT — see [LICENSE](LICENSE)

---

##  Author

**Om Sahare**

---

<div align="center">Built with ❤️ using React Native + Node.js</div>
