cmake_minimum_required (VERSION 2.6)

project (libnanosvg)

set (libnanosvg_VERSION_MAJOR 0)
set (libnanosvg_VERSION_MINOR 1)

# configure_file (
#   "${PROJECT_SOURCE_DIR}/TutorialConfig.h.in"
#   "${PROJECT_BINARY_DIR}/TutorialConfig.h"
#   )

include_directories("${CMAKE_CURRENT_SOURCE_DIR}")

add_library(nanosvg SHARED nanosvg.c nanosvgrast.c)
# add_executable(libnanosvg nanosvg.c nanosvgrast.c)

install(TARGETS nanosvg DESTINATION lib)
install(FILES nanosvg.h DESTINATION include)

# uninstall target
configure_file(
    "${CMAKE_CURRENT_SOURCE_DIR}/cmake_uninstall.cmake.in"
    "${CMAKE_CURRENT_BINARY_DIR}/cmake_uninstall.cmake"
    IMMEDIATE @ONLY)

add_custom_target(uninstall
    COMMAND ${CMAKE_COMMAND} -P ${CMAKE_CURRENT_BINARY_DIR}/cmake_uninstall.cmake)
