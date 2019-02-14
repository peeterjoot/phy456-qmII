THISDIR := phy456-qmII
THISBOOK := phy456

export BOOKSUBVER := 1
export BOOKMAJVER := 0
export REVISIONNUMBER := 8

#.revinfo/gitCommitDateAsMyTime.tex:\newcommand{\myTime}{April 2018}\newcommand{\myVersion}{version V0.117\xspace}
VER := $(shell grep Version .revinfo/gitCommitDateAsMyTime.tex | sed 's/.*{//;s/.xspace.*//;')

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
#GENERATED_SOURCES += backmatter.tex

include ../latex/make.rules

dist:
	cp $(THISBOOK).pdf $(THISBOOK).$(VER).pdf

# a for annotate (releases).
tag:
	git tag -a $(THISBOOK).$(VER).pdf

#backmatter.tex : ../classicthesis_mine/backmatter.tex
#	cp $< $@
