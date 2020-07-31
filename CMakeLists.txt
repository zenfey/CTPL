cmake_minimum_required(VERSION 3.7)
project(CTPL)

# Option.
set(CTPL_BuildTests "build tests" ON)

# packages
find_package(Threads REQUIRED)

# Target.
add_library(CTPL INTERFACE)
target_include_directories(CTPL INTERFACE
  $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
  $<INSTALL_INTERFACE:include>)
target_link_libraries(CTPL INTERFACE
  Threads::Threads
)  

# tests.
if(CTPL_BuildTests)
  add_subdirectory(tests)
endif()

