list(APPEND sources
    # bulk_read.c
    ping.c
    multi_port.c
    read_write.c
    # reset.c
    sync_read_write.c
)

foreach(src ${sources})
    get_filename_component(name ${src} NAME_WE)
    message(STATUS " -> ${name}2")
    add_executable(${name}2 ${src})
    target_link_libraries(${name}2 ${PROJECT_NAME})
    # add_test(NAME ${name} COMMAND ${name})
endforeach()
