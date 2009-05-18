DIRS=fr en template

all: $(DIRS)

fr:
	cd fr && make all && mv cv.pdf ../cv_fr.pdf

en:
	cd en && make all && mv cv.pdf ../cv_en.pdf

template:
	cd template && make all && mv cv.pdf ../cv_template.pdf

clean:
	cd fr && make clean
	cd en && make clean
	cd template && make clean

distclean:
	cd fr && make distclean
	cd en && make distclean
	cd template && make distclean
	rm *.pdf

.PHONY: $(DIRS)
