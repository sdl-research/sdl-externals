use homebrew instead:

    brew install homebrew/versions/gcc6

    brew edit boost # remove the 'patch' sections
    brew uninstall boost
    brew install boost --c++11 --with-gcc=gcc-6 --HEAD

    brew edit log4cxx # remove the 'patch' sections and add:
    # head "http://svn.apache.org/repos/asf/incubator/log4cxx/trunk"
    brew uninstall log4cxx
    brew install --c++11 --with-gcc=gcc-6 log4cxx --HEAD

    brew uninstall icu4c
    brew install icu4c --c++11 --with-gcc=gcc-6

    brew uninstall berkeley-db
    brew install berkeley-db --c++11 --with-gcc=gcc-6
    brew link --force berkeley-db

you might need to `cmake -DSDL_BOOST_MINOR=61` or edit CMakeLists.txt
for boost 1.61
