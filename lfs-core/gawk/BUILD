####################################################################
#
#
#
####################################################################

####################################################################
# BUILD

sed -i 's/extras//' Makefile.in

./configure --prefix=/usr

make

#chown -Rv tester .
#su tester -c "PATH=$PATH make check"

# TEMP INSTALL
mkdir -p "${SOURCE_DIRECTORY}.bld/"
make  DESTDIR="${SOURCE_DIRECTORY}.bld" install

ln -svf ${SOURCE_DIRECTORY}.bld/usr/bin/gawk /usr/bin/awk
