SHELL=/bin/sh

include ../../../configure.trk
# include ../../../pure-openmp.inc

OBJS = \
mova2i.o summary.o aea.o errexit.o errmsg.o fparsei.o fparser.o  \
gbytec.o gbyte.o gbytesc.o gbytes.o getbit.o getgb1.o getgb1re.o  \
getgb1r.o getgb1s.o getgbe.o getgbeh.o getgbem.o getgbemh.o getgbemn.o  \
getgbemp.o getgbep.o getgbex.o getgbexm.o getgb.o getgbh.o getgbm.o  \
getgbmh.o getgbmp.o getgbp.o getgi.o getgir.o gtbits.o idsdef.o  \
instrument.o iw3jdn.o iw3pds.o iw3unp29.o ixgb.o lengds.o makwmo.o  \
mkfldsep.o pdsens.o pdseup.o putgbe.o putgben.o putgbex.o putgb.o  \
putgbn.o q9ie32.o r63w72.o sbytec.o sbyte.o sbytesc.o sbytes.o skgb.o  \
w3ai00.o w3ai01.o w3ai08.o w3ai15.o w3ai18.o w3ai19.o w3ai24.o w3ai38.o  \
w3ai39.o w3aq15.o w3as00.o w3difdat.o w3doxdat.o w3fi01.o w3fi04.o  \
w3fi58.o w3fi59.o w3fi62.o w3fi63.o w3fi64.o w3fi68.o w3fi69.o w3fi71.o  \
w3fi72.o w3fi73.o w3fi74.o w3fi75.o w3fi76.o w3fi82.o w3fi83.o w3fi88.o  \
w3fi92.o w3fp11.o w3fp12.o w3fp13.o w3fs13.o w3fs15.o w3fs21.o w3fs26.o  \
w3ft32.o w3kind.o w3locdat.o w3movdat.o w3nogds.o w3pradat.o w3reddat.o  \
w3tagb.o w3trnarg.o w3unpk77.o w3utcdat.o w3valdat.o w3ymdh4.o xmovex.o  \
xstore.o 

#FFLAGS+=-O0 -check all -debug all -traceback

FC=$(SFC)
CC=$(SCC)

all:
	OUTPUT_LIB=../../libw3nco_i4r8.a \
	make -f Makefile clean lib

lib:	$(OUTPUT_LIB)

# Override the .F to be fixed-form pre-processed
.F.o:
	$(RM) $@ $*.mod
	$(CPP) $(FPPFLAGS) $(FDEFS)  $< > $*.f
	$(FC) $(FFLAGS_W3) -c $*.f 
	$(RM) $*.f

$(OUTPUT_LIB):	$(OBJS)
	$(AR) $(ARFLAGS) $(OUTPUT_LIB) $(OBJS)

clean:
	rm -f *.o *.mod 

