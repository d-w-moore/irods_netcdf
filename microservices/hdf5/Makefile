SRCDIR=src

SRCS=$(SRCDIR)/msiH5Dataset_read.cpp \
		$(SRCDIR)/msiH5Dataset_read_attribute.cpp \
		$(SRCDIR)/msiH5Group_read_attribute.cpp \
		$(SRCDIR)/msiH5File_close.cpp \
		$(SRCDIR)/msiH5File_open.cpp

CFLAGS += -DRODS_SERVER

EXTRAINCS+= -I/usr/include/irods/netcdf/include -I../../api/include -I/usr/include/irods/hdf5/src

EXTRALIBS+= -L/usr/lib/irods/externals -Wl,-rpath -Wl,/usr/lib/irods/externals -lnetcdf

.PHONY: default clean

default: agnostic-base

clean: clean-base

include ../../Makefile.base
