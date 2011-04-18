remake_define(BOOST_TEST_DYN_LINK true)
remake_find_library(boost_unit_test_framework-mt boost/test/unit_test.hpp
  PACKAGE libboost-test-dev)
remake_add_executables(TESTING LINK dai ${BOOST_UNIT_TEST_FRAMEWORK_MT_LIBRARY})
