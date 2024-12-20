# README: Description of Python Scripts

This repository contains three Python scripts that interact with machine learning models to analyze and process medical data, particularly ECG images, for diagnosing atrial fibrillation (AFib) and related tasks.

## 1. `copy_of_qwentest.py`

### Description:
This script interacts with the Hugging Face API to analyze images and generate descriptive text. It uses an image URL and a provided prompt to query a language model for a description of the image.

- **Key Operations**:
  - Sends a request to a Hugging Face model with an image URL and a text prompt.
  - Handles the response and outputs the generated text.
  - Converts images into Base64 encoding for API compatibility.
  - Analyzes ECG images by querying a model about potential AFib diagnoses (based on user-provided ECG images).
  - Sends Base64-encoded images or image URLs to the model for analysis.

### Requirements:
- Python libraries: `requests`, `transformers`
- Access to Hugging Face API

---

## 2. `copy_of_gpttest.py`

### Description:
This script performs operations on medical documents (images and PDFs) related to ECG readings. It involves reading, extracting text from PDFs (including OCR functionality), and categorizing ECG images into AFib and non-AFib categories based on the extracted text.

- **Key Operations**:
  - Extracts text from PDF documents using `PyPDF2` and OCR (`pytesseract`).
  - Analyzes the extracted text to detect the presence of "Atrial Fibrillation" or "Rhythm" and categorizes the corresponding images.
  - Moves the categorized images into appropriate folders for AFib and non-AFib cases.
  - Includes functionality to process and analyze images by converting them to a format suitable for LLMs (Large Language Models).

### Requirements:
- Python libraries: `PyPDF2`, `pytesseract`, `pdf2image`
- Dependencies for OCR (`poppler-utils`, `tesseract-ocr`)

---

## 3. `copy_of_llamatest.py`

### Description:
This script uses a Hugging Face model called "Llama-3.2-11B-Vision-Instruct" to process and analyze ECG images. It categorizes images based on AFib diagnoses and evaluates them step-by-step using pre-defined prompts.

- **Key Operations**:
  - Sends ECG image URLs to the Llama model for analysis.
  - Uses specific prompts to query the model for an AFib diagnosis, confidence level, and other related ECG features (e.g., P waves, QRS complex morphology).
  - Outputs the results in structured JSON format.
  - Supports different types of ECG analysis (AFib vs. non-AFib) with multiple prompts.
  - Organizes the responses and saves them as JSON files for further analysis.

### Requirements:
- Python libraries: `json`, `huggingface_hub`
- Hugging Face API key for accessing models and inference
