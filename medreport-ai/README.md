# AI-Powered Medical Report Analysis & Disease Risk Prediction

## Problem Statement
Medical reports such as blood test results, lipid profiles, and kidney/liver
function reports contain critical health indicators, but interpreting them
requires medical expertise that most patients don't have. As a result, early
warning signs of chronic conditions like diabetes, heart disease, and kidney
disease often go unnoticed until the disease progresses. This project proposes
an AI-powered system that can analyze medical reports (either manually entered
values or uploaded report files), extract relevant clinical parameters, and
predict the risk of diabetes, heart disease, and kidney disease using machine
learning — making health risk assessment faster, more accessible, and
understandable for non-experts.

## Objectives
1. Build a system that accepts patient medical data either via manual input or
   uploaded report files (PDF/image).
2. Extract relevant clinical parameters from uploaded reports using OCR/text
   parsing.
3. Preprocess and structure extracted/entered data into a standard format per
   disease.
4. Train and evaluate ML models to predict risk of diabetes, heart disease, and
   kidney disease.
5. Generate a clear, human-readable risk report/summary for the patient (not
   just a raw prediction).
6. Deploy the system as a web application accessible via browser.

## Diseases Covered
- Diabetes
- Heart Disease
- Kidney Disease

## Input Modes
- **Manual entry** — user types in clinical parameters directly.
- **Report upload** — user uploads a PDF or scanned image of a lab report;
  the system extracts values automatically via OCR + parsing.

## Tech Stack
| Layer | Technology | Purpose |
|---|---|---|
| Language | Python 3.10+ | Core development |
| Data handling | Pandas, NumPy | Structuring extracted/entered data |
| ML | scikit-learn, XGBoost | Risk prediction models |
| Report parsing | pdfplumber, PyPDF2, pytesseract, OpenCV | Extract text/values from PDF or scanned image reports |
| NLP (optional) | Regex, spaCy | Pull specific values (e.g. "Glucose: 145 mg/dL") out of unstructured report text |
| Visualization | Matplotlib, Seaborn | EDA & result charts |
| Model persistence | Joblib / Pickle | Save trained models |
| Web app / UI | Streamlit | Upload reports, show results |
| Version control | Git + GitHub | Source control |
| Notebook env | Jupyter Notebook | Experimentation |

## Project Structure
```
medreport-ai/
├── data/
│   ├── diabetes/            # diabetes dataset(s)
│   ├── heart_disease/       # heart disease dataset(s)
│   ├── kidney_disease/      # kidney disease dataset(s)
│   └── sample_reports/      # sample PDF/image reports for testing the parser
├── notebooks/                # EDA & model experimentation notebooks
├── src/
│   ├── diabetes/              # diabetes preprocessing + model code
│   ├── heart_disease/         # heart disease preprocessing + model code
│   ├── kidney_disease/        # kidney disease preprocessing + model code
│   └── report_parser/         # OCR + text extraction + value-parsing logic
├── models/                   # saved/trained model files (.pkl)
├── app/                      # Streamlit web application
├── docs/                     # project report, diagrams, presentation, phase notes
├── requirements.txt
├── .gitignore
└── README.md
```

## Roadmap
- **Phase 1** — Project Foundation *(current)*
- **Phase 2** — Data Collection & Preprocessing
- **Phase 3** — EDA & Feature Engineering
- **Phase 4** — Model Training & Evaluation
- **Phase 5** — Report Parsing Module (OCR + extraction)
- **Phase 6** — Web App Development (manual entry + report upload)
- **Phase 7** — Deployment & Documentation

## Setup
```bash
python -m venv venv
source venv/bin/activate   # Windows: venv\Scripts\activate
pip install -r requirements.txt
```

Note: OCR requires the Tesseract binary installed on your system separately
from the Python package:
- Ubuntu/Debian: `sudo apt-get install tesseract-ocr`
- macOS: `brew install tesseract`
- Windows: install from https://github.com/UB-Mannheim/tesseract/wiki

## Run the app (once built in later phases)
```bash
streamlit run app/app.py
```
