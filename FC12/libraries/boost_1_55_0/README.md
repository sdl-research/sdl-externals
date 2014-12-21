FIRST_PREFIX=$XMT_EXTERNALS_PATH/FC12/libraries/boost_1_55_0
withouts="--without-mpi --without-python --without-wave"
./bootstrap.sh --prefix=$FIRST_PREFIX
/bjam cxxflags=-fPIC --runtime-link=static,shared --prefix=$FIRST_PREFIX $withouts --runtime-debugging=off -j${MAKEPROC:=8} install
