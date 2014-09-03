GraphicsMagick
==============

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

1. Change the last source line in coders/webp.c to `return (webp_status ? MagickPass : MagickFail);`. ref [here](http://ehc.ac/p/graphicsmagick/discussion/250738/thread/a957cdca/)
1. CFLAGS="-g -O3 -fPIC" CPPFLAGS="-I${INSTALL_DIR}/include" LDFLAGS="-L${INSTALL_DIR}/lib" ./configure --prefix=${INSTALL_DIR} --enable-shared --without-x --without-jbig --without-jp2 --without-tiff -without-ttf --without-lcms --without-wmf --without-magick-plus-plus --disable-openmp
1. make
1. make install

Build imagequant
----------------

1. replace Makefile, add config.mk
2. make
3. copy libimagequant.so and all *.h files to ${INSTALL_DIR}
