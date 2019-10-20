
list(APPEND sources1
    # dxl_monitor.c
    protocol_combined.c
)

foreach(src ${sources1})
    get_filename_component(name ${src} NAME_WE)
    message(STATUS " -> ${name}")
    add_executable(${name} ${src})
    target_link_libraries(${name} ${PROJECT_NAME})
    # add_test(NAME ${name} COMMAND ${name})
endforeach()


add_subdirectory(protocol1.0)
add_subdirectory(protocol2.0)
