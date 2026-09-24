if(IDF_VERSION_MAJOR GREATER_EQUAL 5)
    set(SPI_DRIVER_DEP esp_driver_spi)
else()
    set(SPI_DRIVER_DEP driver)
endif()

idf_component_register(
    SRCS "mcp2515.cpp"
    INCLUDE_DIRS include
    REQUIRES ${SPI_DRIVER_DEP}
)
