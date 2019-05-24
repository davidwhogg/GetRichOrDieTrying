LATEX       = pdflatex
BASH        = bash -c
ECHO        = echo
RM          = rm -rf
TMP_SUFFS   = aux blg log dvi eps out
CHECK_RERUN = grep Rerun $*.log

all: facilities.pdf description.pdf biosketch_hogg.pdf

description.bbl: description.bib description.tex
	${LATEX} description
	bibtex description

description.pdf: description.bbl

%.pdf: %.tex hogg_nasa.tex
	${LATEX} $<
	( ${CHECK_RERUN} && ${LATEX} $< ) || echo "Done."
	( ${CHECK_RERUN} && ${LATEX} $< ) || echo "Done."

clean:
	${RM} $(foreach suff, ${TMP_SUFFS}, *.${suff})
