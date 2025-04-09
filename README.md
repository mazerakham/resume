# Resume Collection

This directory contains multiple versions of resumes tailored for different purposes.

## Available Resumes

- `tech_2025-04-09`: Technical resume focusing on software engineering experience
- `tech_education_2025-04-09`: Academic resume tailored for a head of department position in mathematics and computer science

## Overleaf Instructions

When importing this project into Overleaf:

1. The main entry point is `main.tex` in this directory, which currently imports the academic resume
2. A `.latexmkrc` file is included to help Overleaf identify the main file
3. To switch between different resume versions, modify the `\input{}` command in `main.tex`

## File Structure

- `main.tex`: Main LaTeX file that inputs the desired resume version
- `tech_2025-04-09/`: Directory containing the technical resume files
- `tech_education_2025-04-09/`: Directory containing the academic resume files

## Compilation

Compile using pdfLaTeX.
