source /opt/devkitpro/switchvars.sh
./bootstrap.sh --prefix=$PORTLIBS_PREFIX

project-config.jam > "using gcc : aarch64 : aarch64-none-elf-g++ ;"

./b2 install toolset=gcc-aarch64 link=static runtime-link=static linkflags="-pthread" cxxflags="$CXXFLAGS $CPPFLAGS -D_POSIX_THREADS -DBOOST_HAS_PTHREADS" threading=multi --with-filesystem --with-system --with-random --with-regex --with-program_options --with-locale --with-iostreams --with-thread
