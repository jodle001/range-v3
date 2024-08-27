cmake_minimum_required(VERSION 3.15)
project(range_v3 LANGUAGES CXX)

# Find dependencies
find_package(ament_cmake REQUIRED)

# Create interface library for range-v3
add_library(${PROJECT_NAME} INTERFACE)

# Set include directories for the interface library
target_include_directories(${PROJECT_NAME} INTERFACE
    $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
    $<INSTALL_INTERFACE:include>
)

# Optionally, specify any required compiler features or definitions
target_compile_features(${PROJECT_NAME} INTERFACE cxx_std_17)


# Install headers
install(DIRECTORY include/ DESTINATION include/)

# Install the fp library
install(
    TARGETS ${PROJECT_NAME}
    EXPORT ${PROJECT_NAME}Targets
    INCLUDES DESTINATION include
)

add_subdirectory(perf)

# Export the library
ament_export_dependencies(ament_cmake)
ament_export_include_directories(include)
ament_export_targets(${PROJECT_NAME}Targets)
ament_package()
