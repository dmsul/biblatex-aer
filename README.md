# BibLaTeX-AER

This is a bit of LaTeX code that formats the bibliography and citations
  following the `aer.bst` file used by *The American Economic Review* (see
  [here][aer]) but uses the more recent BibLaTeX and Biber packages which do
  not use the old BibTex `bst` files.
See [here][1] for reasons why you might want to use BibLaTeX/Biber over BibTex
  and [here][2] for how to transition away from BibTex.

This file is not a standalone Latex package, but rather some boilerplate
  preamble code that builds on `biblatex-chicago`.
It builds on the stock `biblatex-chicago` package in three ways:

1. Sets `biblatex-chicago` options to match `aer.bst`.
2. Bolds author names in the bibliography.
3. Extends hyperlinks in in-text citations to the entire citation, name and
   year, not just the year.

## Installation

The file `biblatex-aer.tex` must be in a folder where the LaTeX compiler can
  find it, e.g., in the same directory as your main document.
If you're using TexLive, you can put it in
  `~/texmf/tex/latex/local/biblatex-aer` and it will be available for use in
  any document (see [here][texmf]).


## Usage

Use `biblatex-aer` by adding the following to the preamble of your document:
```Latex
\input{biblatex-aer}
```
***Do not*** use `usepackage` instead of `input`, because `biblatex-aer` isn't
  a package.
It uses `\usepackage{biblatex-chicago}` and then makes various changes from
  there.

If you want to pass additional options to `biblatex-chicago`, like `natbib`,
  you can use
```Latex
\PassOptionsToPackage{natbib}{biblatex-chicago}  % Or other options
\input{biblatex-aer}
```
  instead.

For everything else (adding `bib` files, citations, etc.), you just follow
  standard BibLaTeX or `biblatex-chicago` conventions.


## Requirements
1. `biblatex-chicago` >= 0.9.9h (based on `biblatex` >= 3.3)
2. `biber` >= 2.4

The formatting syntax for `biblatex` changed with version 3.3.
If you really need to use an earlier version of `biblatex`, you can try
  `biblatex-aer` version 0.0.1, which uses the old syntax.

[1]: http://tex.stackexchange.com/questions/25701/bibtex-vs-biber-and-biblatex-vs-natbib
[2]: http://tex.stackexchange.com/questions/5091/what-to-do-to-switch-to-biblatex
[texmf]: http://tex.stackexchange.com/questions/1137/where-do-i-place-my-own-sty-or-cls-files-to-make-them-available-to-all-my-te
[aer]: https://www.aeaweb.org/journals/policies/templates
