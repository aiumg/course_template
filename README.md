# Course template

A ready-made project for building a self-study course website with RStudio and
Quarto, in the corporate design of Universitätsmedizin Göttingen. The course
itself, *Building a Course with This Template*, teaches how to use it: open
`course-template.Rproj` in RStudio, click **Render Website** in the Build tab, and
start with Chapter 1.

## Layout

| Path | Purpose |
|---|---|
| `index.qmd`, `01-…` to `08-….qmd` | Landing page and chapters |
| `_chapter-skeleton.qmd` | Empty chapter to copy (not built) |
| `glossary.qmd`, `references.qmd`, `references.bib` | Reference pages |
| `slides/` | Lecture slides (reveal.js) |
| `_quarto.yml` | Settings: title, chapter list, footer. Lines marked `CHANGE` |
| `assets/` | Theme (colours, fonts, logo placement), quiz styling and script |
| `images/` | Logo, favicon, pictures |
| `docs/` | Rendered website, created by Render Website. Not edited by hand |
| `.nojekyll` | Empty file needed by GitHub Pages; copied into `docs/` |

## Notes for maintainers

- The palette, type stack and logo placement come from the *Corporate Design
  Stylebook* (January 2025). The six brand colours are defined at the top of
  `assets/theme.scss`, and repeated in `assets/dark.scss` and `assets/slides.scss`
  because those files are compiled separately.
- Every variable in `theme.scss` carries `!default`. Keep it: it lets `dark.scss`
  override values regardless of the order in which Quarto stacks the files.
- No fonts or scripts are loaded from third-party servers.
- The quiz engine is `assets/quiz-include.html` plus `assets/quiz.css`. Grading
  runs in the reader's browser; nothing is recorded.
- The template contains no R code and needs no R packages.
- GitLab Pages needs a `.gitlab-ci.yml`, which differs per installation and is
  therefore not included. Chapter 8 has a minimal example for administrators.
