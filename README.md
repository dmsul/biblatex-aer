# BibLaTeX-AER

This is a short Latex snippet that creates a bibliography and citations in a
  format similar to `aer.bst`, the BibTex format file used by
  the *American Economic Review* (see [here][aer]), using 
  BibLaTeX and Biber instead of BibTex.
This `bst` file cannot be used with BibLaTeX and Biber which offer more features
  than BibTex.
See [this][1] post about why you might want to use BibLaTeX/Biber over BibTex
  and [this][2] post about how to transition away from BibTex.

When `hyperref` is used, it also extends hyperlink to the entire citation, not
  just the year.

This file currently is not a standalone Latex package.
It is just some boilerplate preamble code used with the `biblatex-chicago`
  package.

## Usage
Use `biblatex-aer` by adding the following to the preamble of your document:
```Latex
\input{biblatex-aer}
```
The file `biblatex-aer.tex` must be in folder where Latex can find it, e.g., in
  the same directory as your main document file or a user-specific folder like
  `~/texmf/tex/latex/local`.

***Do not*** use `usepackage` instead of `input`, becauase `biblatex-aer` isn't
  a package. It just imports the `biblatex-chicago` package
```Latex
\usepackage[authordate, backend=biber, uniquename=false, noibid]{biblatex-chicago}
```
  and then tweaks some of the formatting.

If you want to pass additional options to `biblatex-chicago`, like `natbib`,
  you can use
```Latex
\PassOptionsToPackage{natbib}{biblatex-chicago}
```
  somewhere before the `input` statement.

For adding `bib` files, citations, and literally everything else, you just
  follow standard BibLaTeX (or `biblatex-chicago`) conventions.


## Requirements
1. `biblatex-chicago` >= 0.9.9h (based on `biblatex` >= 3.3)
2. `biber` >= 2.4

The formatting syntax for `biblatex` change with version 3.3.
If you really need to use earlier versions, you can try `biblatex-aer` version
  0.0.1, which uses the old syntax.

[1]: http://tex.stackexchange.com/questions/25701/bibtex-vs-biber-and-biblatex-vs-natbib
[2]: http://tex.stackexchange.com/questions/5091/what-to-do-to-switch-to-biblatex
[aer]: https://www.aeaweb.org/journals/policies/templates
