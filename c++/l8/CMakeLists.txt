#cmake_minimum_required(VERSION 3.28.3)
#project(ConsoleApplication8)
#set(PROJECT_NAME ConsoleApplication8)
#project("${PROJECT_NAME}")
#set(SFML_DIR "D:\SFML-2.6.1")
#set(CMAKE_CXX_STANDARD 11)
#add_executable(ConsoleApplication8 ConsoleApplication8.cpp)
#target_link_libraries(ConsoleApplication8 sfml-system sfml-window sfml-graphics sfml-audio)

cmake_minimum_required(VERSION 3.28.3)
project(ConsoleApplication8)
set(SFML_DIR "D:/SFML-2.6.1/lib/cmake/SFML")
find_package(SFML 2.6.1 COMPONENTS system window graphics audio REQUIRED)
add_executable(ConsoleApplication8 ConsoleApplication8.cpp)
target_link_libraries(ConsoleApplication8 sfml-system sfml-window sfml-graphics sfml-audio)
