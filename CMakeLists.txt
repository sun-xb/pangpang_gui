cmake_minimum_required(VERSION 3.0.0)
project(pangpang_gui VERSION 0.1.0)


set(wxBUILD_SHARED OFF)
set(wxBUILD_MONOLITHIC ON)
add_subdirectory(3rdparty/wxWidgets)

include(CTest)
enable_testing()



set(TARGET pp)
add_executable(${TARGET} src/main.cpp)
#target_link_libraries(${TARGET} wx::core wx::base wx::aui wx::html)
target_link_libraries(${TARGET} wx::mono)
set_target_properties(${TARGET} PROPERTIES WIN32_EXECUTABLE true)

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)

