set(HEADERS
    imu_spi_buffer.h
)

set(SOURCES
    imu_spi_buffer.c
)

add_library(adi_spibuffer_lib
    ${SOURCES}
    ${HEADERS}
)

target_link_libraries(adi_spibuffer_lib
    PUBLIC
        adi_common_lib
)

target_include_directories(adi_spibuffer_lib
    PUBLIC
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>
        $<BUILD_INTERFACE:${CMAKE_CURRENT_BINARY_DIR}>
        $<INSTALL_INTERFACE:include>
)