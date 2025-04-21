PROJNAME=main
BUILDDIR=build

.PHONY: $(PROJNAME).pdf all clean

all: $(PROJNAME).pdf

$(PROJNAME).pdf: $(PROJNAME).tex
	latexmk -pdf -synctex=1 -verbose -interaction=nonstopmode -file-line-error -output-directory=$(BUILDDIR) $<

clean:
	latexmk -output-directory=$(BUILDDIR) -c && rm -rf build/*

manual:
	pdflatex -output-directory=$(BUILDDIR) $(PROJNAME).tex
	bibtex $(BUILDDIR)/$(PROJNAME)
	pdflatex -output-directory=$(BUILDDIR) $(PROJNAME).tex
pdflatex -output-directory=$(BUILDDIR) $(PROJNAME).tex
