LATEX       = pdflatex
BASH        = bash -c
ECHO        = echo
RM          = rm -rf
TMP_SUFFS   = aux bbl blg log dvi eps out
CHECK_RERUN = grep Rerun $*.log

all: facilities.pdf description.pdf biosketch_hogg.pdf

%.pdf: %.tex hogg_nasa.tex
	${LATEX} $<
	bibtex $*
	${LATEX} $<
	( ${CHECK_RERUN} && ${LATEX} $< ) || echo "Done."
	( ${CHECK_RERUN} && ${LATEX} $< ) || echo "Done."

clean:
	${RM} $(foreach suff, ${TMP_SUFFS}, *.${suff})
