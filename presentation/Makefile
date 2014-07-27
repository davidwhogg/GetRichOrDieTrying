LATEX       = pdflatex
BASH        = bash -c
ECHO        = echo
RM          = rm -rf
TMP_SUFFS   = pdf aux bbl blg log dvi ps eps out
SUFF        = pdf

NAME        = sk

all: hogg_ddd_palo_alto.pdf

%.pdf: %.tex
	${LATEX} $<
