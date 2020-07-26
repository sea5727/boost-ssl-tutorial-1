cmake_minimum_required(VERSION 3.0.0)
project(boost-tutorial-ssl-5 VERSION 0.1.0)

include(CTest)
enable_testing()

find_package(Boost 1.62 REQUIRED COMPONENTS thread)
if(Boost_FOUND)
    
endif()

add_executable(ssl-client client.cpp)
target_link_libraries(ssl-client ${Boost_LIBRARIES} crypto ssl)

add_executable(ssl-server server.cpp)
target_link_libraries(ssl-server ${Boost_LIBRARIES} crypto ssl)


set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)
