cmake_minimum_required (VERSION 2.6)
project (BMP180)

set(CMAKE_CURRENT_SOURCE_DIR .)

set(INCLUDE .)

SET(CMAKE_INSTALL_RPATH_USE_LINK_PATH TRUE)
set(CMAKE_INSTALL_PREFIX /usr/)

set(BMP180_SOURCE
  bmp180.cpp
  firmware_i2c.cpp
)

set(BMP180_HEADERS
  bmp180.h
  firmware_i2c.h
)

add_library(bmp180 SHARED ${BMP180_SOURCE} ${BMP180_HEADERS})
target_link_libraries(bmp180)

set_target_properties(bmp180 PROPERTIES
  VERSION 1.0.0
  SOVERSION 1
)
