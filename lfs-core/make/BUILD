####################################################################
#
#
#
####################################################################

####################################################################
# BUILD

./configure --prefix=/usr

make

#chown -Rv tester .
#su tester -c "PATH=$PATH make check"


# TEMP INSTALL
mkdir -p "${SOURCE_DIRECTORY}.bld/"
make  DESTDIR="${SOURCE_DIRECTORY}.bld" install
