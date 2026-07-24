cmake_minimum_required(VERSION 3.10)
project(PSVR2Camera)

set(CMAKE_CXX_STANDARD 20)

add_executable(PSVR2Camera WIN32
    main.cpp
    distortion.cpp
    renderer.cpp
    shared_memory.cpp
)

target_link_libraries(PSVR2Camera 
    d3d11.lib 
    d3dcompiler.lib 
    dxgi.lib
)

install(TARGETS MyExecutable DESTINATION bin)
install(FILES README.md DESTINATION .)

set(CPACK_PACKAGE_NAME "PSVR2Camera")
set(CPACK_PACKAGE_VERSION "0.2.0")
set(CPACK_GENERATOR "ZIP")

include(CPack)
