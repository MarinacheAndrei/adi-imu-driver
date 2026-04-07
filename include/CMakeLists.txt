# Generate the config header
configure_file(
    ${CMAKE_CURRENT_SOURCE_DIR}/adi_imu_common.h.in
    ${CMAKE_CURRENT_BINARY_DIR}/adi_imu_common.h
    @ONLY
)

set(HEADERS
    ${CMAKE_CURRENT_SOURCE_DIR}/adi_imu_regmap.h
    ${CMAKE_CURRENT_SOURCE_DIR}/imu_spi_buffer_regmap.h    
    ${CMAKE_CURRENT_BINARY_DIR}/adi_imu_common.h
)

# Create header-only INTERFACE library
add_library(adi_common_lib INTERFACE)

# Expose headers to consumers
target_include_directories(adi_common_lib INTERFACE
    ${CMAKE_CURRENT_SOURCE_DIR}          # original headers
    ${CMAKE_CURRENT_BINARY_DIR}          # generated header
)