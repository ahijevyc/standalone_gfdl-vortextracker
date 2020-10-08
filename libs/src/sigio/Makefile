
LIB = ../../libsigio_i4r4.a
INCMOD = ../../mods/sigio

include ../../../configure.trk

.SUFFIXES: .o .f .F .c

$(LIB): $(LIB)(sigio_module.o) $(LIB)(sigio_r_module.o)
	$(MKDIR) $(INCMOD)
	$(CP) *.mod $(INCMOD)

.f.a:
	$(F90) -c $(FFLAGS_SIGIO) $<
	$(AR) $(ARFLAGS) $@ $*.o
	$(RM) $*.o

.c.a:
	$(CC) -c $(CFLAGS) $<
	$(AR) $(ARFLAGS)  $@ $*.o
	$(RM) $*.o

clean:
	$(RM) *.o *.mod

