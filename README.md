# Automatic Paper Checker

An automated system for analyzing and comparing student handwritten papers with teacher answer sheets using OCR, NLP, and computer vision techniques.

## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [How It Works](#how-it-works)
- [Future Enhancements](#future-enhancements)

## Overview

The Automatic Paper Checker is a comprehensive solution designed to automate the process of checking student papers by comparing them against teacher answer sheets. It utilizes OCR technology to extract handwritten text, processes it using NLP techniques, and provides semantic similarity scores.

## Features

- **Handwriting Recognition**: Extracts text from handwritten images using Tesseract OCR
- **Image Preprocessing**: Applies adaptive thresholding and contour detection for better OCR results
- **Sentiment Analysis**: Determines the sentiment of the extracted text using NLTK's VADER
- **Semantic Similarity**: Calculates similarity between student and teacher responses using spaCy
- **Web Interface**: React-based frontend for easy file upload and result visualization
- **Flask Backend**: RESTful API for processing images and returning analysis results

## Tech Stack

- **Frontend**: React
- **Backend**: Flask (Python)
- **OCR**: PyTesseract
- **NLP Processing**: 
  - spaCy (for text processing and similarity)
  - NLTK (for sentiment analysis)
- **Computer Vision**: OpenCV
- **Jupyter Notebook**: For model development and testing

## Installation

### Prerequisites
- Python 3.8+
- Node.js and npm
- Tesseract-OCR installed on your system

### Backend Setup

1. Clone the repository:
```bash
git clone https://github.com/regnROK/AutoGrader.git
cd AutoGrader
```

2. Create a virtual environment and activate it:
```bash
python -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate
```

3. Install required Python packages:
```bash
pip install pytesseract opencv-python pillow spacy nltk flask
```

4. Download required spaCy and NLTK models:
```bash
python -m spacy download en_core_web_sm
python -m nltk.downloader vader_lexicon
```

### Frontend Setup

1. Navigate to the frontend directory:
```bash
cd frontend
```

2. Install npm dependencies:
```bash
npm install
```

## Usage

1. Start the Flask backend:
```bash
python app.py
```

2. In a separate terminal, start the React frontend:
```bash
cd frontend
npm start
```

3. Open your browser and navigate to `http://localhost:3000`

4. Upload a student paper and a teacher answer sheet using the provided interface

5. View the analysis results including:
   - Extracted text from both documents
   - Sentiment analysis
   - Semantic similarity score

## Project Structure

```
automatic-paper-checker/
├── Complete_Model.ipynb     # Jupyter notebook with core functionality
├── app.py                   # Flask backend
├── frontend/               # React frontend
│   ├── public/
│   ├── src/
│   │   ├── components/
│   │   ├── App.js
│   │   └── index.js
│   └── package.json
├── requirements.txt        # Python dependencies
└── README.md
```

## How It Works

1. **Image Preprocessing**:
   - Converts images to grayscale
   - Applies adaptive thresholding
   - Detects contours for better character recognition

2. **OCR Processing**:
   - Uses Tesseract to extract text from preprocessed images
   - Configured with Page Segmentation Mode 6 for uniform text blocks

3. **NLP Analysis**:
   - Tokenizes extracted text using spaCy
   - Performs sentiment analysis using NLTK's VADER
   - Calculates semantic similarity between student and teacher responses

4. **Result Generation**:
   - Returns extracted text, sentiment scores, and similarity metrics

## Future Enhancements

- Support for multiple languages
- Advanced error detection and correction
- Integration with Learning Management Systems (LMS)
- Support for typed documents and mixed content (handwritten + typed)
- Machine learning-based handwriting recognition improvement
- Batch processing capabilities

## License

This project is licensed under the MIT License - see the LICENSE file for details.
