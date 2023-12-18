####################################################################
#
#
#
####################################################################

####################################################################
# BUILD

patch -Np1 -i ${SOURCE_CACHE}/coreutils-9.3-i18n-1.patch

autoreconf -fiv
FORCE_UNSAFE_CONFIGURE=1 ./configure \
            --prefix=/usr            \
            --enable-no-install-program=kill,uptime

make

#make NON_ROOT_USERNAME=tester check-root

#groupadd -g 102 dummy -U tester

#chown -Rv tester .

#su tester -c "PATH=$PATH make RUN_EXPENSIVE_TESTS=yes check"

#groupdel dummy


# TEMP INSTALL

mkdir -p "${SOURCE_DIRECTORY}.bld/"
make  DESTDIR="${SOURCE_DIRECTORY}.bld" install
