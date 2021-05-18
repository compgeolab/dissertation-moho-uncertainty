# Dissertation

Source files and figures for the dissertation. The PDF is built using
[LaTeX](https://en.wikipedia.org/wiki/LaTeX) from the `.tex` source files.
The main document is assembled in `dissertation.tex`, with individual chapters
in the separate `.tex` files. References are managed by BibTeX and should be
included in `references.bib`. To get BibTeX entries for papers based on their
[DOI](https://en.wikipedia.org/wiki/Digital_object_identifier), use the
[doi2bib.org](https://www.doi2bib.org/) website.

Learn more about LaTeX and how to use it to write documents from the [Overleaf
tutorial](https://www.overleaf.com/learn/latex/Main_Page).

## Installing LaTeX

### Windows

Download and install [MikTex](https://miktex.org/).

### Linux

Install the `texlive` package from your system's package manager.

## Building the PDF

To generate a PDF from the LaTeX source files, run the following in a terminal
(or Git Bash on Windows):

```bash
make
```

The `dissertation.pdf` file will be placed in the `output` folder. To remove it
and all junk files created by LaTeX, run:

```bash
make clean
```
