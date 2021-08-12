# Letter Class Option `makelabels`

----------------------------------------------------------------------------

Copyright (c) Markus Kohm, 2009-2021  
Licence: LPPL 1.3c  
Release: 2021/08/11 v1.0

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

It is recommended to use the package installer of your TeX distribution to
install `makelabels.lco`. If it is not available or if you are a destributor
you can use

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

## Usage

Like all other LCO files you can load `makelabels.lco` using
`\LoadLetterOption{makelabels}`. For `scrlttr2` loading via optional
argument of `\documentclass` also works, but is not recommended any linger.

After loading the LCO file, you can add `\makelabels` into your document
preamble to active the automatic generation of labels at the end of the
document while reading the `*.aux`-file.

Note: In oposite to other LCO files you must not load `mkalelabels.lco`
after `\begin{document}`!

See the manual for more information.
