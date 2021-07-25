cmake_minimum_required(VERSION 3.10)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)
set(CMAKE_BUILD_TYPE Release)
set (MAIN_DIR ${CMAKE_CURRENT_SOURCE_DIR}/GAME/main.cpp)
project("GAME_Tetris")
include_directories(
    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5/
    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5/bin/
    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5/include/
    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5/include/SFML/
    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5/include/SFML/Audio/
    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5/include/SFML/Graphics/
    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5/include/SFML/Network/
    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5/include/SFML/System/
    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5/include/SFML/Window/
    # ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5/include/SFML/ucrt/
    # ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5/include/SFML/vs2019/
    # ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5/include/SFML/vs2019/cliext/
    # ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5/include/SFML/vs2019/CodeAnalysis/
    # ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5/include/SFML/vs2019/cvt/
    # ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5/include/SFML/vs2019/experimental/
    # ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5/include/SFML/vs2019/Manifest/
    # ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5/include/SFML/vs2019/msclr/

    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5.1/include/
    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5.1/include/SFML/
    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5.1/include/SFML/Audio/
    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5.1/include/SFML/Graphics/
    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5.1/include/SFML/Network/
    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5.1/include/SFML/System/
    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5.1/include/SFML/Window/

    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5.1/extlibs/headers/
    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5.1/extlibs/headers/AL/
    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5.1/extlibs/headers/FLAC/
    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5.1/extlibs/headers/freetype2/
    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5.1/extlibs/headers/freetype2/config/
    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5.1/extlibs/headers/mingw/
    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5.1/extlibs/headers/ogg/
    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5.1/extlibs/headers/stb_image/
    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5.1/extlibs/headers/vorbis/

    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5.1/src/
    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5.1/src/SFML/
    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5.1/src/SFML/Audio/
    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5.1/src/SFML/Graphics/
    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5.1/src/SFML/Network/
    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5.1/src/SFML/System/
    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5.1/src/SFML/Window/
    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5.1/src/SFML/Window/Win32
    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5.1/src/SFML/Window/Unix
    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5.1/src/SFML/Window/Unix
#open GL
    # ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5/openGL/include/
)

file(GLOB src 
    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5.1/src/*.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5.1/src/SFML/*.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5.1/src/SFML/Audio/*.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5.1/src/SFML/Graphics/*.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5.1/src/SFML/Network/*.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5.1/src/SFML/System/*.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5.1/src/SFML/Window/*.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5.1/src/SFML/Window/Win32/*.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5.1/src/SFML/Window/Unix/*.cpp
    )
add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5/bin)

add_compile_options(
    -g
    -std=c++17
    -w
)
file(GLOB LIB_EXT
    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5.1/extlibs/libs-mingw/x64/*.a
)
file(GLOB OPENGL_GLUT
    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5/openGL/lib/x64/*.a
    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5/openGL/lib/*.a
    )
add_definitions(
    -D_GLIBCXX_USE_CXX11_ABI
    # -DNDEBUG
)
# set(LIB_SELECT
#     ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5/lib/libFLAC.a
#     ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5/lib/libfreetype.a
#     ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5/lib/libogg.a
#     ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5/lib/libopenal32.a
#     ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5/lib/libsfml-audio.a
#     ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5/lib/libsfml-graphics.a
#     ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5/lib/libsfml-main.a
#     ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5/lib/libsfml-system.a
#     ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5/lib/libsfml-window.a
#     ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5/lib/libvorbis.a
#     ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5/lib/libvorbisenc.a
#     ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5/lib/libvorbisfile.a
#     )
set(addition_src 
    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5.1/src/SFML/Graphics/Texture.cpp
    # ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5.1/src/SFML/Graphics/Image.cpp
    )
file(GLOB lib
    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5/lib/*.a
    )
set (target texture)
file(GLOB dll
    ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5/bin/*.dll
    )

# SET_TARGET_PROPERTIES (
#     ${target} PROPERTIES DEFINE_SYMBOL  ${dll}
#     )
# set (Add_more_lib
#     ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5/lib/libsfml-graphics.a
#     ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5/lib/libsfml-graphics-d.a
#     ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5/lib/libsfml-graphics-s.a
#     ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5/lib/libsfml-graphics-s-d.a
#     )
file(COPY ${CMAKE_CURRENT_SOURCE_DIR}/GAME/images DESTINATION ${CMAKE_CURRENT_SOURCE_DIR}/build/)
file(COPY ${CMAKE_CURRENT_SOURCE_DIR}/SFML2.5/bin/ DESTINATION ${CMAKE_CURRENT_SOURCE_DIR}/build/)
add_executable(
    project
    # ${src}
    ${MAIN_DIR}
)
target_link_libraries(
    project
    # ${LIB_SELECT}
    ${lib}
    # SDL2
)

# add_library(${target} SHARED 
#     ${addition_src}
#     # ${src}
#     )
# target_link_libraries(
#     ${target}
#     ${lib}
#     # ${LIB_EXT}
#     # ${OPENGL_GLUT}
#     -lopengl32
#     # -lglew32
#     # -lfreeglut
#     -lglu32
#     SDL2
# )