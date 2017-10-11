cmake_minimum_required(VERSION 2.8.3)
project(my_path_service)

find_package(catkin_simple REQUIRED)

catkin_simple()

# Executables
cs_add_executable(my_path_service src/my_path_service.cpp)
cs_add_executable(my_path_client src/my_path_client.cpp)

cs_install()
cs_export()
    
