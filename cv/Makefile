PDFLATEX=pdflatex
FILE=cv
DIRS=fr en template

all: fr en template

fr:
	cd fr && make all && cp cv.pdf ../cv_fr.pdf

en:
	cd en && make all && cp cv.pdf ../cv_en.pdf

template:
	cd template && make all && cp cv.pdf ../cv_template.pdf

clean:
	cd fr && make clean
	cd en && make clean
	cd template && make clean

distclean:
	cd fr && make distclean
	cd en && make distclean
	cd template && make distclean
	rm *.pdf

# Export PDFVIEWER to the program you want to read PDF with
view:
	if [ -z "$(PDFVIEWER)" ]; then		\
		xpdf $(FILE).pdf;		\
	else					\
		$(PDFVIEWER) $(FILE).pdf;	\
	fi;

.PHONY: $(DIRS)
