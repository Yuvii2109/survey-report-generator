# EDXSO Student Well-Being Report Generator

![Python](https://img.shields.io/badge/Python-3.9%2B-blue)
![Streamlit](https://img.shields.io/badge/Streamlit-1.31.0-FF4B4B)
![Gemini AI](https://img.shields.io/badge/AI-Google%20Gemini-8E75B2)

## Overview

The **EDXSO Survey Report Generator** is a data processing and reporting tool designed to automate the creation of "Gold Standard" Student Well-Being Reports. 

It takes raw survey data (Excel/CSV), calculates stress metrics based on a specific psychometric scoring framework, and uses **Google's Gemini AI** to generate qualitative insights, executive summaries, and recommendations tailored to each school's unique data profile.

The output is a downloadable ZIP file containing high-fidelity, render-ready HTML reports that match strict design guidelines (Tailwind CSS).

## Key Features

* **Bulk Processing:** Upload a single Excel file containing data for hundreds of schools and generate individual reports for all of them in seconds.
* **Psychometric Scoring:** Automatically calculates:
    * Stress Categories (Balanced, Mild, Moderate, High, Severe).
    * Resilience Scores (via Reverse Scoring logic).
    * Key Indicators (Exam Anxiety, Parental Pressure, Support Accessibility).
* **AI-Powered Insights:** Uses the Gemini API to write unique *Executive Summaries* and *Strategic Interpretations* for each school, comparing their specific metrics against National Benchmarks.
* **High-Fidelity Output:** Generates HTML reports that preserve exact CSS styling, responsiveness, and layout requirements.
* **Secure:** API keys are input at runtime and are never stored.

## Quick Start (Local)

### Prerequisites
* Python 3.8 or higher
* A Google Gemini API Key (Optional, but required for AI text generation)

### Installation

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/Yuvii2109/survey-report-generator.git
    cd survey-report-generator
    ```

2.  **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

3.  **Run the application:**
    ```bash
    streamlit run app.py
    ```

4.  **Open your browser:**
    The app will usually open automatically at `http://localhost:8501`.

## Deployment (Streamlit Cloud)

This app is optimized for [Streamlit Community Cloud](https://streamlit.io/cloud).

1.  Push this code to a public GitHub repository.
2.  Log in to Streamlit Cloud.
3.  Click **"New App"** and select your repository.
4.  Click **"Deploy"**.

## Data Format Requirements

The application expects a CSV or Excel file with the following structure:
* **School Identifier:** A column named `sname` (Case sensitive).
* **Survey Questions:** 20 Columns representing the diagnostic statements (Likert Scale: Never, Rarely, Sometimes, Often, Always).
* **Metadata:** Timestamps, etc. (Optional, but standard export format expected).

**Note:** Questions 1-16 are standard scoring; Questions 17-20 are reverse-scored for resilience.

## Tech Stack

* **Frontend/UI:** Streamlit
* **Data Processing:** Pandas, NumPy
* **AI/LLM:** Google Generative AI (Gemini Pro)
* **Templating:** Python String Manipulation (HTML Injection)
* **Styling:** Tailwind CSS (Injected via CDN in reports)

## Privacy & Security

* **Data Processing:** All data processing happens in memory. No student data is saved to a database.
* **API Keys:** API keys entered in the UI are used strictly for the session and are not logged.

---
*Built for EDXSO K12 Education Excellence Solutions.*
