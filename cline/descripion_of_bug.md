# LaTeX Resume Compilation Bug

## Issue Description

When attempting to compile the main.tex file in the root directory, we encounter two critical errors:

1. Missing `curve.cls` file: The LaTeX compiler cannot find the custom document class file required by the resume template.
2. Multiple `\documentclass` commands: There's a conflict because both the main.tex file and the included cv-llt.tex file contain `\documentclass` commands.

## Relevant Code

### main.tex (Root Directory)
```latex
% Main entry point for Overleaf
% This file inputs the academic CV file from the tech_education_2025-04-09 directory

\input{resumes/tech_education_2025-04-09/cv-llt.tex}
```

### resumes/tech_education_2025-04-09/cv-llt.tex (First Few Lines)
```latex
%%%%%%%%%%%%%%%
% This CV example/template is based on my own
% CV which I (lamely attempted) to clean up, so that
% it's less of an eyesore and easier for others to use.
%
% LianTze Lim (liantze@gmail.com)
% 23 Oct, 2022
% 24 Aug, 2024 -- Updated X (Twitter) icon
\documentclass[a4paper,skipsamekey,11pt,english]{curve}

% Uncomment to enable Chinese; needs XeLaTeX
% \usepackage{ctex}


% Most commands and style definitions are in settings.sty.
\usepackage{settings}

% Change the fonts if you want
\ifxetexorluatex % If you're using XeLaTeX or LuaLaTeX
  \usepackage{fontspec} 
  %% You can use \setmainfont etc; I'm just using these font packages here because they provide OpenType fonts for use by XeLaTeX/LuaLaTeX anyway
  \usepackage[p,osf,swashQ]{cochineal}
  \usepackage[medium,bold]{cabin}
  \usepackage[varqu,varl,scale=0.9]{zi4}
\else % If you're using pdfLaTeX or latex
  \usepackage[T1]{fontenc}
  \usepackage[p,osf,swashQ]{cochineal}
  \usepackage{cabin}
  \usepackage[varqu,varl,scale=0.9]{zi4}
\fi
```

## Error Messages

When running `pdflatex main.tex`, we get the following errors:

```
! LaTeX Error: File `curve.cls' not found.

Type X to quit or <RETURN> to proceed,
or enter new name. (Default extension: cls)
```

And if we try to continue:

```
! LaTeX Error: Two \documentclass or \documentstyle commands.

See the LaTeX manual or LaTeX Companion for explanation.
Type  H <return>  for immediate help.
 ...                                              
                                                  
l.9 ...entclass[a4paper,skipsamekey,11pt,english]{
                                                  curve}
```

## Possible Solutions

1. **Find or create the missing curve.cls file**:
   - Check if it's available in the example directory
   - Look for it in the LaTeX distribution
   - Create it based on the template requirements

2. **Fix the document structure**:
   - Option A: Make main.tex a proper LaTeX document with its own \documentclass and include content from cv-llt.tex without its preamble
   - Option B: Use cv-llt.tex directly as the main document and remove main.tex
   - Option C: Restructure main.tex to only include the content portion of cv-llt.tex, not its preamble

The most straightforward solution might be to compile the cv-llt.tex file directly instead of using main.tex as an intermediary, assuming we can locate or create the curve.cls file.
