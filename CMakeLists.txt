cmake_minimum_required(VERSION 3.11)
project(checkers)

set(CMAKE_VERBOSE_MAKEFILE ON)
set(CMAKE_CXX_STANDARD 14)

add_compile_options(-Wall -Wextra)

if (UNIX)
  
    set ( CMAKE_MODULES_PATH "/usr/share/SFML/cmake/Modules" ${CMAKE_MODULES_PATH})

  
    set ( CMAKE_PREFIX_PATH "/usr/lib/x86_64-linux-gnu/cmake/SFML" ${CMAKE_PREFIX_PATH})

endif(UNIX)

if (WIN32)
    set( SFML_STATIC_LIBRARIES TRUE )

    set (SFML_DIR "C:/SFML/lib/cmake/SFML/")
endif(WIN32)


find_package(SFML 2 COMPONENTS graphics )


add_executable(checkers main.cpp Checkerboard.cpp Checkerboard.h CheckerboardSFML.cpp CheckerboardSFML.h Gamecontroller.cpp Gamecontroller.h Menu.cpp Menu.h)
target_link_libraries(checkers sfml-graphics sfml-audio)