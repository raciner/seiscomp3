SET(PLUGIN_TARGET md)

SET(
	PLUGIN_SOURCES
		md.cpp
		l4c1hz.cpp
)
SET(
	PLUGIN_HEADERS
		md.h
		l4c1hz.h
)

SC_ADD_PLUGIN_LIBRARY(PLUGIN ${PLUGIN_TARGET} "")
SC_LINK_LIBRARIES_INTERNAL(${PLUGIN_TARGET} client core config)

FILE(GLOB descs "${CMAKE_CURRENT_SOURCE_DIR}/descriptions/*.xml")
INSTALL(FILES ${descs} DESTINATION ${SC3_PACKAGE_APP_DESC_DIR})
