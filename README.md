# coverletter-automation
A lightweight tool to auto-generate cover letters from structured data

## Project Background
Writing personalized cover letters for each job application is essential but often time-consuming and repetitive. Many applicants struggle to maintain consistency and efficiency when tailoring content to multiple roles across different companies

This project addresses that challenge by automating the cover letter creation process. By inputting details like the company name and job description, users can quickly generate customized PDF cover letters—saving time while ensuring a professional and personalized result every time.

## Project Goal
This project aims to automate the generation of personal cover letters in PDF by using **Python Jupyter Notebook** and **Microsoft Word** based on the company name and job title to streamlines the application process and saves time during online job submissions.

## Table of Contents
- README.md
- LICENSE.txt
- [utils](https://github.com/leopengningchuan/personal_utils) (submodel)
- coverletter_automation.ipynb
- cover_letter_prototype.docx

## Instructions

### 1. Package Used
- `datetime`: for data manipulation
- [`personal_utils.docx_manipulate`](https://github.com/leopengningchuan/personal_utils): for modifying Word files

### 2. Build Cover Letter Information Dictionary
By inputting the company name and job title, the program generates a structured Python dictionary containing all necessary placeholder values, including the current date in long format (e.g., `COMPANY`, `POSITION`, `LONG_DATE`). This ensures that the data is clean, well-formatted, and ready for accurate and consistent substitution during document generation.

### 3. Word Cover Letter with Placeholder Replacement
The cover letter automation process uses `populate_docx_paragraph()` from the `utils.docx_manipulate` module to dynamically replace placeholders in a Word docx template using values from an cover letter dictionary.

For each cover letter entry, the script replaces matching placeholders within the Word template using the provided information. The generated document preserves the original formatting and layout, while the template itself remains unchanged to ensure consistency across all cover letters.

The `utils/` folder is included as a Git submodule and contains a reusable function library maintained in the [`personal_utils`](https://github.com/leopengningchuan/personal_utils). You can refer to that repository for detailed function documentation and personal notes.

### 4. Convert Word File to PDF File
After the cover letter is generated as a Word file, it is immediately converted into a PDF file for final output. Both the Word file and the PDF file will be kept for future use.

## Future Improvements


## License
This project is licensed under the MIT License - see the [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://github.com/leopengningchuan/coverletter-automation?tab=MIT-1-ov-file) file for details.
