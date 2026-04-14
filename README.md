
# MO903-1s2026-Final-Presentation

Final presentation for MO903 (Scientific Writing) at the Institute of Computing (IC) - UNICAMP, 1st Semester 2026. This project presents an AI-Augmented Framework for Personalized Student Timetabling.

## 🛠 Local Setup

This project is designed for a terminal-based LaTeX environment on Arch Linux (Omarchy), utilizing a modular structure to ensure full control over the build pipeline.

### Installation

To install the required dependencies, run:

```bash
sudo pacman -S texlive-basic texlive-latexextra texlive-fontsrecommended \
               texlive-fontsextra texlive-bibtexextra texlive-plaingeneric \
               texlive-binextra texlive-science biber zathura
```

### Build Instructions

The following command prepares the output directory, sets the search paths for TeX components, and launches `latexmk` in continuous preview mode with Zathura:

```bash
mkdir -p output && find output -type f -delete && \
trap 'pkill -P $$ zathura' EXIT; \
BIBINPUTS="./src/sections/:" \
BSTINPUTS="./src/sections/:" \
TEXINPUTS="./src//:./src/img//:" \
latexmk -pdf -pvc -e '$pdf_previewer="zathura %S"' -outdir=output src/main.tex
```

## 📂 Project Structure

The project uses the polished IC Beamer template with the Gillius (Gill Sans) font set and a modular content layout:

```text
.
├── README.md               # Setup and project info
└── src/
    ├── main.tex            # Main entry point
    ├── structure/
    │   ├── engine.tex      # Beamer theme logic and Gillius font config
    │   └── metadata.tex    # Presentation metadata (Course, RA, Instructor)
    └── sections/           # Modular slide files
        ├── 00_title.tex
        ├── 01_intro.tex
        ├── 02_related.tex
        ├── 03_methodology.tex
        ├── 04_outcomes.tex
        └── 99_questions.tex
```

## 🚀 Last Working Code (LWC)

To provide a clean dump of the current source code for LLM context or debugging, run:

```bash
find src -name "*.tex" | sort -u | xargs tail -n +1
```
```

