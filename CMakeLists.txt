cmake_minimum_required(VERSION 2.6)

include(ReMake)

remake_project(
  libdai
  VERSION 0.3
  RELEASE beta
  SUMMARY "A free/open source C++ library for Discrete Approximate Inference"
  AUTHOR "Joris M. Mooij"
  CONTACT "joris.mooij@libdai.org"
  HOME "http://aslforge.ethz.ch/projects/libdai"
  LICENSE "BSD 2-Clause License (FreeBSD)"
  PREFIX dai-
  INSTALL /usr
  HEADER_DESTINATION include/dai
)

remake_doc(
  html
  latex
)

remake_add_directories(
  data
  COMPONENT data
)

remake_pack_deb(
  libgmp3-dev
  libgmpxx4ldbl
)

remake_pack_deb(
  COMPONENT dev
  DESCRIPTION "Development headers"
  libdai
  libboost-dev
)

remake_pack_deb(
  COMPONENT tests
  DESCRIPTION "Test programs"
  libdai
)

remake_pack_deb(
  COMPONENT examples
  DESCRIPTION "Examples programs"
  libdai
)

remake_pack_deb(
  COMPONENT utils
  DESCRIPTION "Utility programs"
  libdai
)

remake_pack_deb(
  COMPONENT doc
  DESCRIPTION "Documentation"
  libdai
)

remake_pack_deb(
  COMPONENT data
  DESCRIPTION "Data for examples, tests and utils"
)
