# Letter Class Option `makelabels`

----------------------------------------------------------------------------

Copyright (c) Markus Kohm, 2009-2021  
Licence: LPPL 1.3c  
Release: 2021/08/14 v1.0

----------------------------------------------------------------------------

Requires: KOMA-Script

----------------------------------------------------------------------------

## Summary

The standard letter class `letter` has a label feature. You can activate it 
using `\makelabels`.  While in Germany window envelopes are common, printing
labels is not common and `scrltt2` never supported label printing.  At the
[German KOMA-Script book](https://komascript.de/komascriptbuch) I've shown
how you can print labels simply by printing a letter with special pseudo
value settings.  Doing so you can use several configuration features.  Using
`makelabels.lco` in opposite does only implement a `\makelabels` feature
similar to the standard letter classes.  Currently there are no
configuration features at `makelabel.lco`.  But you may use package
[`envlab`](https://www.ctan.org/pkg/envlab) from CTAN after loading
`mlabel.lco` to get various configuration features.

## Installation

It is recommended to use the package manager of your TeX distribution to
install `makelabels.lco`. But if this is not possible of if you are a
distribution you can either use `l3build` and [sources from the git
repository](https://github.com/komascript/makelabels) or a completely manual
installation using a basic source file distribution.

### Manual installation using `l3build` and the git sources

First of all copy or clone the sources of the current release or the developer
code from [github](https://github.com/komascript/makelabels) and use

    l3build unpack

to unpack the package. The unpacked files then can be found be in
`build/unpacked`. You can use

    l3build doc

to generate the manual and the example PDFs.

    l3build install

to install the package locally. But this will neither install the manual nor
nor the example files. Currently there are two example files, generated by
`l3build`:

 - `makelabels-example.tex` is the source of a very simple example using
   `scrletter` class and `makelabels.lco` only. The result can be found in
   `makelabels-example.pdf`
 - `makelabels-envlab-example.tex` is the source of an example that shows
   how to use package [`envlab`](https://www.ctan.org/pkg/envlab) in
   combination with `scrletter` class and `makelabels.lco` to have more
   versability.
   
### Manual installation using a basic source distribution

A basic source distribution consists of `makelabels.dtx` and `README.md`
only. There may be additional manual and demo files like `makelabels.pdf`,
`makelabels-example.pdf` or `makelabels-envlab-example.pdf`.

If you have got such a basic source distribution, i.e., from CTAN,
you first have to unpack the files using:

    tex makelabels.dtx

Don't use `latex`, `pdflatex`, `lualatex` or `xelatex` instead of `tex`!
The unpacking will produce `makelabels.lco`, `makelabels-example.tex` and
`makelabels-envlab-example.tex`.

If your source distribution does not contain the manual `makelabels.pdf` and
the example files `makelabals-example.pdf` and `makelabels-envlab-example.pdf`
you can generate these (after the unpacking previously explained) using:

	pdflatex makelabels-example.tex
	pdflatex makelabels-example.tex
	pdflatex makelabels-envlab-example.tex
	pdflatex makelabale-envlab-example.tex
	pdflatex makelabels.dtx
	mkindex makelabels
	pdflatex makelabels.dtx
	mkindex makelabels
	pdflatex makelabels.dtx

To install all the runtime files, make a folder `tex/latex/makelabels` in you
private or local TEXMF tree if this folder does not yet exists. Then copy
`makelabels.lco` to this folder.

To install the manual and the demo files, make a folder `doc/latex/makelabels`
in the same TEXMF tree you've uses for the installation of
`makelabels.lco`, if the folder does not yet exists. Then copy the demo files
`makelabels-example.tex`, `makelabels-envlab-example.tex`,
`makelabels-example.pdf`, `makelabels-envlab-example.pdf` and the manual
`makelabels.pdf` to this folder.

 MiKTeX users have to additionally update the *Filename Database*. See the
 manual of the *MiKTeX console* for more information. TeX Live user usually do
 not need to run `texhash`, because the private and the personal TEXMF tree is
 usually searched completely.

## Usage

Like all other LCO files you can load `makelabels.lco` using
`\LoadLetterOption{makelabels}`. For `scrlttr2` loading via optional
argument of `\documentclass` also works, but is not recommended any longer.

After loading the LCO file, you can add `\makelabels` into your document
preamble to active the automatic generation of labels at the end of the
document while reading the `*.aux`-file.

Note: In oposite to other LCO files you must not load `mkalelabels.lco`
after `\begin{document}`!

See the manual for more information.
