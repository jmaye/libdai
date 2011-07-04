remake_find_package(Boost)

remake_include(${Boost_INCLUDE_DIR})

remake_add_library(dai PREFIX off)
remake_add_headers()
