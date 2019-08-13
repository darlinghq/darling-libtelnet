project(libtelnet)

set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -nostdinc")

include_directories(${CMAKE_SOURCE_DIR}/src/external/openssl/src/include)

set(libtelnet_sources
	auth.c
	enc_des.c
	encrypt.c
	forward.c
	genget.c
	getent.c
	misc.c
	read_password.c
	rsaencpwd.c
)

set(DYLIB_INSTALL_NAME "/usr/lib/libtelnet.dylib")
add_darling_library(telnet ${libtelnet_sources})
target_link_libraries(telnet system)

install(TARGETS telnet DESTINATION libexec/darling/usr/lib)

