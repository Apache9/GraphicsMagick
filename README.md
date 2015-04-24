GraphicsMagick
==============

Build z
-------

1. CFLAGS="-g -O3 -fPIC" ./configure --prefix=${INSTALL_DIR}
1. make
1. make install

Build bz2
---------

1. make -f Makefile-libbz2_so
1. make install PREFIX=${INSTALL_DIR}
1. cp libbz2.so.1.0.6 ${INSTALL_DIR}/lib
1. cd ${INSTALL_DIR}/lib && ln -s libbz2.so.1.0.6 libbz2.so.1.0 && ln -s libbz2.so.1.0.6 libbz2.so

Build webp
----------

1. CFLAGS="-g -O3 -fPIC" ./configure --prefix=${INSTALL_DIR}
1. make
1. make install

Build mozjpeg
-------------

1. CFLAGS="-g -O3 -fPIC" CPPFLAGS="-I${INSTALL_DIR}/include" LDFLAGS="-L${INSTALL_DIR}/lib" ./configure --prefix=${INSTALL_DIR} --with-jpeg8
1. make
1. make install

Build png16
-----------

1. CFLAGS="-g -O3 -fPIC" CPPFLAGS="-I${INSTALL_DIR}/include" LDFLAGS="-L${INSTALL_DIR}/lib" ./configure --prefix=${INSTALL_DIR}
1. make
1. make install

Build GraphicsMagick
--------------------

1. CFLAGS="-g -O3 -fPIC" CPPFLAGS="-I${INSTALL_DIR}/include" LDFLAGS="-L${INSTALL_DIR}/lib" ./configure --prefix=${INSTALL_DIR} --enable-shared --without-x --without-jbig --without-jp2 --without-tiff -without-ttf --without-lcms --without-wmf --without-magick-plus-plus --disable-openmp
1. make
1. make install

Build imagequant
----------------
1. cd lib
1. ./configure --extra-cflags=-g --extra-ldflags=-Wl,-soname,libimagequant.so.0
1. make
1. cp libimagequant.so.0 ${INSTALL_DIR}/lib
1. cp *.h ${INSTALL_DIR}/include