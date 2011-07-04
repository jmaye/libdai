remake_define(NEW_CIMG true)
remake_find_package(X11)
remake_find_package(Threads)
if(NOT ${CMAKE_USE_PTHREADS_INIT})
  message(FATAL_ERROR "Missing POSIX thread support!")
endif(NOT ${CMAKE_USE_PTHREADS_INIT})
remake_find_file(CImg.h PACKAGE cimg-dev)

remake_include(${CIMG_DEV_FILE})

remake_add_executables(LINK dai ${X11_LIBRARIES} ${CMAKE_THREAD_LIBS_INIT})
