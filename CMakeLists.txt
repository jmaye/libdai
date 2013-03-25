cmake_minimum_required(VERSION 2.6)

include(ReMake)

remake_project(
  libdai
  VERSION 0.3.1
  RELEASE beta
  SUMMARY "A free/open source C++ library for Discrete Approximate Inference"
  AUTHOR "Joris M. Mooij"
  CONTACT "joris.mooij@libdai.org"
  HOME "http://www.libdai.org"
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
  DEPENDS libgmpxx4ldbl
)

remake_pack_deb(
  COMPONENT dev
  DESCRIPTION "Development headers"
  DEPENDS libdai libgmp3-dev libboost-all-dev
)

remake_pack_deb(
  COMPONENT tests
  DESCRIPTION "Test programs"
  DEPENDS libdai libboost-program-options[0-9.]*
)

remake_pack_deb(
  COMPONENT examples
  DESCRIPTION "Examples programs"
  DEPENDS libdai libx11-[0-9.]*
)

remake_pack_deb(
  COMPONENT utils
  DESCRIPTION "Utility programs"
  DEPENDS libdai libboost-program-options[0-9.]*
)

remake_pack_deb(
  COMPONENT doc
  DESCRIPTION "Documentation"
  DEPENDS libdai
)

remake_pack_deb(
  COMPONENT data
  DESCRIPTION "Data for examples, tests and utils"
  DEPENDS libdai
)

remake_distribute_deb(
  DISTRIBUTION lucid
  SECTION libs
  UPLOAD ppa:jmaye/ethz
  DEPENDS remake doxygen libgmp3-dev libboost-all-dev cimg-dev graphviz texlive
    texlive-extra-utils texlive-font-utils ghostscript
  PASS CMAKE_BUILD_TYPE LIBDAI_SUBVERSION_REVISION
)

remake_distribute_deb(
  DISTRIBUTION precise
  SECTION libs
  UPLOAD ppa:jmaye/ethz
  DEPENDS remake doxygen libgmp3-dev libboost-all-dev cimg-dev graphviz texlive
    texlive-extra-utils texlive-font-utils ghostscript
  PASS CMAKE_BUILD_TYPE LIBDAI_SUBVERSION_REVISION
)
