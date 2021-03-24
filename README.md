# irods_netcdf

API plugins, microservices, and commands for accessing NetCDF data/metadata contained in iRODS data objects.

Currently supported version(s) of iRODS:
   - 4.2.8

OS Distributions presently supported:
   - Centos 7
   - Ubuntu 16.04
   - Ubuntu 18.04

Automated building and packaging is available as before, but is now done through CMake.

## Building the Plugin for iRODS 4.2+

Make sure the development packages for OpenSSL, NetCDF, HDF5, and iRODS itself are installed on the build machine, as well
as these build externals:

   - `irods-externals-cmake3.11.4-0`
   - `irods-externals-clang6.0-0`
   - `irods-externals-boost1.67.0-0`

Clone this repository:
```sh
git clone -b {BRANCH|TAG|COMMIT} http:/github.com/irods/irods_netcdf
```
(Currently  `4.2.8.0` is the only plugin version available on iRODS 4.2+, and you must be running the 4.2.8 release of the server.)

3. Build:
```sh
mkdir build ; cd build
/opt/irods-externals/cmake3.11.4-0/bin/cmake ../irods_netcdf
make -j7
```
Then:
```
make
```

---

## Packages

Using the build command
```
make package
```
will produce the following package files (in .rpm or .deb format):
   1. irods-netcdf-server_modules
   2. irods-netcdf-client_modules
   3. irods-netcdf-icommands

Note:

Dependencies are set such that both the server_modules and icommands packages depend on client_modules.
The remaining prerequisites, ie. the openssl and netcdf libraries, can be installed via yum or apt-get via the
default repositories.
