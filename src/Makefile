%.o : %.f90
	$(FC) $(FFLAGS) -c $< -o $@

% : %.o
	$(FC) $< $(LDFLAGS) $(LDLIBS) -o $@

ifndef TRAVIS
    EXTRAINCLUDE=-I/usr/lib64/gfortran/modules
    NCFLAGS=$(shell nf-config --fflags)
    NCLIBS=$(shell nf-config --flibs)
else
    EXTRAINCLUDE=-I/usr/include 
    NCFLAGS=-I/usr/include
    NCLIBS=-lnetcdff 
endif

FFLAGS=$(NCFLAGS) $(EXTRAINCLUDE)
LDLIBS=$(NCLIBS)

FC=gfortran

all: nchello

test: nchello
	./nchello

clean:
	\rm -f *.o nchello
