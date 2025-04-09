# Overleaf Instructions for Resume Compilation

## Issue Summary

We encountered two main issues when trying to compile the resume locally:

1. Missing `curve.cls` file: The LaTeX compiler couldn't find the custom document class file required by the resume template.
2. Multiple `\documentclass` commands: There was a conflict because both the main.tex file and the included cv-llt.tex file contained `\documentclass` commands.

## Preparation for Overleaf

We've made the following changes to prepare the project for Overleaf:

1. Added a `.gitignore` file to ignore `.log` files
2. Removed `.log` files from git tracking
3. Generated the `curve.cls` file from the source files
4. Copied `settings.sty` to the root directory

## Uploading to Overleaf

When uploading to Overleaf, make sure to include the following files:

1. `main.tex` - The main entry point
2. `curve.cls` - The custom document class
3. `settings.sty` - The style definitions
4. The entire `resumes/tech_education_2025-04-09/` directory - Contains all the content files

## Overleaf Configuration

Overleaf should automatically detect `main.tex` as the main file to compile. If not, you can manually set it as the main file in the Overleaf project settings.

## Alternative Approaches

If you still encounter issues on Overleaf, consider these alternatives:

1. **Direct Compilation**: Instead of using `main.tex` as an intermediary, compile `resumes/tech_education_2025-04-09/cv-llt.tex` directly.

2. **Restructure main.tex**: Modify `main.tex` to be a proper LaTeX document with its own `\documentclass` command and include only the content portion of `cv-llt.tex`, not its preamble.

3. **Install Missing Packages**: If Overleaf reports missing packages, you can install them through Overleaf's package manager or by uploading the package files directly.

## Expected Result

Once properly set up on Overleaf, the compilation should produce a PDF of your resume with all the sections (education, employment, skills, publications, misc) properly formatted according to the CurVe class style.
