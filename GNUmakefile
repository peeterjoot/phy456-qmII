THISDIR := phy456-qmII
THISBOOK := phy456

export BOOKSUBVER := 1
export BOOKMAJVER := 0
# This isn't a good way to version.  It depends on the local git reflog history count.
export REVCOUNTSTART := 1

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

#backmatter.tex : ../classicthesis_mine/backmatter.tex
#	cp $< $@
