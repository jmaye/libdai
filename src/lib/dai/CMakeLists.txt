remake_find_package(Boost COMPONENTS graph)
remake_find_library(gmpxx gmpxx.h PACKAGE libgmp3-dev)

remake_include(${Boost_INCLUDE_DIR})

remake_add_library(dai PREFIX off LINK ${GMPXX_LIBRARY})
remake_add_headers()
