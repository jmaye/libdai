cmake_minimum_required(VERSION 2.6)

include(ReMake)

remake_project(
  libdai
  VERSION 0.1
  RELEASE alpha
  SUMMARY "A free/open source C++ library for Discrete Approximate Inference"
  AUTHOR "Joris M. Mooij"
  CONTACT "joris.mooij@libdai.org"
  HOME "http://aslforge.ethz.ch/projects/libdai"
  LICENSE "GNU General Public License (GPL)"
  PREFIX dai-
  INSTALL /usr
)

remake_doc(
  html
)

remake_pack_deb(libboost-program-options-dev)

remake_pack_deb(
  COMPONENT dev
  DESCRIPTION "Development headers"
  libdai
)

remake_pack_deb(
  COMPONENT tests
  DESCRIPTION "Test programs"
  libdai
)

remake_pack_deb(
  COMPONENT examples
  DESCRIPTION "Examples programs"
  libdai cimg-dev
)

remake_pack_deb(
  COMPONENT utils
  DESCRIPTION "Utility programs"
  libdai
)

remake_pack_deb(
  COMPONENT doc
  DESCRIPTION "Documentation"
)
