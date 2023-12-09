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

patch -Np1 -i ${SOURCE_CACHE}/glibc-2.38-fhs-1.patch
patch -Np1 -i ${SOURCE_CACHE}/glibc-2.38-memalign_fix-1.patch

mkdir -v build
cd       build

echo "rootsbindir=/usr/sbin" > configparms

../configure --prefix=/usr                            \
             --disable-werror                         \
             --enable-kernel=4.14                     \
             --enable-stack-protector=strong          \
             --with-headers=/usr/include              \
             libc_cv_slibdir=/usr/lib

make

####################################################################
# TEMP INSTALL

mkdir -p "${SOURCE_DIRECTORY}.bld/"
make  DESTDIR="${SOURCE_DIRECTORY}.bld" install

# TEMP LINK LIBS
ln -sfv ${SOURCE_DIRECTORY}.bld/usr/lib/ld-linux-x86-64.so.2 \
		/lib64
ln -sfv ${SOURCE_DIRECTORY}.bld/lib/ld-linux-x86-64.so.2 \
		/lib64/ld-lsb-x86-64.so.3

ldconfig ${SOURCE_DIRECTORY}.bld/usr/lib/

ls -al /lib64

message "${MESSAGE_COLOR}Deleting glibc, press ctrl-c to \
cancel ${DEFAULT_COLOR}"
sleep 30
