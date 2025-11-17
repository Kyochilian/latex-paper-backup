# LaTeX Paper Backup

GitHub repo for LaTeX paper writings.<br>
## Project Roadmap

| # | Task / Paper | Status | Start | Deadline | Notes |
|---|--------------|--------|-------|----------|-------|
| 1 | **paper** AViT-UNet | ✅ Done | 2025-07 | 2025-07 | Accepted in JuUESTC 2025 |
| 2 | **paper** MedSeg with Vision RWKV| 🔄 Writing | 2026-01 | 2025-11 | Now writing in LaTeX |
| 3 | **code** SpatailGlue| 📅 Planned | 2026-02 | 2025-11 | Target: recurrent |
| 4 | **paper** Cell clustering| 📅 Planned | 2026-02 | 2025-12 | research paper in Cell clustering |

Legend:  
✅ Done 🔄 In Progress 📅 Planned
<br>
**macOS + VS Code toolchain.**

## Directory Layout
``` markdown
TexDocuments/
├── .gitignore
├── .vscode/
│   ├── settings.json
│   └── latex-workshop.code-snippets
├── out/          # compiled PDF & aux files
├── pic/          # figures (pdf/png/eps)
├── src/          # source files
│   ├── main.tex
│   └── refs.bib
└── README.md     # this file
```

## Git Ignore List
```
.vscode/
.gitignore
.DS_Store
*.aux
*.log
*.fls
*.fdb_latexmk
*.synctex.gz
*.out
*.toc
*.bbl
*.blg
.DS_Store
```
> upload .PDF file.

## Required VS Code Extensions (macOS)

Install inside VS Code → Extensions (`⇧⌘X`):

| Extension ID               | Description                     |
| -------------------------- | ------------------------------- |
| `James-Yu.latex-workshop`  | LaTeX Workshop |
| `ms-vscode.vscode-json`    | Built-in JSON support           |

Optional but handy:

| Extension ID               | Description                     |
| -------------------------- | ------------------------------- |
| `streetsidesoftware.code-spell-checker` | Spell check |
| `jlelong.latex-workshop-snippets`       | Extra snippets |

## Minimal `.vscode/settings.json`

```json
{
    "latex-workshop.latex.outDir": "%WORKSPACE_FOLDER%/out",
    "latex-workshop.latex.tools": [
        {
            "name": "xelatex",
            "command": "xelatex",
            "args": [
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "-output-directory=%WORKSPACE_FOLDER%/out",
                "%DOCFILE%.tex"
            ]
        },
        {
            "name": "pdflatex",
            "command": "pdflatex",
            "args": [
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "-output-directory=%WORKSPACE_FOLDER%/out",
                "%DOCFILE%.tex"
            ]
        },
        {
            "name": "latexmk",
            "command": "latexmk",
            "args": [
                "-xelatex",
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "-output-directory=%WORKSPACE_FOLDER%/out",
                "%DOC%"
            ]
        },
        {
            "name": "bibtex",
            "command": "bibtex",
            "args": [
                "-output-directory=%WORKSPACE_FOLDER%/out",
                "%DOC%"
            ]
        }
    ],
    "latex-workshop.latex.recipes": [
        {
            "name": "XeLaTeX",
            "tools": [
                "xelatex"
            ]
        },
        {
            "name": "PDFLaTeX",
            "tools": [
                "pdflatex"
            ]
        },
        {
            "name": "BibTeX",
            "tools": [
                "bibtex"
            ]
        },
        {
            "name": "LaTeXmk",
            "tools": [
                "latexmk"
            ]
        },
        {
            "name": "xelatex -> bibtex -> bibtex -> xelatex -> xelatex",
            "tools": [
                "xelatex",
                "bibtex",
                "bibtex",
                "xelatex",
                "xelatex"
            ]
        },
        {
            "name": "pdflatex -> bibitex -> bibtex -> pdflatex -> pdflatex",
            "tools": [
                "pdflatex",
                "bibtex",
                "bibtex",
                "pdflatex",
                "pdflatex"
            ]
        }
    ],
    "latex-workshop.latex.clean.fileTypes": [
        "*.aux",
        "*.bbl",
        "*.blg",
        "*.idx",
        "*.ind",
        "*.lof",
        "*.lot",
        "*.out",
        "*.toc",
        "*.acn",
        "*.acr",
        "*.alg",
        "*.glg",
        "*.glo",
        "*.gls",
        "*.ist",
        "*.fls",
        "*.log",
        "*.fdb_latexmk"
    ],
    "latex-workshop.view.pdf.viewer": "tab",
    "latex-workshop.latex.autoBuild.run": "onSave",
    "latex-workshop.latex.autoClean.run": "never",
    "latex-workshop.showContextMenu": true,
    "latex-workshop.intellisense.package.enabled": true,
    "latex-workshop.message.error.show": false,
    "latex-workshop.message.warning.show": false,
    "latex-workshop.latex.recipe.default": "lastUsed",
    "latex-workshop.view.pdf.internal.synctex.keybinding": "double-click",
}
```