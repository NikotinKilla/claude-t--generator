
# Claude Test Case Generator

A lightweight tool that uses Anthropic Claude API to automatically generate structured QA test cases from a documentation file.  
Implemented and tested in Google Colab.

## 📂 Project Files

- `Test_case generator.ipynb` — main notebook that handles Claude API interaction and output generation  
- `exit_button_spec.md` — example design document for a mobile game feature  
- `Result.xlsx` — generated test cases in Excel format  
- `README.md` — this description

## 🔍 Overview

This project demonstrates how to automate the creation of QA test cases using LLMs.  
You upload a functional specification in `.md` or `.txt`, and the script sends it to Claude (Opus 4). Claude responds with a markdown-formatted table, which is parsed and saved as `.xlsx`.

## ✅ Features

- Claude Opus 4 model support via API
- Prompt-based generation of test cases
- Markdown parsing using `pandas`
- Excel export (`.xlsx`)
- No local setup — runs in Google Colab

## 🛠 How to Use

1. Open `Test_case generator.ipynb` in [Google Colab](https://colab.research.google.com/).
2. Upload your `.md` or `.txt` spec file when prompted.
3. Enter your Claude API key.
4. Run the notebook step by step.
5. The result will be saved as `Result.xlsx` and offered for download.

## 📤 Prompt Template

```
You are a QA engineer. Based on the following documentation, generate test cases
in markdown table format with the columns: ID | Title | Preconditions | Steps | Expected Result.
```

## 📄 Example Input

See `exit_button_spec.md` for a sample input describing a UI feature in a mobile game.

## 📈 Output Format

`Result.xlsx` contains a structured table with the following columns:
- ID
- Title
- Preconditions
- Steps
- Expected Result

## 🔐 Requirements

- Claude API key (get one from https://console.anthropic.com/)
- Internet connection (Google Colab)

## 📄 License

MIT License
