###############################################################################
# Macros
###############################################################################

macro(ecl_ipc_add_gtest test_name)
  ament_add_gtest(ecl_test_${test_name} ${test_name}.cpp)
  if(TARGET ecl_test_${test_name})
    target_link_libraries(
      ecl_test_${test_name}
      ${PROJECT_NAME}
      ecl_exceptions::ecl_exceptions
      ecl_time::ecl_time
    )
  endif()
endmacro()

###############################################################################
# Google Tests
###############################################################################

ecl_ipc_add_gtest(shared_memory)
ecl_ipc_add_gtest(semaphores)
ecl_ipc_add_gtest(semaphores_timed)

