remake_find_package(Boost COMPONENTS unit_test_framework program_options
  RESULT_VAR Boost_FOUND)

remake_include(../lib ${Boost_INCLUDE_DIR})

remake_add_directories(tests COMPONENT tests)
remake_add_directories(examples COMPONENT examples)
remake_add_directories(utils COMPONENT utils)
