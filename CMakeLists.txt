project(libtelnet)

set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -nostdinc")

add_compile_definitions(
	__FBSDID=__RCSID
	HAS_CGETENT
	AUTHENTICATION
	RSA
	KRB5
	FORWARD
	HAVE_STDLIB_H
)

add_darling_static_library(telnet FAT SOURCES
	auth.c
	enc_des.c
	encrypt.c
	forward.c
	genget.c
	getent.c
	kerberos.c
	kerberos5.c
	krb4encpwd.c
	misc.c
	read_password.c
	rsaencpwd.c
	sra.c
)
