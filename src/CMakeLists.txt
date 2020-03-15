
include_directories(${CMAKE_CURRENT_SOURCE_DIR})

add_library(uSockets
    context.c
    loop.c
    socket.c
    eventing/libuv.c
    )

# TODO: make this an OPTION
target_compile_definitions(uSockets PUBLIC LIBUS_NO_SSL)

# Use libuv because because it isolates the underlying platform and is fast
target_compile_definitions(uSockets PUBLIC WITH_LIBUV)
