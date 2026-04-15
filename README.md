# wimpy-paper

A Quarto + Typst manuscript template for academic papers. Built for political
science workflows (APSA citation style by default) but easily retargeted for
other disciplines.

- **Fast** — Typst renders in a fraction of the time LaTeX takes
- **Clean defaults** — sensible typography, margins, and spacing out of the box
- **Just one source file** — `manuscript.qmd` holds YAML + prose + code chunks

## Requirements

| Tool   | Minimum version | Notes                                                      |
|--------|-----------------|------------------------------------------------------------|
| Quarto | **1.7.0+**      | Typst support + extensions. Check with `quarto --version`  |
| R      | Any recent      | Only if you use R code chunks — otherwise not required     |
| Fonts  | Optional        | Template calls Minion Pro / Myriad Pro; see below for swap |

Typst itself is bundled with Quarto 1.5+, so nothing separate to install.

### Fonts (optional)

The template specifies Minion Pro (body) and Myriad Pro (headings). If you
don't have those installed, either:

- **Swap them** — edit `_extensions/manuscript/typst-template.typ` and change
  the `#set text(font: ...)` lines to a font you have (e.g. `"Times New Roman"`
  or `"Charter"`), **or**
- **Override from YAML** — set `mainfont:` in the document's YAML header.

If a specified font is missing, Typst falls back to a default and emits a
warning during render.

## Install

### Option 1 — `quarto use template` (recommended)

From the folder where you want your new paper's directory created:

```bash
quarto use template cwimpy/wimpy-paper
```

Quarto prompts for a directory name, copies the template files in, and you're
ready to edit `manuscript.qmd`.

### Option 2 — Clone directly

```bash
git clone https://github.com/cwimpy/wimpy-paper.git my-new-paper
cd my-new-paper
rm -rf .git      # drop template's history
git init         # start fresh
```

### Option 3 — Download ZIP

Grab the latest from
[github.com/cwimpy/wimpy-paper](https://github.com/cwimpy/wimpy-paper) via the
green **Code → Download ZIP** button.

## Render

```bash
quarto render manuscript.qmd
```

Or use the **Render** button in RStudio / VS Code / Positron. Output is
`manuscript.pdf` in the same directory.

## Customize

| What                  | Where                                                             |
|-----------------------|-------------------------------------------------------------------|
| Fonts                 | `_extensions/manuscript/typst-template.typ`                       |
| Line spacing, margins | `_extensions/manuscript/typst-template.typ` (`leading`, `margin`) |
| Citation style        | Swap `apsa.csl` for any CSL file; update YAML                     |
| TOC                   | Uncomment `toc: true` in `manuscript.qmd` YAML                    |
| Section numbers       | Uncomment `section-numbering: "1.1"` in YAML                      |
| Bibliography          | Edit `references.bib` (or point YAML to another file)             |

## Structure

```
wimpy-paper/
├── _extensions/
│   └── manuscript/          # Typst format extension
│       ├── _extension.yml
│       ├── typst-template.typ
│       ├── typst-show.typ
│       └── biblio.typ
├── manuscript.qmd           # Main document — edit this
├── references.bib           # Bibliography
└── apsa.csl                 # Citation style
```

## License

MIT — use it, fork it, adapt it. See [LICENSE](LICENSE).
