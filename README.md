GraphicsMagick
==============

Build jemalloc
--------------

1. CFLAGS="-g -O3 -fPIC" ./configure --prefix=/home/work/image-lib-install --with-jemalloc-prefix=je_
1. make
1. make install

Build z
-------

1. CFLAGS="-g -O3 -fPIC" ./configure --prefix=${INSTALL_DIR}
1. make
1. make install

Build bz2
---------

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

1. patch memory.c.h to magick/memory.c
1. CFLAGS="-g -O3 -fPIC" CPPFLAGS="-I${INSTALL_DIR}/include" LDFLAGS="-L${INSTALL_DIR}/lib" ./configure --prefix=${INSTALL_DIR} --enable-shared --without-x --without-webp --without-jbig --without-jp2 --without-tiff -without-ttf --without-lcms --without-wmf --without-magick-plus-plus --disable-openmp
1. append -ljemalloc to MAGICK_DEP_LIBS in Makefile
1. make
1. make install
