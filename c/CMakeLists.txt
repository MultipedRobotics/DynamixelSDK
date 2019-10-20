cmake_minimum_required(VERSION 3.10.0)
project(dynamixel VERSION 0.5.1 LANGUAGES C)

file(GLOB SOURCES src/dynamixel_sdk/*.c)

add_library(${PROJECT_NAME} SHARED ${SOURCES})
# target_link_libraries(${PROJECT_NAME}
#     PUBLIC
#         ${ALL_LIBS}
#         marko
# )
target_include_directories(${PROJECT_NAME}
    PUBLIC
        include/dynamixel_sdk
)

# add_executable(ping example/protocol1.0/ping/ping.c)
# target_link_libraries(ping PUBLIC ${PROJECT_NAME})
add_subdirectory(example)
