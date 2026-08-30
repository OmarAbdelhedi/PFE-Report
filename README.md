# PFE report — build instructions

Compiled and verified on TeX Live 2023 with `pdflatex`.

## 1. Install

You need a **full** TeX distribution, not a minimal one — the report pulls in
Arabic support, two bibliographies and TikZ.

**Windows** — [MiKTeX](https://miktex.org/download) (choose "install missing
packages on the fly: Yes") or [TeX Live](https://tug.org/texlive/).

**macOS** — [MacTeX](https://tug.org/mactex/) (the full installer, not
BasicTeX).

**Linux (Debian/Ubuntu)** — the minimal set that covers this document:

```bash
sudo apt install texlive-latex-recommended texlive-latex-extra \
                 texlive-lang-arabic texlive-bibtex-extra \
                 texlive-science texlive-pictures \
                 cm-super latexmk
```

`texlive-lang-arabic` is the one people forget — it provides **arabtex**, which
the cover page needs. Without it the build dies immediately on
`! Undefined control sequence. \setcode`.

An editor is optional; VS Code + the **LaTeX Workshop** extension works well and
its default recipe (latexmk) is already the right one.

## 2. Build

```bash
latexmk -pdf main.tex
```

That is the whole build. latexmk runs pdflatex and bibtex as many times as
needed, including the **second** bibtex pass for the Netography bibliography
(`bibtex N`), which is easy to miss by hand.

To clean up: `latexmk -C`

**Use pdflatex.** Do not switch the engine to xelatex or lualatex — the preamble
is an `inputenc` + `arabtex` setup, which is a pdflatex arrangement.

If you build by hand instead of with latexmk, the sequence is:

```bash
pdflatex main    # 1st pass
bibtex main      # main bibliography
bibtex N         # Netography (web sources) -- do not skip
pdflatex main
pdflatex main
```

## 3. Layout

```
report/
├── main.tex          <- preamble + document skeleton; BUILD THIS
├── references.bib    <- main bibliography
├── urls.bib          <- web sources (Netography)
├── README.md
├── images/
└── chapters/         <- every other .tex lives here
    ├── pg-EPT.tex          cover page
    ├── cover-arabic.tex    Arabic blocks for the cover (see trap 1)
    ├── 0-i-signature.tex … 0-v-abbreviations.tex   front matter
    ├── 0-introduction.tex
    ├── 1-first-chapter.tex … 5-fifth-chapter.tex
    ├── conclusion.tex
    ├── annexes.tex         not included yet; see "Appendices" in main.tex
    └── pg-ENSI_ang.tex     unused alternative cover (see section 5)
```

### Which file to edit

| What you want to change | File |
|---|---|
| Cover page: title, names, supervisors, dates, spacing | `chapters/pg-EPT.tex` |
| Preamble: packages, margins, headers, numbering | `main.tex` |
| Abstract / dedication / acknowledgements / abbreviations | `chapters/0-*.tex` |
| Chapters | `chapters/1-first-chapter.tex` … `chapters/5-fifth-chapter.tex` |
| Introduction / conclusion | `chapters/0-introduction.tex`, `chapters/conclusion.tex` |
| Bibliography entries | `references.bib` |
| Web sources (Netography, cited with `\citeN{...}`) | `urls.bib` |
| Figures | `images/` |

Files in `chapters/` are pulled in by `\subfile{chapters/...}` from `main.tex`,
so each starts with `% !TEX root = ../main.tex`. Build `main.tex` at the root,
never a file in `chapters/` (see trap 3). Figures are referenced by bare
filename — `\includegraphics{ev-building.jpg}` — because `\graphicspath` in
the preamble already points at `images/`.

## 4. Three traps, please read

**Never put a `%` comment inside `\begin{arabtext} ... \end{arabtext}`.**
arabtex re-parses that environment's body itself and does not treat `%` as a
comment there. A comment swallows the closing brace, and the build fails with a
confusing error pointing at a completely different line — typically:

```
! LaTeX Error: \begin{center} on input line 28 ended by \end{titlepage}.
```

To keep this out of the way, all the Arabic lives in **`chapters/cover-arabic.tex`** as
two macros, `\EPTArabicHeader` and `\EPTArabicFooter`. `chapters/pg-EPT.tex` just
calls them. So: edit `chapters/pg-EPT.tex` freely; only open it if the Arabic
text itself has to change, and read the notes at the top of it first.

**The cover must stay on one page.** It currently fits with roughly 1.5 cm to
spare. If you add lines to it and the EPT address footer jumps to page 2, take
the space back from the `\vspace{...}` values in `chapters/pg-EPT.tex` rather than
touching the footer.

**Never give a chapter file a `subfiles` preamble.** The chapter files are
plain fragments: no `\documentclass[../main.tex]{subfiles}`, no
`\begin{document}`. That is deliberate. `arabtex` replaces LaTeX's `\end`
(`alatex.sty`), so `subfiles` never gets to neutralise the `\end{document}` of
a subfile. Add the usual subfiles wrapper to a chapter and the **first**
`\end{document}` reached ends the whole document: `main.pdf` silently becomes a
1-page cover, with **no error message**. Reproduced with subfiles v2.2 in both
default and `[v1]` modes.

The cost is that a chapter cannot be typeset on its own (`pdflatex
chapters/1-first-chapter` fails with `Missing \begin{document}`); always build
`main.tex`. If you really need a chapter-only PDF, build the whole document and
extract the pages, or comment out the other `\subfile` lines in `main.tex`.

## 5. Known, harmless

* `Package auxhook Warning: Cannot patch \document` — arabtex redefines
  `\document` before hyperref loads; auxhook falls back correctly. Ignore it.
* `LaTeX Warning: Empty 'thebibliography' environment` — appears only while
  there are no `\cite` commands in the text. It clears itself once you cite
  something.
* `chapters/pg-ENSI_ang.tex` is an unused alternative cover and references
  `logo_entreprise.jpg`, which is **not** in `images/`. Leave its `\subfile`
  line in `main.tex` commented out, or the build will fail on the missing file.
