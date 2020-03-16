
find_package(libuv REQUIRED)

add_library(uSockets
    context.c
    loop.c
    socket.c
    eventing/libuv.c
    )

target_include_directories(uSockets PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})

# TODO: make this an OPTION
target_compile_definitions(uSockets PUBLIC LIBUS_NO_SSL)

# Use libuv because because it isolates the underlying platform and is fast
target_compile_definitions(uSockets PUBLIC WITH_LIBUV LIBUS_USE_LIBUV)

target_link_libraries(uSockets LibUV::LibUV)
