include ../../configure.trk

LIBS = -L../../libs -lw3emc_i4r8 -lw3nco_i4r8 -lbacio -lg2
EXEC = ../../trk_exec/tave.exe

FFLAGS += $(GRIB2_FFLAGS)
LIBS += $(GRIB2_LIBS)

all: $(EXEC)

$(EXEC):      tave.f 
	$(SFC) $(FFLAGS) $(LDFLAGS) tave.f $(LIBS) -o $(EXEC)

.PHONY: clean

clean:
	$(RM) *.o  *.mod
