# 🧠 Agentic CV Screener

An enterprise-grade, asynchronous resume processing dashboard powered by Python, Flask, and Google's Gemini 2.5 Flash.

Unlike standard AI wrappers that return unstructured chat text, this application utilizes an **Agentic Workflow** to enforce strict JSON data extraction. It evaluates multiple candidates in batches, scores them against a Job Description, and generates real-time visual analytics without ever reloading the browser.

![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python&logoColor=white) ![Flask](https://img.shields.io/badge/Flask-Serverless-lightgrey?logo=flask) ![Gemini](https://img.shields.io/badge/Google_GenAI-2.5_Flash-orange) ![Tailwind](https://img.shields.io/badge/Tailwind_CSS-Integrated-06B6D4?logo=tailwindcss)

## 🏗️ Core Capabilities

* **Asynchronous Batch Pipeline:** Features a custom drag-and-drop accumulator that accepts multiple PDFs. The frontend orchestration engine processes files sequentially with built-in API throttling to prevent server overloads and 503 rate limits.
* **Structured Agentic Reasoning:** The AI acts under a strict recruiter persona, bypassing conversational outputs to return clean JSON schemas containing Match Scores, Candidate Summaries, and Critical Skill Gaps.
* **Dynamic Visual Analytics:** Integrates `matplotlib` using an in-memory `Agg` backend to instantly generate Base64-encoded comparative bar charts—mapping a candidate's verified skills directly against the job requirements.
* **Actionable Interview Strategy:** Automatically translates a candidate's technical weaknesses into a targeted list of 5-7 technical interview questions for HR teams to utilize.
* **Single Page Application (SPA):** A glassmorphic, responsive UI built with Tailwind CSS and Vanilla JS that dynamically transitions from an upload interface to a sleek analytics dashboard.

## 💻 The Tech Stack

**Backend System**
* **Framework:** Flask (Python)
* **Data Processing:** `pypdf` for rapid, stateless text extraction.
* **Analytics Engine:** `matplotlib` + `io.BytesIO` for diskless image rendering.

**AI & Orchestration**
* **Model:** `gemini-2.5-flash` via the `google-genai` SDK.
* **Architecture:** System Instructions with `application/json` enforced mime-types.

**Frontend Interface**
* **Styling:** Tailwind CSS (via CDN)
* **Logic:** Vanilla JavaScript (Fetch API, Promises, DataTransfer Objects)

## ⚙️ Quick Start Guide

Follow these steps to run the pipeline on your local machine:

**1. Clone & Navigate**
```bash
git clone [https://github.com/ishita230105/hr-ai-agent.git](https://github.com/ishita230105/hr-ai-agent.git)
cd hr-ai-agent
```

**2. Create & Activate a Virtual Environment**
```bash
python -m venv venv

# Windows:
venv\Scripts\activate

# Mac/Linux:
source venv/bin/activate
```

**3. Install Dependencies**
```bash
pip install -r requirements.txt
```

**4. Set Environment Variables & Run**
```bash
# Mac/Linux:
export GOOGLE_API_KEY="your_gemini_api_key_here"
python api/index.py

# Windows (Command Prompt):
set GOOGLE_API_KEY=your_gemini_api_key_here
python api/index.py

# Windows (PowerShell):
$env:GOOGLE_API_KEY="your_gemini_api_key_here"
```
**5. Initialize the Server**
```bash
python api/index.py
```
