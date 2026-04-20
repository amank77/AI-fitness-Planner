
# 🏋️‍♂️ **AI Fitness Planner** 

*7-Day Personalized Workout + Diet Plan using CrewAI Agents + FastAPI + Streamlit*

---

## 📌 Overview

**AI Fitness Planner** is a lightweight, agentic AI application built for hackathons.
It generates a **7-day personalized fitness plan** using **CrewAI agents** and provides a simple **daily dashboard** to track progress.

This project focuses on delivering a **clean, functional MVP** in under 24 hours.

### 🚀 Features

* **AI-powered workout + diet plan generation**
* **Simple daily dashboard** to track if you completed your workout & diet
* **FastAPI backend**
* **CrewAI agents** (Workout Agent + Diet Agent)
* **Streamlit frontend**
* Clean and expandable folder structure

---

# 📂 Folder Structure

```
fitness-ai/
│
├── backend/
│   ├── main.py                     # FastAPI app entry
│   ├── plan/
│   │   ├── generator.py            # Plan generation logic (CrewAI)
│   │   └── agents.py               # Workout & Diet agents
│   ├── routers/
│   │   ├── plan.py                 # /generate-plan endpoint
│   │   └── dashboard.py            # dashboard endpoints
│   ├── models/
│   │   ├── profile.py
│   │   └── progress.py
│   ├── requirements.txt
│   └── README.md
│
├── frontend/
│   ├── Home.py                     # Streamlit main page
│   ├── pages/
│   │   ├── 1_Onboarding.py
│   │  
│   ├── utils/
│   │   └── api.py                  # Backend API calls
│   └── README.md
│
└── README.md                        # You're reading this!
```

---

# ⚡ Installation Guide

## 1. Install **uv** (Required)

### Linux / Mac

```sh
curl -LsSf https://astral.sh/uv/install.sh | sh
```

### Windows

```powershell
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

Verify installation:

```sh
uv --version
```

---

## 2. Create & Activate a Virtual Environment

```sh
uv venv
source .venv/bin/activate   # Linux / Mac
.venv\Scripts\activate      # Windows
```

---

## 3. Install Backend Dependencies

```sh

    uv syn #install dependecy
```
---

## 4. Environment Variables (IMPORTANT)

Inside `/backend`, create a `.env` file:

```
GOOGLE_API_KEY=your_key_here
```

⚠️ Never commit `.env` to Git.

---

## 5. Run the FastAPI Backend

Inside `/backend`:

```sh
uvicorn main:app --reload --port 8000
```

Backend runs at:

```
http://localhost:8000
```

API docs:

```
http://localhost:8000/docs
```

---

# 🧠 How AI Agents Work

### 🏋️ Workout Agent

* Generates 7-day routine
* Adapts to user goal
* Uses time availability
* Morning/evening preference

### 🥗 Diet Agent

* Veg / Non-veg diet plan
* Indian-friendly simple meals
* 7-day structure

Agents collaborate via `generator.py`.


# 🎨 Run The Streamlit Frontend

Install required packages:

```sh
uv pip install streamlit requests
```

Then:

```sh
cd frontend
streamlit run Home.py
```

Frontend runs at:

```
http://localhost:8501
```

---

# 🖥️ Frontend Pages

### 1️⃣ **Onboarding Page**

→ Inputs user data
→ Calls backend
→ Saves plan

### 2️⃣ **Your Plan Page**

→ Displays diet + workout plan

### 3️⃣ **Dashboard Page**

→ Checkbox: Workout completed
→ Checkbox: Diet followed
→ Shows progress %

---

# 🧪 Testing the Backend with curl

### Generate a Plan:

```sh
curl -X POST http://localhost:8000/generate-plan \
-H "Content-Type: application/json" \
-d '{"goal":"lose weight","height":170,"weight":70,"time":30,"preference":"morning","diet_type":"veg"}'
```

---

# 🚀 Future Improvements

* AI chat fitness coach
* Wearable integration (steps/calories)
* Dynamic calorie macro calculator
* Export plan as PDF
* Personalized workout music playlist

---

# ❤️ Contributors

**Team Fitness-AI**
Tech Used: CrewAI, Google Gemini, FastAPI, Streamlit


