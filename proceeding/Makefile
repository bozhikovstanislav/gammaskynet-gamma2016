TARGET=gammaskynet-gamma2016
LATEX=pdflatex
BIBTEX=bibtex

all: $(TARGET).pdf

$(TARGET).pdf: *.tex figures/* text/* tables/* $(TARGET).bib

%.pdf: %.tex
	$(LATEX) $<
	$(BIBTEX) $*
	$(LATEX) $<
	$(LATEX) $<

make clean:
	- rm -f $(TARGET).pdf $(TARGET).aux $(TARGET).log $(TARGET).bbl $(TARGET).fff
	- rm -f *.aux */*.aux */*/*.aux



tarball:
	- tar -cvzf $(TARGET).tar.gz \
	gammaskynet-gamma2016.tex \
	gammaskynet-gamma2016.bib \
	gammaskynet-gamma2016.bbl \
	text/*.tex \
	figures/mapview_retake.PNG \
	figures/catview_retake.PNG \
	figures/four_images.png \
	figures/galactic_region_NEW.png \
	figures/cygnus_region.png \
	aip-cp.cls aipnum-cp.bst \
	Makefile
