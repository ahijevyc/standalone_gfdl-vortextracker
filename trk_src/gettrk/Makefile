include ../../configure.trk

 LIBS = -L../../libs/ -lw3emc_i4r8 -lw3nco_i4r8 -lbacio -lg2 \
       -L${NETCDF}/lib -lnetcdff -lnetcdf -L${PNETCDF}/lib -lpnetcdf \
       -L${HDF5}/lib -lhdf5_hl -lhdf5 -lhdf5_fortran
 INCMOD   =  -I${NETCDF}/include -I${PNETCDF}/include -I${HDF5}/include
FFLAGS += $(GRIB2_FFLAGS)
LIBS += $(GRIB2_LIBS)

OBJS = gettrk_modules.o module_waitfor.o cwaitfor.o # all non-main objects
EXEC = ../../trk_exec/gettrk.exe

all: $(EXEC)

$(EXEC):      gettrk_main.f $(OBJS) 
	$(SFC) $(FFLAGS) ${INCMOD} $(LDFLAGS) $(OBJS) gettrk_main.f $(LIBS) -o $(EXEC)

.f.o:
	$(SFC) $(FFLAGS) ${INCMOD} -c $< 

.PHONY: clean

clean:
	$(RM) *.o  *.mod
