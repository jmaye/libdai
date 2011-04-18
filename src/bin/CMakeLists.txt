remake_include(../lib)
remake_find_library(boost_program_options-mt boost/program_options.hpp
  PACKAGE libboost-program-options-dev)
remake_add_directories(tests COMPONENT tests)
remake_add_directories(examples COMPONENT examples)
remake_add_directories(utils COMPONENT utils)
