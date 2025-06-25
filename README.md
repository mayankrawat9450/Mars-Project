# 📘 Automated Metadata Generator

This project builds a web-based system to automatically extract and generate semantic metadata from various document types such as PDF, DOCX, TXT, and image files using OCR.

## 🚀 Features

- 📤 Upload document (PDF, DOCX, TXT, or image)
- 📄 Extracts raw content using OCR/text parsing
- 🧠 Generates:
  - Document Title
  - Word Count
  - Language Detection
  - First Few Lines (Preview)
  - Abstractive Summary (via Transformers)
  - Top Keywords (TF-IDF)
  - Named Entities (Person, Organization, Location)
- 📥 Download metadata as a `.json` file
- 🌐 Simple Web UI using Flask + HTML/CSS
- ✅ Works in Google Colab via `pyngrok`

## 🧠 Technologies Used

| Task                     | Technology                    |
|--------------------------|-------------------------------|
| Text Extraction          | `pdfplumber`, `python-docx`, `pytesseract` |
| OCR for images           | `Tesseract`                   |
| Abstractive Summarization| `Transformers (BART)`         |
| Keyword Extraction       | `TF-IDF` from `scikit-learn`  |
| Language Detection       | `langdetect`                  |
| Named Entity Recognition | `spaCy`                       |
| Web Framework            | `Flask`, `Jinja2`             |
| Deployment (Colab)       | `pyngrok`                     |

## 📦 Installation

### ✅ In Google Colab

Just copy-paste the cells from the Colab notebook or use the `.ipynb` version (if available). Run each cell in order.

### 🖥️ Locally (optional)

```bash
pip install flask flask-cors transformers scikit-learn pdfplumber python-docx pytesseract langdetect spacy
python -m spacy download en_core_web_sm
```

Also install [Tesseract OCR](https://github.com/tesseract-ocr/tesseract) on your system if working with images.

## 🧪 How to Use

1. Upload a `.pdf`, `.docx`, `.txt`, or image file.
2. The app will:
   - Extract content
   - Generate summary, keywords, etc.
3. View results in the browser.
4. Download the JSON metadata.

## 🖼️ Sample Output

```json
{
  "title": "report.docx",
  "word_count": 672,
  "language": "en",
  "preview": "Executive Summary:...",
  "summary": "This document outlines...",
  "keywords": ["project", "development", "model"],
  "named_entities": ["India", "Google", "Python"]
}
```

## 📁 Project Structure

```
├── app.py / main.py          # Flask app logic
├── templates/
│   └── index.html            # Web interface
├── static/
│   └── style.css             # Styling
├── uploads/                  # Uploaded documents
├── metadata.json             # Downloadable result
├── README.md                 # This file
```

## 🙌 Acknowledgments

- 🤗 HuggingFace Transformers
- 📚 spaCy NLP
- 🧠 Scikit-learn
- 🖼️ Tesseract OCR
- 🔌 pyngrok


