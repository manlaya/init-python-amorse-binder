# LaTeX generic makefile

TEXFILE = main
DST = initiation-python-amorse

LATEX = pdflatex -synctex=1
#BIBTEX = bibtex
BIBTEX = biber

MYFILES = *.pdf *.tex *.bib Makefile fig/ beamertheme-brgm/

.PHONY: all clean bibtex rename distrib
all:  makepdf

# makepdf: typeset1 bibtex rename distrib
makepdf: mkpdf1 bibtex mkpdf2

mkpdf1: $(TEXFILE).tex
	$(LATEX) $<; $(LATEX) $<

bibtex:
	# $(BIBTEX) $<
	$(BIBTEX) $(TEXFILE)


mkpdf2: $(TEXFILE).tex
	$(LATEX) $<; $(LATEX) $<

rename:
	mv $(TEXFILE).pdf $(DST).pdf

distrib:
	rm -f $(DST).tar.gz
	tar -zcvf $(DST).tar.gz $(MYFILES)

clean:
	rm -f **/*~ **/*.aux *.aux *.log *.dvi *.idx *.ilg *.ind *.toc textput.log *.out \
	*.blg *.nav *.bbl *.snm *.lof *.lot *.bcf *.run.xml \
	*.acn *.acr *.alg *.glg *.glo *.gls *.ist \
	*.synctex.gz *.fdb_latexmk *.fls

