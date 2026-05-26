# ⚡ CareerVolt — AI-Driven Career Analysis Platform

> **Maps your resume skills to real-world job opportunities at Indian companies** — with AI-powered matching, skill gap analysis, resume audit, JD comparison, interview prep, LinkedIn optimization, and a Groq-powered career copilot.

<div align="center">

![Platform](https://img.shields.io/badge/Platform-Web%20App-7c3aed?style=for-the-badge)
![Frontend](https://img.shields.io/badge/Frontend-React%2018%20%2B%20Vite-61DAFB?style=for-the-badge&logo=react)
![Backend](https://img.shields.io/badge/Backend-FastAPI%20v5-009688?style=for-the-badge&logo=fastapi)
![AI](https://img.shields.io/badge/AI-Groq%20llama3-FF6B35?style=for-the-badge)

**💰 ₹599 — One-time purchase · Lifetime access · Self-hosted**

</div>

---

## 📌 What CareerVolt Does

Upload your resume PDF → The system automatically:

1. **Extracts your skills** using NLP (spaCy + keyword matching)
2. **Matches you to 25 job roles** at Indian companies — Flipkart, Swiggy, Zomato, Razorpay, CRED, Zerodha, PhonePe, and more
3. **Shows your readiness score** with weighted AI matching
4. **Predicts career impact**: *"Learning Deep Learning can boost your match from 54% → 85%"*
5. **Generates a step-by-step roadmap** to reach your best-fit role
6. **Compares your resume vs any job description** you paste
7. **Audits your resume** with ATS scoring across 5 dimensions
8. **Suggests curated courses** for every missing skill
9. **Runs AI interview prep** with role-specific questions
10. **Optimizes your LinkedIn profile** using Groq AI
11. **Shows salary insights** for entry, mid, and senior levels
12. **Answers career questions** via an AI chatbot with your resume context

---

## ✨ Feature List

| Feature | Description | Powered By |
|---|---|---|
| 📄 **PDF Resume Parsing** | Extracts text from any PDF resume | pdfplumber + pypdf |
| 🧠 **NLP Skill Extraction** | Identifies 100+ tech skills automatically | spaCy + keyword matching |
| 🏢 **Company-Aligned Job Matching** | 25 roles at Indian companies | Custom dataset |
| ⚖️ **Weighted Scoring** | Core skills = 70%, Other = 30% | Custom algorithm |
| ⚡ **Impact Prediction** | *"Learning X raises match Y% → Z%"* | Insights Engine |
| 🔥 **Critical Skill Split** | 🔥 Must-learn vs ⚪ Secondary skills | jobs.json core_skills |
| 📚 **One-Click Course Links** | Every missing skill → direct course URL | courses.json |
| 🗺️ **Career Roadmap** | Step-by-step path to your best-fit role | Insights Engine |
| 📋 **JD Matcher** | Paste any job description → gap report | skill_extractor.py |
| 📊 **Resume Audit Score** | 5-dimension ATS compatibility score | resume_scorer.py |
| 👥 **Candidate Benchmarking** | *"Top candidates have 9-11 skills. You have 5."* | Job dataset |
| 🎤 **Interview Prep** | 10 Q&A per role + AI-generated custom questions | Groq llama3 |
| 💼 **LinkedIn Optimizer** | AI rewrites your summary, headline, and sections | Groq llama3 |
| 🤖 **AI Career Copilot** | Context-aware career guidance chatbot | Groq llama3 |
| 💰 **Salary Insights** | Entry/Mid/Senior splits for all 25 roles | jobs.json |
| ⏱️ **Time Estimates** | *"~2 months of structured learning needed"* | Gap-based formula |

---

## 🧠 How the Matching Algorithm Works

We use **weighted matching based on core competencies** — not a simple skill count:

```python
# Core skills carry 70% of the score
# Other required skills carry 30%

core_score  = len(core_skills_matched)  / len(total_core_skills)
other_score = len(other_skills_matched) / len(total_other_skills)

weighted_match = (0.70 × core_score + 0.30 × other_score) × 100
```

**Why this matters:** A candidate who knows Python + ML (core skills for Data Scientist) ranks higher than someone who only knows secondary tools — this mirrors **real hiring priorities** at Indian companies.

---

## 📊 Dataset — 25 Indian Job Roles

| # | Role | Company | Level | Salary Range |
|---|------|---------|-------|-------------|
| 1 | Data Scientist | Flipkart | Mid | ₹18-30 LPA |
| 2 | Data Analyst | Swiggy | Entry | ₹6-12 LPA |
| 3 | ML Engineer | Razorpay | Mid | ₹20-35 LPA |
| 4 | AI Engineer | CRED | Mid | ₹22-40 LPA |
| 5 | Deep Learning Engineer | Zerodha | Senior | ₹30-50 LPA |
| 6 | NLP Engineer | ShareChat | Mid | ₹18-32 LPA |
| 7 | Computer Vision Engineer | Ola | Mid | ₹18-35 LPA |
| 8 | Data Engineer | Zomato | Mid | ₹14-28 LPA |
| 9 | Business Analyst | Myntra | Entry | ₹6-12 LPA |
| 10 | BI Developer | PhonePe | Mid | ₹12-24 LPA |
| 11 | Full Stack Developer | Razorpay | Mid | ₹16-30 LPA |
| 12 | Frontend Developer | CRED | Mid | ₹14-28 LPA |
| 13 | Backend Developer | Swiggy | Mid | ₹16-30 LPA |
| 14 | DevOps Engineer | Zerodha | Senior | ₹22-40 LPA |
| 15 | Cloud Architect | Flipkart | Senior | ₹35-60 LPA |
| 16 | MLOps Engineer | Groww | Mid | ₹20-35 LPA |
| 17 | Software Engineer | Uber | Mid | ₹20-38 LPA |
| 18 | QA Engineer | Ola | Entry | ₹4-8 LPA |
| 19 | Cybersecurity Analyst | Paytm | Mid | ₹12-24 LPA |
| 20 | Blockchain Developer | CoinSwitch | Mid | ₹18-35 LPA |
| 21 | Product Manager | Flipkart | Senior | ₹30-55 LPA |
| 22 | Technical Writer | Postman | Entry | ₹6-12 LPA |
| 23 | Database Administrator | Myntra | Mid | ₹10-20 LPA |
| 24 | Mobile Developer | Swiggy | Mid | ₹16-30 LPA |
| 25 | Site Reliability Engineer | Zerodha | Senior | ₹28-50 LPA |

---

## 🏗️ System Architecture

```
┌─────────────┐     ┌──────────────┐     ┌──────────────┐
│   Browser   │────▶│   Vercel     │────▶│   Render     │
│  (React)    │     │  (Rewrites)  │     │  (FastAPI)   │
└─────────────┘     └──────────────┘     └──────┬───────┘
       │                                         │
       │                                         ▼
       │                                  ┌──────────────┐
       │                                  │   Groq API   │
       │                                  │  (LLM Chat)  │
       │                                  └──────────────┘
       │
       │              ┌──────────────┐     ┌──────────────┐
       ├─────────────▶│   Render     │────▶│  MongoDB     │
       │              │  (Auth Svr)  │     │  (Atlas)     │
       │              └──────────────┘     └──────────────┘
       │
       ▼
  ┌─────────────┐
  │ Google OAuth │
  └─────────────┘
```

---

## 📁 Project Structure

```
Career-Volt/
│
├── backend/                        # Python FastAPI backend
│   ├── data/
│   │   ├── jobs.json               # 25 job roles · Indian companies · salaries
│   │   └── courses.json            # Skill → course URL mappings
│   ├── main.py                     # FastAPI app — all API routes
│   ├── job_matcher.py              # Weighted matching engine (70/30 core split)
│   ├── insights_engine.py          # Impact prediction · roadmap · suggestions
│   ├── resume_parser.py            # PDF text extraction (pdfplumber + pypdf)
│   ├── resume_scorer.py            # 5-dimension resume quality audit
│   ├── skill_extractor.py          # NLP skill extraction (spaCy + keyword)
│   ├── ai_chat.py                  # Groq LLM career copilot
│   ├── interview_prep.py           # Interview Q&A bank + AI question generator
│   ├── linkedin_optimizer.py       # LinkedIn profile AI optimizer
│   └── requirements.txt
│
├── auth-server/                    # Node.js JWT + Google OAuth microservice
│   ├── routes/auth.js              # /signup · /login · /google (rate limited)
│   ├── controllers/authController.js
│   ├── models/User.js
│   └── server.js
│
├── src/                            # React 18 + Vite frontend
│   ├── components/
│   │   ├── Dashboard.jsx           # Multi-tab main dashboard
│   │   ├── LandingPage.jsx         # Landing page with upload
│   │   ├── AuthPage.jsx            # Login/Signup/Google
│   │   ├── CopilotPanel.jsx        # AI Career Copilot (Groq-powered)
│   │   ├── JobMatchCard.jsx        # Company card + readiness labels
│   │   ├── MissingSkills.jsx       # 🔥/⚪ skill split + Learn buttons
│   │   ├── JDMatcher.jsx           # Job description comparison
│   │   ├── CareerRoadmap.jsx       # Step-by-step roadmap
│   │   ├── InterviewPrep.jsx       # Interview Q&A + AI questions
│   │   ├── LinkedInOptimizer.jsx   # LinkedIn AI optimizer
│   │   ├── SalaryInsights.jsx      # Salary range benchmarks
│   │   ├── ResumeAudit.jsx         # ATS resume scoring
│   │   ├── CoursesPanel.jsx        # Curated course recommendations
│   │   └── ChatBot.jsx             # Fallback chatbot
│   ├── context/
│   │   ├── AuthContext.jsx         # Global auth state
│   │   ├── CopilotContext.jsx      # Global copilot state
│   │   └── ThemeContext.jsx        # Dark/light theme
│   ├── utils/                      # API helpers and utilities
│   └── index.css                   # Dark glassmorphism design system
│
├── .env.example
├── vercel.json                     # Vercel deployment config
├── vite.config.js
└── README.md
```

---

## 🚀 Live Demo

The platform is deployed and live:

- **Frontend**: https://career-volt.vercel.app
- **Backend API**: https://careervolt-api.onrender.com

Upload your resume and get instant AI-powered career analysis — no signup required.

---

## 💰 Purchase — ₹599 (One-Time)

This is a **commercial product** — not open source.

### What you get:
- ✅ Full source code (React + FastAPI + Express)
- ✅ Complete 25-job Indian dataset
- ✅ Google OAuth + JWT authentication
- ✅ Vercel + Render deployment configs
- ✅ Deployment support via email
- ✅ Lifetime updates

### How to purchase:
1. Contact: **[jeedimetlacharan213@gmail.com]**
2. Payment: UPI / PayPal / Bank Transfer
3. Delivery: Private GitHub repository access within 24 hours

### Self-hosted:
- No recurring fees (pay ₹599 once)
- No data leaves your servers
- Full control over customization
- Add your own job roles and companies

---

## 🔐 Security

- ✅ All API keys stored in `.env` (never committed)
- ✅ Rate limiting on all auth endpoints (10 req / 15 min per IP)
- ✅ JWT-based session management (7-day expiry)
- ✅ bcrypt password hashing
- ✅ Google OAuth token verification
- ✅ No `dangerouslySetInnerHTML` — XSS-safe
- ✅ `.gitignore` excludes `.env`, `node_modules`, `__pycache__`, `.venv`

---

## 📄 License

**Commercial License** — All rights reserved.

This software is not open source. Purchase of a license grants you the right to:
- Use the software for personal or commercial purposes
- Modify the code for your own use
- Deploy on your own infrastructure

You may NOT:
- Redistribute or resell the source code
- Remove attribution from the platform
- Share access with non-licensees

---

<div align="center">

Built with ⚡ by **CareerVolt**  
*AI Career Analysis Platform · v5.0.0*

📧 [jeedimetlacharan213@gmail.com] • 💻 https://career-volt.vercel.app

</div>
