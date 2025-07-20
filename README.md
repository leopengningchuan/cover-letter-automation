# coverletter-automation
A lightweight tool to auto-generate cover letters from structured data

## Table of Contents
- [Project Background](#project-background)
- [Project Goal](#project-goal)
- [File Structure](#file-structure)
- [Instructions](#instructions)
  - [1. Packages Used](#1-packages-used)
  - [2. Build Cover Letter Information Dictionary](#2-build-cover-letter-information-dictionary)
  - [3. DOCX Cover Letter with Placeholder Replacement](#3-docx-cover-letter-with-placeholder-replacement)
  - [4. Convert DOCX File to PDF File](#4-convert-docx-file-to-pdf-file)
- [Future Improvements](#future-improvements)
- [License](#license)

## Project Background
Writing personalized cover letters for each job application is essential but often time-consuming and repetitive. Many applicants struggle to maintain consistency and efficiency when tailoring content to multiple roles across different companies

This project addresses that challenge by automating the cover letter creation process. By inputting details like the company name and job description, users can quickly generate customized PDF cover letters—saving time while ensuring a professional and personalized result every time.

## Project Goal
This project aims to automate the generation of personal cover letters in PDF by using **Python Jupyter Notebook** and **Microsoft Word** based on the company name and job title to streamlines the application process and saves time during online job submissions.

## File Structure
Configuration & Metadata:
- `README.md` – project overview
- `LICENSE.txt` – license information
- `.gitignore` – git ignore config
- `.gitattributes` – git attributes config
- `.gitmodules` – git submodules config

Core Logic:
- [`utils`](https://github.com/leopengningchuan/personal_utils) – submodule used
- `coverletter_automation.ipynb` – main notebook for cover letter generation
- `cover_letter_prototype.docx` – DOCX cover letter template
- `skill_set.json` – cover letter skill sets information

## Instructions

### 1. Packages Used
- `datetime`: for data manipulation
- `os`: core Python libraries for basic system operations
- `dotenv`: for loading environment variables from a `.env` file
- `json`: for json file processing
- [`personal_utils.docx_manipulate`](https://github.com/leopengningchuan/personal_utils): for modifying DOCX files

### 2. Build Cover Letter Information Dictionary
By inputting the company name and job title, the program generates a structured Python dictionary containing all necessary placeholder values, including the current date in long format (e.g., `COMPANY`, `POSITION`, `LONG_DATE`). It also reads a `skill_set.json` file containing predefined skills and detailed descriptions. From this dataset, three relevant skills are selected—either manually or programmatically—and added to the dictionary using keys such as `SKILL_1`, `SKILL_DETAILS_1`, etc. This ensures the data is clean, well-formatted, and tailored for each job application, enabling accurate and consistent substitution in the cover letter template.

### 3. DOCX Cover Letter with Placeholder Replacement
The cover letter automation process uses `populate_docx_paragraph()` from the `utils.docx_manipulate` module to dynamically replace placeholders in a DOCX template using values from an cover letter dictionary.

For each cover letter entry, the script replaces matching placeholders within the DOCX template using the provided information. The generated document preserves the original formatting and layout, while the template itself remains unchanged to ensure consistency across all cover letters.

The `utils/` folder is included as a Git submodule and contains a reusable function library maintained in the [`personal_utils`](https://github.com/leopengningchuan/personal_utils). You can refer to that repository for detailed function documentation and personal notes.

### 4. Convert DOCX File to PDF File
After the cover letter is generated as a DOCX file, it is immediately converted into a PDF file for final output. Both the DOCX file and the PDF file will be kept for future use.

## Future Improvements
- **Skill Set Extraction**: Implement a function to parse job descriptions and automatically identify relevant skills to include in the cover letter.
- **Version History**: Store previously generated cover letters and log generation details in an XLSX file for future reference.

## License
This project is licensed under the MIT License - see the [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://github.com/leopengningchuan/coverletter-automation?tab=MIT-1-ov-file) file for details.
