SHELL=/bin/sh

SUBDIRS = bacio sigio w3emc w3nco g2tmpl g2 w3emc_i4r4 w3nco_i4r4

all: $(SUBDIRS)
	@for dir in $(SUBDIRS); do \
           ( cd $$dir; echo "Making $@ in `pwd`" ; make -f Makefile ) ; \
        done

clean: $(SUBDIRS)
	@for dir in $(SUBDIRS); do \
           ( cd $$dir; echo "Cleaning $@ in `pwd`" ; make -f Makefile $@ ) ; \
        done
