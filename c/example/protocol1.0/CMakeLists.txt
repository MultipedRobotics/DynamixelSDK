# add_executable(ping/ping.c)
# target_link_libraries(ping PUBLIC ${PROJECT_NAME})

list(APPEND sources
    bulk_read.c
    ping.c
    multi_port.c
    read_write.c
    reset.c
    sync_write.c
)

foreach(src ${sources})
    get_filename_component(name ${src} NAME_WE)
    message(STATUS " -> ${name}")
    add_executable(${name} ${src})
    target_link_libraries(${name} ${PROJECT_NAME})
    # add_test(NAME ${name} COMMAND ${name})
endforeach()
