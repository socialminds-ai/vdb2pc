cmake_minimum_required(VERSION 3.8)
project(vdb2pc)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

find_package(ament_cmake_auto REQUIRED)

# Find TBB via its system config BEFORE OpenVDB, to prevent OpenVDB's
# bundled FindTBB.cmake from creating a partial TBB::tbb target that
# later conflicts with the full TBB target set expected by VTK/PCL.
find_package(TBB CONFIG REQUIRED)

# Use CMAKE_LIBRARY_ARCHITECTURE for arch-independent path
# (resolves to x86_64-linux-gnu or aarch64-linux-gnu automatically)
list(APPEND CMAKE_MODULE_PATH "/usr/lib/${CMAKE_LIBRARY_ARCHITECTURE}/cmake/OpenVDB")
find_package(OpenVDB MODULE REQUIRED)
ament_auto_find_build_dependencies()

include_directories(
  include/vdb2pc
)

ament_auto_add_library(${PROJECT_NAME}_lib SHARED
  src/vdb2pc.cpp
  src/vdb2pc_publisher.cpp
)

target_link_libraries(${PROJECT_NAME}_lib
  ${OpenVDB_LIBRARIES} ${PCL_LIBRARIES})

ament_export_include_directories(
  include
)

ament_export_libraries(
  ${PROJECT_NAME}_lib
)

install(
  DIRECTORY include/vdb2pc
  DESTINATION include
)

if(BUILD_TESTING)
  ament_auto_find_test_dependencies()
  ament_lint_auto_find_test_dependencies()
endif()

ament_auto_package(USE_SCOPED_HEADER_INSTALL_DIR)
