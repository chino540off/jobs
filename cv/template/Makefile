##
## Makefile for Assistants-2009-subject in templates/subject
##
## Made by clement perrod
## Login   <perrod_c@epita.fr>
##
## Started on  Sat Jun 14 13:33:03 2008 clement perrod
## Last update Sat Jun 14 13:33:03 2008 clement perrod
##

FILE=cv
RM=rm
RMOPT=-rf

LOGIN=ACU-2009
PROJECT=project-subject

CP=cp
CPOPT=-rf

MKDIR=mkdir
PDFVIEWER=kpdf

PDFLATEX=pdflatex
FIND=find
DISTDIR=$(LOGIN)-$(PROJECT)
DISTEXT=.tar.bz2
DISTBIN=tar
DISTOPT=--exclude .svn --exclude CVS --exclude .hg  -c -v -j -f
DISTFILES=	$(FILE).tex			\
		Makefile			\
		moderncvthemecasual.sty		\
		moderncvthemeempty.sty		\
		moderncvcompatibility.sty	\
		moderncvthemeclassic.sty	\
		moderncv.cls

# Use this target if you want to be sure that your PDF file is OK
all: $(FILE).tex
	$(PDFLATEX) $(FILE).tex
	$(PDFLATEX) $(FILE).tex
	$(PDFLATEX) $(FILE).tex

# Use this target if you don't want to compile three times !
light:
	$(PDFLATEX) $(FILE).tex

# Export PDFVIEWER to the program you want to read PDF with
view: all
	if [ -z "$(PDFVIEWER)" ]; then		\
		xpdf $(FILE).pdf;		\
	else					\
		$(PDFVIEWER) $(FILE).pdf;	\
	fi;

clean:
	$(FIND) \( -name '*.toc' -o -name '*.aux' -o -name '*.bat' \) -exec $(RM) $(RMOPT) {} \;
	$(FIND) \( -name '*.glo' -o -name '*.log' -o -name '*.out' \) -exec $(RM) $(RMOPT) {} \;
	$(FIND) \( -name '#*' -o -name '*.aux' -o -name '*~' \) -exec $(RM) $(RMOPT) {} \;

distclean: clean
	$(RM) $(RMOPT) $(FILE).pdf

dist: distclean
	if [ -d $(DISTDIR) ]; then				\
		$(RM) $(RMOPT) $(DISTDIR);			\
	fi
	$(MKDIR) $(DISTDIR);
	$(CP) $(CPOPT) $(DISTFILES) $(DISTDIR)
	$(DISTBIN) $(DISTOPT) $(DISTDIR)$(DISTEXT) $(DISTDIR)
	$(RM) $(RMOPT) $(DISTDIR)
