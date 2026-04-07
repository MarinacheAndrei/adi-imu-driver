set(HEADERS
    adi_imu_driver.h
)

set(SOURCES
    adi_imu_driver.c
)

add_library(adi_imudriver_lib
    ${SOURCES}
    ${HEADERS}
)

target_link_libraries(adi_imudriver_lib
    PUBLIC
        adi_common_lib
)

target_include_directories(adi_imudriver_lib
    PUBLIC
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>
        $<BUILD_INTERFACE:${CMAKE_CURRENT_BINARY_DIR}>
        $<INSTALL_INTERFACE:include>
)