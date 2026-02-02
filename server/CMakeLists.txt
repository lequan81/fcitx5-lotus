find_package(PkgConfig REQUIRED)

pkg_check_modules(LIBINPUT REQUIRED IMPORTED_TARGET libinput)
pkg_check_modules(LIBUDEV  REQUIRED IMPORTED_TARGET libudev)

add_executable(fcitx5-vmk-server vmk-server.cpp)

target_link_libraries(fcitx5-vmk-server
    PkgConfig::LIBINPUT
    PkgConfig::LIBUDEV
)

install(TARGETS fcitx5-vmk-server DESTINATION ${CMAKE_INSTALL_BINDIR})
