if(${verbose_traversal})
  message(STATUS "Entered GenHayes/Tests subdirectory")
endif(${verbose_traversal})

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "${CMAKE_CURRENT_BINARY_DIR}")

file(GLOB Test_c  RELATIVE "${CMAKE_CURRENT_SOURCE_DIR}" "*.C")

foreach( test_c ${Test_c} )
  get_filename_component( test ${test_c} NAME_WE )
  add_executable(${test} ${test_c})
  target_link_libraries( ${test} GenHayes EOS )
endforeach( test_c )

set(BLESSED_OUTPUT ${EOSLIB_BLESSED_OUTPUT}/EOStypes/GenHayes)


if(${verbose_traversal})
  message(STATUS "Exiting GenHayes/Tests subdirectory")
endif(${verbose_traversal})
