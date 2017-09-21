%.o : %.f90
	$(FC) $(FFLAGS) -c $< -o $@

% : %.o
	$(FC) $(LDFLAGS) $(LDLIBS) $< -o $@

NCLAGS=$(shell nf-config --fflags)
NCLIBS=$(shell nf-config --flibs)

FFLAGS=$(NCFLAGS) -I/usr/lib64/gfortran/modules 
LDLIBS=$(NCLIBS)

FC=gfortran

all: nchello

test: nchello
	./nchello

clean:
	\rm -f *.o nchello
