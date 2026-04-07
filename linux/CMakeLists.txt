set(HEADERS
    gpio.h
    spi_driver.h
    uart_driver.h
    utils.h    
)

set(SOURCES
    gpio.c
    hw_main.c
    spi_driver.c
    uart_driver.c
    utils.c
)

if(DEBUG_SPI)
target_compile_definitions(adi_linux_lib PRIVATE -DDEBUG_SPI)
message("DEBUG_SPI ENABLED")
endif()

if(DEBUG_UART)
target_compile_definitions(adi_linux_lib PRIVATE -DDEBUG_UART)
message("DEBUG_UART ENABLED")
endif()


add_library(adi_linux_lib
    ${SOURCES}
    ${HEADERS}
)

target_link_libraries(adi_linux_lib
    PUBLIC
        adi_common_lib
        adi_spibuffer_lib
        adi_imudriver_lib
)

target_include_directories(adi_linux_lib
    PUBLIC
        ${CMAKE_CURRENT_BINARY_DIR}
)