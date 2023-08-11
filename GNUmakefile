THISDIR := phy456-qmII
THISBOOK := phy456

BIBLIOGRAPHY_PATH := classicthesis_mine
HAVE_OWN_CONTENTS := 1
HAVE_OWN_TITLEPAGE := 1
MY_CLASSICTHESIS_FRONTBACK_FILES += ../latex/classicthesis_mine/FrontBackmatter/Index.tex
MY_CLASSICTHESIS_FRONTBACK_FILES += ../latex/classicthesis_mine/FrontBackmatter/ContentsAndFigures.tex
BOOKTEMPLATE := ../latex/classicthesis_mine/ClassicThesis2.tex

# comment this out for online pdf version (uncomment for KDP)
#PRINT_VERSION := 1

ifndef PRINT_VERSION
PARAMS += --no-print
endif
ifdef PRINT_VERSION
DISTEXTRA := kdp
endif

include make.revision
include ../latex/make.bookvars

FIGURES := ../figures/phy456-qmII

#ONCEFLAGS := -justonce

SOURCE_DIRS += approx
SOURCE_DIRS += handouts
SOURCE_DIRS += mathematica
SOURCE_DIRS += problems
SOURCE_DIRS += scattering
SOURCE_DIRS += spin
SOURCE_DIRS += $(FIGURES)

PRIMARY_SOURCES := $(shell grep input chapters.tex | sed 's/%.*//;s/.*{//;s/}.*//;')
PRIMARY_SOURCES += FrontBackmatter/preface.tex

GENERATED_SOURCES += mathematica.tex 
GENERATED_SOURCES += backmatter.tex

DO_SPELL_CHECK := $(shell cat spellcheckem.txt)

include ../latex/make.rules

$(THISBOOK).pdf :: $(EXTERNAL_DEPENDENCIES)

.PHONY: spellcheck
spellcheck: $(patsubst %.tex,%.sp,$(filter-out $(DONT_SPELL_CHECK),$(DO_SPELL_CHECK)))

%.sp : %.tex
	spellcheck $^
	touch $@

scrpage2.sty : ../latex/scrpage2.sty
	cp $^ $@

backmatter.tex: ../latex/classicthesis_mine/backmatter_with_parts.tex
	rm -f $@
	ln -s ../latex/classicthesis_mine/backmatter2.tex backmatter.tex
	#ln -s ../latex/classicthesis_mine/backmatter_with_parts.tex backmatter.tex
