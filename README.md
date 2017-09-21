# f90-nc-ci-test
Test travis build of Fortran program linked to NetCDF library

## Example

```bash session
[f90-nc-ci-test]$ cd src
[src]$ make
gfortran  -I/usr/lib64/gfortran/modules  -c nchello.f90 -o nchello.o
gfortran  -lnetcdff   nchello.o -o nchello
rm nchello.o
[src]$ make test
./nchello
 4.3.3.1 of Dec 10 2015 16:44:18 $
```
