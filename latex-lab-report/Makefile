SRC_DIR=src
SECTION_DIR=$(SRC_DIR)/sections
OUTDIR=build
TEXFILE=$(SRC_DIR)/rapport.tex
SECTFILES=$(wildcard $(SECTION_DIR)/*.tex)
PDFFILE=$(basename $(notdir $(TEXFILE))).pdf
REMISEFILE=nom-matricule.pdf

TEXFILES=$(TEXFILE) $(SECTFILES)

all: $(OUTDIR)/$(PDFFILE)

$(OUTDIR)/$(PDFFILE): $(TEXFILES)
	mkdir -p $(OUTDIR)
	latexmk -pdf -bibtex -outdir=$(OUTDIR) $(TEXFILE)

clean:
	rm -rf $(OUTDIR)

run: all
	xdg-open $(OUTDIR)/$(PDFFILE)

remise: all
	mv $(OUTDIR)/$(PDFFILE) $(REMISEFILE)
	rm -rf $(OUTDIR)
	xdg-open $(REMISEFILE)

