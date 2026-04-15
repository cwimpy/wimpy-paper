# wimpy-paper

A Quarto + Typst manuscript template for academic papers. Built for political
science (APSA citation style by default), but easy to retarget.

## Quickstart

### From GitHub (recommended)

```bash
quarto use template cwimpy/wimpy-paper
```

Quarto will copy the extension and template files into a new directory, prompt
for a directory name, and you're ready to open in RStudio.

### Local copy (offline)

```bash
cp -r ~/path/to/wimpy-paper ~/projects/my-new-paper
```

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
├── references.bib           # Replace with your project .bib file
└── apsa.csl                 # Citation style — swap as needed
```

## Render

```bash
quarto render manuscript.qmd
```

Or use the RStudio Render button.

## Customization

- **Fonts:** Minion Pro (body) and Myriad Pro (headings). Change in
  `_extensions/manuscript/typst-template.typ` or override via YAML `mainfont:`.
- **Citation style:** Swap `apsa.csl` for any CSL file and update
  `bibliographystyle:` in the YAML.
- **Spacing/margins:** Controlled in `typst-template.typ` — `leading` for line
  spacing, `margin` for page margins.
- **Section numbering:** Uncomment `section-numbering: "1.1"` in YAML.
- **TOC:** Uncomment `toc: true` in YAML.

## License

MIT. Use it, fork it, adapt it.
