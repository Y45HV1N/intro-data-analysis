# Understanding and analyzing social and behavioral data

A Quarto book introducing R for the analysis of social and behavioral data, written for complete beginners.

## How to render the book locally

You will need:

- R (≥ 4.2) and RStudio
- Quarto CLI (≥ 1.4) — comes bundled with recent RStudio versions, or install from <https://quarto.org/docs/get-started/>
- The R package `webexercises`

Install the R package:

```r
install.packages("webexercises")
```

From the project root, render the book with:

```bash
quarto render
```

To preview while editing:

```bash
quarto preview
```

The rendered HTML lives in `_book/`. This folder is git-ignored on the `main` branch and is published to the `gh-pages` branch by GitHub Actions on every push.

## How publishing to GitHub Pages works

1. The first time, run `quarto publish gh-pages` locally. This creates the `gh-pages` branch and pushes the rendered site there.
2. After that, every push to `main` triggers `.github/workflows/publish.yml`, which re-renders the book and updates `gh-pages` automatically.
3. In your repo settings, under **Pages**, set the source to the `gh-pages` branch (root). The book will be live at `https://USERNAME.github.io/REPO/`.

## Project structure

```
.
├── _quarto.yml              # Book configuration: title, parts, chapters, formatting
├── index.qmd                # Preface (book home page)
├── 01-basics-r.qmd          # Chapter 1
├── 02-r-vs-rstudio.qmd      # Chapter 2
├── 03-files-and-environment.qmd
├── 04-projects-and-sessions.qmd
├── 05-objects-and-functions.qmd
├── 06-operations-and-packages.qmd
├── 07-recap.qmd
├── include/                 # webexercises CSS and JS (added by add_to_quarto)
│   ├── webex.css
│   └── webex.js
├── .github/workflows/       # GitHub Actions for auto-publishing
└── .gitignore
```
