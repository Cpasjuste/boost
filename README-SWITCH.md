source /opt/devkitpro/switchvars.sh
./bootstrap.sh --prefix=$PORTLIBS_PREFIX
project-config.jam > "using gcc : aarch64 : aarch64-none-elf-g++ ;"
./b2 install toolset=gcc-aarch64 link=static runtime-link=static cxxflags="$CXXFLAGS $CPPFLAGS" --with-filesystem --with-system --with-random --with-regex --with-program_options --with-locale --with-iostreams
