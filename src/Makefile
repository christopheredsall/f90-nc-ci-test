%.o : %.f90
	$(FC) $(FFLAGS) -c $< -o $@

% : %.o
	$(FC) $(LDFLAGS) $(LDLIBS) $< -o $@

NCLAGS=$(shell nf-config --fflags)
NCLIBS=$(shell nf-config --flibs)

ifndef TRAVIS
    EXTRAINCLUDE=-I/usr/lib64/gfortran/modules
else
    EXTRAINCLUDE=-I/usr/include 
endif

FFLAGS=$(NCFLAGS) $(EXTRAINCLUDE)
LDLIBS=$(NCLIBS)

FC=gfortran

all: nchello

test: nchello
	./nchello

clean:
	\rm -f *.o nchello
