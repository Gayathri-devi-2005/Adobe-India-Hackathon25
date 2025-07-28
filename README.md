# Adobe India Hackathon 2025 – Submission

This repository contains solutions for both **Round 1A** and **Round 1B** of Adobe’s “Connecting the Dots” Hackathon 2025.

---

## 🔹 CHALLENGE_1A – PDF Outline Extractor

### 🧠 Description

Extracts hierarchical outlines (H1, H2, H3 headings) from PDF documents using Python and PyMuPDF.  
Outputs a structured JSON file listing document titles, section headings, and their page numbers.

### 📁 Folder Structure

```
CHALLENGE_1A/
├── main.py
├── utils.py
├── Dockerfile
├── requirements.txt
├── input/        # PDF input files
└── output/       # JSON output files
```

### 🚀 How to Run (Docker)

```bash
docker build --platform linux/amd64 -t pdf_outline_extractor .
docker run --rm \
  -v ${PWD}/input:/app/input \
  -v ${PWD}/output:/app/output \
  --network none pdf_outline_extractor
```

📌 On Windows CMD, use `%cd%` instead of `${PWD}`

---

## 🔹 CHALLENGE_1B – Persona-Driven Document Intelligence

### 🧠 Description

Given a persona and a task (job-to-be-done), the system:
- Analyzes multiple PDFs
- Extracts relevant sections
- Ranks and returns them in `challenge1b_output.json`

### 📁 Folder Structure

```
CHALLENGE_1B/
├── Collection1/
│   ├── PDFs/
│   ├── challenge1b_input.json
│   └── challenge1b_output.json
├── Collection2/
├── Collection3/
├── main.py
├── utils.py
├── Dockerfile
├── requirements.txt
└── approach_explanation.md
```

### 🚀 How to Run (Docker)

```bash
docker build --platform linux/amd64 -t adobe1b:final .
docker run --rm -v $(pwd)/CHALLENGE_1B:/app --network none adobe1b:final
```

---

## ⚙️ Dependencies

Install locally (if not using Docker):

```bash
pip install -r requirements.txt
```

Main packages:
- `PyMuPDF (fitz)`
- `sentence-transformers`
- `scikit-learn`
- `numpy`
- `json`, `os`, `re`

---

## ✅ Output Formats

### 1A Output (outline JSON)
```json
{
  "title": "sample",
  "outline": [
    {
      "level": "H1",
      "text": "1. Introduction to AI",
      "page": 0
    },
    {
      "level": "H2",
      "text": "1.1 Neural Networks",
      "page": 1
    }
  ]
}
```

### 1B Output (persona-relevant JSON)
Structured output with:
- Persona metadata
- Ranked relevant content
- Refined section summaries

---

## 👩‍💻 Developed By

**Gayathri Devi Yaragarla**  
Participant – Adobe India Hackathon 2025 (Rounds 1A & 1B)

---

## 📄 License

This project is submitted for Adobe’s India Hackathon 2025. All rights reserved.
