cmake_minimum_required(VERSION 3.7.0)

project(Thread_Cancel)

set (CMAKE_C_FLAGS "-D_GNU_SOURCE -Wall -std=c99")
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)
set(LIBRARY_OUTPUT_PATH ${CMAKE_BINARY_DIR}/lib)
set(CMAKE_BUILD_TYPE Debug)


#build thread
add_executable(thread "")

target_link_libraries(thread PUBLIC hardware pthread)

target_sources(thread
  PUBLIC 
  ${CMAKE_CURRENT_LIST_DIR}/src/thread_cancel.c
  )

target_include_directories(thread 
  PUBLIC 
  ${CMAKE_CURRENT_LIST_DIR}/lib  
  )

install(TARGETS thread DESTINATION bin)