#SHELL=/bin/sh
#  

include ../configure.trk


SUBDIRS = src

all: $(SUBDIRS)
	@for dir in $(SUBDIRS); do \
           ( cd $$dir; echo "Making $@ in `pwd`" ; make -f Makefile ); \
        done

clean: $(SUBDIRS)
	$(RM) mods/bacio/* mods/g2/*  mods/g2tmpl/*  mods/sigio/*  mods/w3emc/*  mods/w3nco/* *.a
	@for dir in $(SUBDIRS); do \
           ( cd $$dir; echo "Cleaning $@ in `pwd`" ; \
                make -f Makefile clean $@) ; \
        done
