message("Start compiling gmp library.")
include(ExternalProject)

ExternalProject_Add(gmp
	PREFIX gmp
	SOURCE_DIR ${CMAKE_CURRENT_SOURCE_DIR}/gmp-6.3.0
	BINARY_DIR ${CMAKE_CURRENT_BINARY_DIR}/build
	CONFIGURE_COMMAND sh ${CMAKE_CURRENT_SOURCE_DIR}/gmp-6.3.0/configure --enable-cxx --prefix=${CMAKE_CURRENT_BINARY_DIR}/install
	BUILD_COMMAND $(MAKE)
	INSTALL_COMMAND $(MAKE) install
)

message("Finish compiling gmp library.")
