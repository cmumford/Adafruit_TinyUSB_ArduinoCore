file( GLOB SOURCES *.cc )

idf_component_register(SRCS ${SOURCES} INCLUDE_DIRS "include")
