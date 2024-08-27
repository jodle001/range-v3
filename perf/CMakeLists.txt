set(CMAKE_FOLDER "perf")

add_executable(range_v3_counted_insertion_sort counted_insertion_sort.cpp)
target_link_libraries(range_v3_counted_insertion_sort range_v3)
#
#add_executable(range_v3_range_conversion range_conversion.cpp)
#target_link_libraries(range_v3_range_conversion range_v3 benchmark_main)
#
#add_executable(range_v3_sort_patterns sort_patterns.cpp)
#target_link_libraries(range_v3_sort_patterns range_v3)
