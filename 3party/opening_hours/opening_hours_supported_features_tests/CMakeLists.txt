project(opening_hours_supported_features_tests)

set(SRC
  opening_hours_supported_features_tests.cpp
)

omim_add_executable(${PROJECT_NAME} ${SRC})

target_include_directories(${PROJECT_NAME} PRIVATE "${OMIM_ROOT}/3party/boost")

target_link_libraries(${PROJECT_NAME} opening_hours)
