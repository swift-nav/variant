project(variant CXX)
cmake_minimum_required(VERSION 2.8)

add_library(variant INTERFACE)
if(NOT CMAKE_CROSSCOMPILING OR THIRD_PARTY_INCLUDES_AS_SYSTEM)
  target_include_directories(variant
      SYSTEM INTERFACE $<BUILD_INTERFACE:${PROJECT_SOURCE_DIR}/include>
      )
else()
  target_include_directories(variant
      INTERFACE $<BUILD_INTERFACE:${PROJECT_SOURCE_DIR}/include>
      )
endif()

