####################################################################
#
#
#
####################################################################

####################################################################
# BUILD

patch -Np1 -i ${SOURCE_CACHE}/kbd-2.6.1-backspace-1.patch

sed -i '/RESIZECONS_PROGS=/s/yes/no/' configure
sed -i 's/resizecons.8 //' docs/man/man8/Makefile.in

./configure --prefix=/usr --disable-vlock

make

#make check
