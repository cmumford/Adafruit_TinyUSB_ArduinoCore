file( GLOB SOURCES *.cpp )

idf_component_register(
    SRCS
        ${SOURCES}
    INCLUDE_DIRS
        "include"
        "${CMAKE_SOURCE_DIR}/components/Adafruit_TinyUSB_ArduinoCore/include"
        "${CMAKE_SOURCE_DIR}/components/tinyusb/src"
        "${CMAKE_SOURCE_DIR}/components/tinyusb/src/class"
        "${CMAKE_SOURCE_DIR}/components/tinyusb/src/device"
        "${CMAKE_SOURCE_DIR}/main"
        "${IDF_PATH}/components/freertos/include/freertos"
    REQUIRES
        tinyusb
        freertos
)

target_compile_options(
  ${COMPONENT_TARGET} PUBLIC
  "-DCFG_TUSB_MCU=OPT_MCU_ESP32S2"
)