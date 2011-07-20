remake_find_package(Boost)
remake_find_library(gmp gmp.h PACKAGE libgmp3-dev)
remake_find_library(gmpxx gmpxx.h PACKAGE libgmpxx4ldbl)

remake_include(${Boost_INCLUDE_DIR})

remake_add_library(dai PREFIX off LINK ${GMP_LIBRARY} ${GMPXX_LIBRARY})
remake_add_headers()
