cmake_minimum_required(VERSION 2.8)

project(variant CXX)

add_library(variant INTERFACE)
if (DEFINED THIRD_PARTY_INCLUDES_AS_SYSTEM AND NOT THIRD_PARTY_INCLUDES_AS_SYSTEM)
  target_include_directories(variant INTERFACE
      $<BUILD_INTERFACE:${PROJECT_SOURCE_DIR}/include>)
else()
  target_include_directories(variant SYSTEM INTERFACE
      $<BUILD_INTERFACE:${PROJECT_SOURCE_DIR}/include>)
endif()