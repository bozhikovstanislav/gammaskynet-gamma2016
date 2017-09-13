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
	- rm -f $(TARGET).pdf $(TARGET).aux $(TARGET).log $(TARGET).bbl $(TARGET).fff $(TARGET).tar.gz
	- rm -f *.aux */*.aux */*/*.aux

tarball:
	- tar -cvzf $(TARGET).tar.gz \
	$(TARGET).tex \
	$(TARGET).bib \
	$(TARGET).bbl \
	text/*.tex \
	tables/*.tex \
	figures/mapview_retake.PNG \
	figures/catview_retake.PNG \
	figures/four_images.png \
	figures/galactic_region_NEW.png \
	figures/cygnus_region.png \
	aip-cp.cls aipnum-cp.bst \
	Makefile
