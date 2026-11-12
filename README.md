# MLPP Project – Keyword Extraction from Scanned Notices

## Overview

This project focuses on automatically extracting important keywords from scanned notices using Optical Character Recognition (OCR) and Natural Language Processing (NLP).

It compares two keyword extraction techniques:

- **TF-IDF:** A statistical approach that identifies important terms based on their frequency and importance across documents.
- **KeyBERT:** A semantic approach that uses sentence embeddings to identify meaningful keywords and keyphrases.

The project also evaluates both techniques against manually prepared ground-truth keywords and provides an interactive web interface using Gradio.

## Objectives

- Extract text from scanned notice images using OCR.
- Clean extracted text and remove recurring letterhead information.
- Identify important keywords using TF-IDF and KeyBERT.
- Compare keyword extraction performance using Precision, Recall and F1-score.
- Evaluate performance across different notice categories.
- Build an interactive interface for keyword extraction.

## Technologies Used

| Technology | Purpose |
|---|---|
| Python | Core programming language |
| OpenCV | Image preprocessing |
| Tesseract OCR | Text extraction from images |
| Pytesseract | Python interface for Tesseract |
| Scikit-learn | TF-IDF and evaluation metrics |
| KeyBERT | Semantic keyword extraction |
| Sentence Transformers | Text embeddings |
| Pandas | Data processing |
| Matplotlib | Performance visualization |
| Gradio | Interactive web interface |
| Google Colab | Development environment |

## Project Workflow

1. **Image Upload:** Upload scanned notice images and a ground-truth CSV/XLSX file.
2. **OCR Processing:** Convert images to grayscale, remove noise, apply Otsu thresholding and extract text using Tesseract.
3. **Text Cleaning:** Remove recurring letterhead information and normalize extracted text.
4. **Keyword Extraction:**
   - TF-IDF extracts statistically important words and phrases.
   - KeyBERT extracts semantically relevant keywords using the `all-MiniLM-L6-v2` model.
5. **Performance Evaluation:** Compare predicted keywords with ground-truth keywords using Precision, Recall and F1-score.
6. **Visualization:** Generate category-wise performance comparisons.
7. **Deployment Interface:** Use Gradio to create an interactive interface for processing individual notice images.

## Evaluation Metrics

The project uses three evaluation metrics:

- **Precision:** Measures how many extracted keywords are relevant.
- **Recall:** Measures how many relevant ground-truth keywords were successfully extracted.
- **F1-score:** Measures the harmonic mean of Precision and Recall.

Results are compared across TF-IDF and KeyBERT, including category-wise F1-score comparisons.

## Input Data

The notebook requires:

- Scanned notice images (`.jpg`, `.jpeg`, `.png`).
- A ground-truth dataset (`.csv` or `.xlsx`).

The ground-truth dataset should contain:

| Column | Description |
|---|---|
| file | Corresponding notice image filename |
| category | Notice category |
| truth | Manually prepared ground-truth keywords |

The notebook also supports the column aliases `file name` and `keywords`.

## Generated Outputs

The notebook generates:

- `keywords.csv` – Extracted keywords using TF-IDF and KeyBERT.
- `evaluation_results.csv` – Individual evaluation results.
- `evaluation_summary.csv` – Overall evaluation summary.
- `f1_by_category.png` – Category-wise F1-score comparison chart.

## How to Run

This notebook is designed for Google Colab.

1. Open the notebook in Google Colab.
2. Install the required dependencies and Tesseract OCR.
3. Upload the scanned notice images.
4. Upload the ground-truth CSV/XLSX file.
5. Execute the notebook cells sequentially.
6. Review the extracted keywords and evaluation results.
7. Access the Gradio interface for individual image processing.

## Installation

The notebook uses the following dependencies:

```bash
pip install pytesseract keybert sentence-transformers gradio
```

Additional libraries used include:

```bash
pip install opencv-python pandas scikit-learn matplotlib openpyxl
```

Tesseract OCR must also be installed and available to Pytesseract.

## Future Improvements

- Improve OCR accuracy for low-quality scanned documents.
- Support additional document formats.
- Experiment with other transformer-based keyword extraction models.
- Improve keyword extraction for multilingual notices.
- Develop a more scalable document-processing interface.


*This project explores the application of OCR, NLP and semantic text processing to automate keyword extraction and evaluation from scanned notices.*
