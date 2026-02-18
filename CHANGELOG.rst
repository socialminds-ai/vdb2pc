^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Changelog for package vdb2pc
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Forthcoming
-----------
* compat with jazzy
  - avoid CMake conflict with TBB
  - depend on libopenvdb instead of specific libopenvdb8.2
  - USE_SCOPED_HEADERS
* Contributors: Séverin Lemaignan

0.2.0 (2025-06-26)
------------------
* it's linting over everything
  Trailing spaces vanish,
  Tabs and spaces reconciled—
  Code breathes peacefully.
* removed ETHICAL_STATEMENT and MAINTENANCE_NOTE
* fix spacing in README
* fixed linking
* build_export libopenvdb-dev
* Contributors: Lorenzo Ferrini, Séverin Lemaignan

0.1.0 (2025-02-13)
------------------
* improve package.xml
* added libopenvdb-dev key to package.xml
* fix wrong openvdb key in package.xml
* making linters happy
* CMakeLists refactoring
  This commit also includes the removal of an unused testing node.
* package.xml de-anonymization + ament_cmake --> ament_cmake_auto
* anonymization
* polish MAINTENANCE_NOTE
* maintenance and ethical statements
* anonymization
* updated README
* updated package.xml
* minor - code refactoring
* Wip - The License type has been changed from Apache-2.0 to LGPLv3, and the noticing text has been properly modified.
* Wip - Removed the comments related to the included header files.
* Wip - The namespace 'vdb_utilities' has been renamed 'ros_utils' and placed within the namespace 'vdb2pc'. Moreover, the files 'vdb2pc_pub.*' have been renamed 'vdb2pc_publisher.*'.
* Wip - The remaining 'this' pointers have been removed.
* Wip - Global variables have been removed. The callback function has been templatized.
* Wip - In the 'VDB2PCPublisher' class, the name of each attribute and the sign of each method has been made coherent with the C++ convention.
* Wip - The 'VDB2PointCloud' class has been removed and its method have been converted into functions.
* Wip - The 'VDB2PCPublisher' class uses the node pointer passed to the constructor to create the publisher.
* Wip - Separators removed
* Wip - The namespaces 'vdb_utilities' and 'ros_vdb_utilities' have been renamed 'vdb2pc' and 'ros_vdb2pc', respectively.
* Wip - Apache 2 license headers added
* Wip - Fixed dependencies
* Wip - Publishing of a Grid on a Topic (Added)
* Wip - Porting vdb2pc to ROS2
* Initial commit
* Contributors: Joe, Lorenzo, Lorenzo Ferrini, lorenzoferrini
