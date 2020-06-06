cmake_minimum_required(VERSION 3.4)
project(solver)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)


add_library(solver_lib STATIC ${CMAKE_CURRENT_SOURCE_DIR}/../solver_lib/solver.cpp ${CMAKE_CURRENT_SOURCE_DIR}/../formatter_ex_lib/formatter_ex.cpp ${CMAKE_CURRENT_SOURCE_DIR}/../formatter_lib/formatter.cpp)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/../solver_lib ${CMAKE_CURRENT_SOURCE_DIR}/../formatter_ex_lib ${CMAKE_CURRENT_SOURCE_DIR}/../formatter_lib)

add_executable(solver ${CMAKE_CURRENT_SOURCE_DIR}/equation.cpp)
target_link_libraries(solver solver_lib)


install(TARGETS solver
	ARCHIVE DESTINATION lib
	RUNTIME DESTINATION bin
)
