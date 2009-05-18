SOURCE		= cv.tex
TARGET		= $(SOURCE:.tex=.pdf)

LATEX   	?= texi2pdf
VIEWER		= xpdf

TODEL		= tags *~ .*.swp *.log *.aux *.dvi *.png

INCLUDE		= ../template
IMG		= ./data
BUILD_DIR	= ./tmp

all: latex

clean:
	rm -rf $(BUILD_DIR)

distclean: clean
	$(RM) $(RMFLAGS) $(TARGET)

latex: $(TARGET)

$(TARGET): $(SOURCE) $(SOURCES_DEPS)
	$(LATEX) $< -o $(TARGET) --build-dir=$(BUILD_DIR) -I "$(IMG)" -I "$(INCLUDE)"

view: $(TARGET)
	$(VIEWER) -z page $(TARGET)
