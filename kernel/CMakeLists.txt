set(BASE "${CMAKE_CURRENT_SOURCE_DIR}")

set(
    SOURCES
    "${BASE}/build.cpp"
    "${BASE}/entwine.cpp"
    "${BASE}/infer.cpp"
    "${BASE}/merge.cpp"
    "${BASE}/rebase.cpp"
)

add_executable(kernel ${SOURCES})
add_dependencies(kernel entwine)

target_link_libraries(kernel entwine ${Backtrace_LIBRARIES})
set_target_properties(kernel PROPERTIES OUTPUT_NAME entwine)

install(TARGETS kernel DESTINATION bin)

