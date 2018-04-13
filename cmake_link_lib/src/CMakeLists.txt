INCLUDE_DIRECTORIES("/home/kpm/bin/include")
LINK_DIRECTORIES("/home/kpm/bin/lib")
#alternative solution but need `export CMAKE_INCLUDE_PATH=/usr/include/hello`in bash
FIND_PATH(myHeader hello.hpp)
IF(myHeader)
INCLUDE_DIRECTORIES(${myHeader})
ENDIF(myHeader)
#-----------------------
ADD_EXECUTABLE(main main.cpp)
TARGET_LINK_LIBRARIES(main libhello.so)