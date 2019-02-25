cmake_minimum_required(VERSION 2.6)
project (faizan531)

include_directories(${CMAKE_SOURCE_DIR}/include)
link_directories(${CMAKE_SOURCE_DIR}/lib)

set(SOURCES src/driver.c)
add_executable(myapp ${PROJECT_SOURCE_DIR}/${SOURCES})

target_link_libraries(myapp libc.so libmyfunction.a)

install(TARGETS myapp DESTINATION /usr/bin)
install(FILES man/prog2.3 DESTINATION /usr/share/man/man3)

include(InstallRequiredSystemLibraries)
set(CPACK_GENERATOR "DEB")
set(CPACK_DEBIAN_PACKAGE_MAINTAINER "Faizan Murtaza")
include(CPack)
