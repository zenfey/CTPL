cmake_minimum_required(VERSION 3.7)

add_executable(example_ctpl example.cpp)
target_link_libraries(example_ctpl PRIVATE
  CTPL
  )
target_compile_options(example_ctpl PRIVATE -Wall -Wextra)
