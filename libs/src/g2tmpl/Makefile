SHELL  = /bin/sh
LIB    = ../../libg2tmpl.a
INCMOD = ../../mods/g2tmpl

#
# configuration file contains architecture and compile information
include ../../../configure.trk

#  If you want to enable support for PNG or JPEG2000 encoding/decoding,
#  you must specify -DUSE_PNG and/or -DUSE_JPEG2000 in the FDEFS variable
#  for the Fortran pre-processor
#  -DUSE_PNG requires libpng.a and libz.a
#                     ( and png.h pngconf.h zconf.h zlib.h include files).
#  -DUSE_JPEG2000 requires libjasper.a
#                     ( and all the jasper/*.h include files).
#
#  In addition, INCDIR must include all directories where the above
#  mentioned include files can be found.
FDEFS=-DUSE_JPEG2000

#
# extra flags
CPPFLAGS = $(FDEFS)
FFLAGS   = $(FFLAGS_G2) -c $(PROMOTION) -I. -DLINUX
CFLAGS   = $(CFLAGS_G2) -c $(GRIB2SUPT_INC) -DLINUX

#--------------------------------------
# TARGETs

all: $(LIB)
	$(MKDIR) $(INCMOD)
	$(CP) *.mod $(INCMOD)

g2sec4_temp11.o: grib2_all_tables_module.o
g2sec4_temp12.o: grib2_all_tables_module.o
g2sec4_temp1.o: grib2_all_tables_module.o

$(LIB):	$(LIB)(g2sec4_temp11.o) \
	$(LIB)(g2sec4_temp12.o) \
	$(LIB)(g2sec4_temp1.o) \
	$(LIB)(gdtsec3.o) \
	$(LIB)(grib2_all_tables_module.o) \
	$(LIB)(process_4dot2.o)

clean :
	@for f in `ls *.mod` ; do \
		$(RM) $$f ; $(RM) $(INCMOD)/$$f ; \
	done
	@for f in `ls -1 *.F|sed "s/.F$$/.f/"` ; do \
		$(RM) $$f   ; \
	done
	$(RM) $(LIBDIR)/$(LIB)
	$(RM) $(LIB)
	$(RM) $*.o

.F.a:
	$(CPP) $(CPP_FLAGS) $(CPPFLAGS) $*.F $*.f
	$(FC) -c $(FFLAGS) $(FFLAGS) $*.f
	$(AR) $(ARFLAGS) $@ $*.o

.f.a:
	$(FC) -c $(FFLAGS) $(FFLAGS) $<
	$(AR) $(ARFLAGS) $@ $*.o

.c.a:
	$(CC) -c $(CFLAGS) $(CFLAGS) $<
	$(AR) $(ARFLAGS) $@ $*.o
