project(tracking)

set(
  SRC
  connection.cpp
  connection.hpp
  protocol.cpp
  protocol.hpp
  reporter.cpp
  reporter.hpp
  archival_file.cpp
  archival_file.hpp
  archival_manager.cpp
  archival_manager.hpp
  archival_reporter.cpp
  archival_reporter.hpp
  archive.cpp
  archive.hpp
)

omim_add_library(${PROJECT_NAME} ${SRC})

target_include_directories(${PROJECT_NAME} PRIVATE "${OMIM_ROOT}/3party/boost")

omim_add_test_subdirectory(tracking_tests)

if (USE_LIBFUZZER)
  add_subdirectory(tracking_fuzz_tests)
endif()
