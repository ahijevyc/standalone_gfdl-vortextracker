SHELL=/bin/sh

include ../../../configure.trk

OBJS = \
args_mod.o gblevents.o getgbens.o isrchne.o iw3mat.o mersenne_twister.o  \
mova2i.o orders.o putgbens.o w3ai40.o w3ai41.o w3ctzdat.o  \
w3fa01.o w3fa03.o w3fa03v.o w3fa04.o w3fa06.o w3fa09.o w3fa11.o  \
w3fa12.o w3fa13.o w3fb00.o w3fb01.o w3fb02.o w3fb03.o w3fb04.o w3fb05.o  \
w3fb06.o w3fb07.o w3fb08.o w3fb09.o w3fb10.o w3fb11.o w3fb12.o w3fc02.o  \
w3fc05.o w3fc06.o w3fc07.o w3fc08.o w3fi02.o w3fi03.o w3fi18.o w3fi19.o  \
w3fi20.o w3fi32.o w3fi47.o w3fi48.o w3fi52.o w3fi61.o w3fi65.o w3fi66.o  \
w3fi67.o w3fi70.o w3fi78.o w3fi85.o w3fm07.o w3fm08.o w3fp04.o w3fp05.o  \
w3fp06.o w3fp10.o w3fq07.o w3ft00.o w3ft01.o w3ft02.o w3ft03.o w3ft05.o  \
w3ft05v.o w3ft06.o w3ft06v.o w3ft07.o w3ft08.o w3ft09.o w3ft10.o  \
w3ft11.o w3ft12.o w3ft16.o w3ft17.o w3ft201.o w3ft202.o w3ft203.o  \
w3ft204.o w3ft205.o w3ft206.o w3ft207.o w3ft208.o w3ft209.o w3ft210.o  \
w3ft211.o w3ft212.o w3ft213.o w3ft214.o w3ft21.o w3ft26.o w3ft33.o  \
w3ft38.o w3ft39.o w3ft40.o w3ft41.o w3ft43v.o w3log.o w3miscan.o \
xdopen.o

FC=$(SFC)
CC=$(SCC)
FFLAGS=$(FFLAGS_W3)  -I../../mods/sigio -DLINUX
CFLAGS=$(CFLAGS_W3)  -DLINUX

all:
	OUTPUT_LIB=../../libw3emc_i4r8.a \
	make -f Makefile clean lib

lib:	$(OUTPUT_LIB)

# Override the .F to be fixed-form pre-processed
.F.o:
	$(RM) $*.mod $*.o
	$(FC) $(FPPFLAGS) $(FFLAGS) -c $*.F

.f.o:
	$(RM) $*.mod $*.o
	$(FC) $(FFLAGS) -c $*.f 

$(OUTPUT_LIB):	$(OBJS)
	$(AR) $(ARFLAGS) $(OUTPUT_LIB) $(OBJS)

clean:
	rm -f *.o *.mod 

