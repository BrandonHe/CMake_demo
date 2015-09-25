add_executable(main main.c)
#include_directories(/usr/include/hello)
#It's better to replace above sentence with below, please note to set env var wiht export CMAKE_INCLUDE_PATH=/usr/include/hello
find_path(myHeader hello.h)
if(myHeader)
include_directories(${myHeader})
endif(myHeader)

#shared linkage
target_link_libraries(main libhello.so)

#static linkage
target_link_libraries(main libhello.a)
