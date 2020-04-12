THISDIR := phy456-qmII
THISBOOK := phy456

BIBLIOGRAPHY_PATH := classicthesis_mine
#HAVE_OWN_CONTENTS := 1
#HAVE_OWN_TITLEPAGE := 1
MY_CLASSICTHESIS_FRONTBACK_FILES += ../latex/classicthesis_mine/FrontBackmatter/Index.tex
#MY_CLASSICTHESIS_FRONTBACK_FILES += ../latex/classicthesis_mine/FrontBackmatter/ContentsAndFigures.tex
BOOKTEMPLATE := ../latex/classicthesis_mine/ClassicThesis2.tex

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

GENERATED_SOURCES += mathematica.tex 
GENERATED_SOURCES += backmatter.tex

include ../latex/make.rules

backmatter.tex: ../latex/classicthesis_mine/backmatter_with_parts.tex
	rm -f $@
	ln -s ../latex/classicthesis_mine/backmatter_with_parts.tex backmatter.tex
