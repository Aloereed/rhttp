# The Flutter tooling requires that developers have CMake 3.10 or later
# installed. You should not increase this version, as doing so will cause
# the plugin to fail to compile for some customers of the plugin.
cmake_minimum_required(VERSION 3.10)

# Project-level configuration.
set(PROJECT_NAME "rhttp")
set(TARGET_LIB_DIR ${CMAKE_CURRENT_SOURCE_DIR}/../libs/${OHOS_ARCH})
project(${PROJECT_NAME} LANGUAGES CXX)
if (NOT DEFINED FLUTTER_TARGET_PLATFORM)
  set(FLUTTER_TARGET_PLATFORM "ohos-arm64")
endif()
include("../../cargokit/cmake/cargokit.cmake")
apply_cargokit(${PROJECT_NAME} ../../rust rhttp "")


# List of absolute paths to libraries that should be bundled with the plugin.
# This list could contain prebuilt libraries, or libraries created by an
# external build triggered from this build file.
# set(rhttp_bundled_libraries
#   "${${PROJECT_NAME}_cargokit_lib}"
#   PARENT_SCOPE
# )
