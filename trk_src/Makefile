SHELL=/bin/sh
# Vortex Tracker makefile
#------------
# Include machine dependent compile & load options
#------------

SUBDIRS = gettrk vint tave

all: $(SUBDIRS)

$(SUBDIRS)::
	cd $@ ; make

clean::
	@for dir in $(SUBDIRS); do                                       \
           ( cd $$dir; echo "Making $@ in `pwd`" ;                       \
             $(MAKE) $@ );                                               \
        done

