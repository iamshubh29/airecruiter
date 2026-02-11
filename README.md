# RecruiterAI: Intelligent Voice-First Recruitment Platform

RecruiterAI is a high-performance, full-stack application designed to streamline the technical hiring process. By leveraging **Generative AI** and **Voice AI agents**, the platform automates candidate screening, generates role-specific technical assessments, and provides real-time feedback for recruiters.

## 🚀 Key Features
* **Dynamic AI Question Generation**: Utilizes **OpenRouter (GPT-3.5-Turbo)** to generate tailored interview questions based on job titles, descriptions, and duration.
* **Voice-AI Interaction**: Integrated with **Vapi AI** to conduct realistic, low-latency voice interviews.
* **Automated Feedback Loop**: Features a specialized AI feedback API to analyze candidate performance and provide scoring.
* **Enterprise Dashboard**: Built with **Radix UI** and **Tailwind CSS** for a responsive, accessible interface to manage interviews and candidates.
* **Real-time Persistence**: Powered by **Supabase** (PostgreSQL) for secure, real-time data storage and candidate tracking.

## 🛠️ Tech Stack
* **Framework**: Next.js 15 (App Router)
* **Language**: JavaScript / React 18
* **Database & Auth**: Supabase
* **AI Integration**: OpenRouter (LLM Orchestration) & Vapi AI (Voice)
* **Styling**: Tailwind CSS 4 & Framer Motion (Animations)
* **State Management**: React Context API (User and Interview Data)

## 🏗️ Architecture Overview

### **AI Pipeline (`/app/api/ai-model/route.js`)**
The core intelligence layer uses a modular API route that transforms job metadata into structured prompts. It handles:
1. **Prompt Engineering**: Injecting job roles and durations into specialized templates defined in `Constants.jsx`.
2. **Model Agnosticism**: Utilizing OpenRouter to ensure flexibility across different LLM providers like OpenAI and Gemini.
3. **Error Handling**: Robust try-catch blocks to manage API latencies and failures.

### **Database Layer (`/services/supabaseClient.js`)**
The backend utilizes a **Backend-as-a-Service (BaaS)** approach with Supabase to manage:
* Candidate interview logs and generated question sets.
* Secure environment-variable-based authentication for sensitive API keys.

