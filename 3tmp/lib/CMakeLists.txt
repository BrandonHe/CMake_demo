set(LIBHELLO_SRC hello.c)
add_library(hello SHARED ${LIBHELLO_SRC})

#Add version of shared library
set_target_properties(hello PROPERTIES VERSION 1.2 SOVERSION 1)

#Error: because another target with the same name already exists.
#add_library(hello STATIC ${LIBHELLO_SRC})

add_library(hello_static STATIC ${LIBHELLO_SRC})
#Uncomment below codes to make the static library name same with shared library
get_target_property(OUTPUT_VALUE hello_static OUTPUT_NAME)
message(STATUS "This is the hello_static OUTPUT_NAME: " ${OUTPUT_VALUE})
set_target_properties(hello_static PROPERTIES OUTPUT_NAME "hello")

#Install the shared and static library and head file
install(TARGETS hello hello_static
	LIBRARY DESTINATION lib
	ARCHIVE DESTINATION lib)
install(FILES hello.h DESTINATION include/hello)
