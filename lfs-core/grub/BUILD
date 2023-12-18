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

patch -Np1 -i ${SOURCE_CACHE}/grub-2.06-upstream_fixes-1.patch

./configure --prefix=/usr          \
            --sysconfdir=/etc      \
            --disable-efiemu       \
            --disable-werror

make
