SHELL=/bin/sh
include ../../../configure.trk
LIB = ../../libbacio.a
INCMOD  = ../../mods/bacio

INC=clib.h

$(LIB):	$(LIB)(bacio.o baciof.o bafrio.o byteswap.o chk_endianc.o)

$(LIB)(bacio.o):       bacio.c $(INC)
	$(SCC) -c $(CFLAGS_BACIO) bacio.c
	$(AR) $(ARFLAGS) $(LIB) bacio.o

$(LIB)(byteswap.o):     byteswap.c $(INC)
	$(SCC) -c $(CFLAGS_BACIO) byteswap.c
	$(AR) $(ARFLAGS) $(LIB) byteswap.o

$(LIB)(baciof.o):   baciof.f
	$(SFC) -c $(FFLAGS_BACIO) baciof.f
	$(AR) $(ARFLAGS) $(LIB) baciof.o 
	$(CP) *.mod $(INCMOD)

$(LIB)(bafrio.o):   bafrio.f
	$(SFC) -c $(FFLAGS_BACIO) bafrio.f
	$(AR) $(ARFLAGS) $(LIB) bafrio.o 

$(LIB)(chk_endianc.o):   chk_endianc.f
	$(SFC) -c $(FFLAGS_BACIO) chk_endianc.f
	$(AR) $(ARFLAGS) $(LIB) chk_endianc.o

clean:
	$(RM) baciof.o bafrio.o $(LIB) bacio.o byteswap.o chk_endianc.o *.mod $(INCMOD)/bacio_module.mod

