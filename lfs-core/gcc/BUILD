####################################################################
#
#
#
####################################################################

# clear optimizations
unset CFLAGS
unset CXXFLAGS
unset CPPFLAGS
unset LDFLAGS

####################################################################
# BUILD

case $(uname -m) in
  x86_64)
    sed -e '/m64=/s/lib64/lib/' \
        -i.orig gcc/config/i386/t-linux64
  ;;
esac

mkdir -v build
cd       build

../configure --prefix=/usr            \
             LD=ld                    \
             --enable-languages=c,c++ \
             --enable-default-pie     \
             --enable-default-ssp     \
             --disable-multilib       \
             --disable-bootstrap      \
             --disable-fixincludes    \
             --with-system-zlib

make

#ulimit -s 32768

#chown -Rv tester .
#su tester -c "PATH=$PATH make -k check"

#../contrib/test_summary

####################################################################
# TEMP INSTALL

mkdir -p "${SOURCE_DIRECTORY}.bld/"
make  DESTDIR="${SOURCE_DIRECTORY}.bld" install
