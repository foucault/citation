citation
========

About
-----
**citation** is a dead simple Python script used to download readily formatted
citations for use in bibtex just by providing its Document Object Identifier
(DOI). Cut and paste the output into your `.bib` file and you are ready to go!

    $ citation 10.1007/bf00883088
    @article{Foti_1977,
     author = {Foti, G. and Rimini, E. and Vitali, G. and Bertolotti, M.},
     doi = {10.1007/bf00883088},
     issn = {1432-0630},
     journal = {Applied Physics},
     month = oct,
     number = {2},
     pages = {189–191},
     publisher = {Springer Nature},
     shortjournal = {Appl. Phys.},
     title = {Amorphous-polycrystal transition induced by laser pulse in self-ion implanted silicon},
     url = {http://dx.doi.org/10.1007/bf00883088},
     volume = {14},
     year = {1977}
    }


If you are using vim you can do that directly from your editor by using the
following command

    :r !citation 10.1007/bf00883088

and the bibtex entry will be appended into your current buffer.

Features
--------
* Download bibtex entries with just the DOI of the article.
* Automatically generate the abbreviated journal name into the `shortjournal`
  bibtex field. If you use `biblatex` you can use this field instead of the
  `journal` to create a more compact bibliography.
* Automatically strip curly braces from month specifications (`{jan}` → `jan`).
  Enclosing month abbreviations in curly braces is a LaTeX literal and should
  be avoided if you want your citations to be sorted correctly in a
  chronological order.

Caveats
-------
**citation** should work fairly well at least for most western languages. It is
completely untested with anything else than latin and greek alphabet, so
expect things to break. Although **citation** will probably get your citations
correct the first time there is always the chance of typos or invalid
characters. These errors are propagated from CrossRef and are very hard to
catch. However this should not happen very often. In my PhD I only had to edit
3 or 4 citations out of a 400+ references.

Dependencies
------------

 * Python ≥ 3.2
 * [Requests](https://github.com/requests/requests)
 * [BibtexParser](https://github.com/sciunto-org/python-bibtexparser)

