# CMakeList.txt : CMake project for RuiTemplate, include source and define
# project specific logic here.
#


file(GLOB SRC_FILES "${ImportFolder}/*.cpp")



add_library (RuiTemplate SHARED "RuiTemplate.cpp" ${SRC_FILES})

set_target_properties(RuiTemplate PROPERTIES OUTPUT_NAME "${ExportDllName}")

target_include_directories(RuiTemplate PRIVATE ${CMAKE_CURRENT_SOURCE_DIR})


if (CMAKE_VERSION VERSION_GREATER 3.12)
  set_property(TARGET RuiTemplate PROPERTY CXX_STANDARD 20)
endif()

# TODO: Add tests and install targets if needed.
