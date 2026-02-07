# PDF Analysis with Gemini (LangChain)

A Python tool for automatic analysis of **scientific articles in PDF format** using **Google Gemini** via **LangChain**.  
The script supports both **single PDF analysis** and **batch processing of multiple PDFs**, with results saved to a CSV file.

> ⚠️ Note:  
> The source code and prompts are written in **Polish**, but this README is provided in English for international users.

---

## Features

- Load and process scientific PDF articles
- Content analysis using **Gemini 2.5 Flash**
- Automatic extraction of:
  - article objective
  - key technical concepts
  - main conclusions
- Language handling:
  - Polish articles → output in Polish
  - English articles → summarized in Polish (CSV mode) or EN + PL (single-file analysis)
- Export results to a **CSV file**
- Automatically skips already processed files

---

## Requirements

- Python **3.9+**
- Google AI Studio account with API key

---

## Environment Setup

Create a `.env` file in the project root:

```env
GOOGLE_API_KEY=your_google_api_key
```

## Configuration

Edit the following variables in the script:
```python
INPUT_PATH = "Articles/2007.00047v1.pdf"  
OUTPUT_FILE = "podsumowanie_bibliografii.csv"
model_name = "gemini-2.5-flash"
```

## Operating Modes

### Single PDF Analysis

If `INPUT_PATH` points to a file:

- Results are printed to the console
- Includes:
  - Research objective
  - 3 key technical concepts
  - Main conclusions
- English articles → English output followed by Polish translation

---

### Batch PDF Analysis

If `INPUT_PATH` points to a directory:

- Each PDF is analyzed separately
- Results are appended to `podsumowanie_bibliografii.csv`
- Previously processed files are automatically skipped

#### CSV File Contents

The output CSV file (`podsumowanie_bibliografii.csv`) contains the following columns:

| Column | Description |
|--------|------------|
| File | Name of the processed PDF |
| Title | Article title (original) |
| Author | Article author(s) (original) |
| Research Objective | Summary of the article’s objective |
| Keywords | 3–5 key technical concepts |
| Main Conclusions | Main conclusions from the article |


