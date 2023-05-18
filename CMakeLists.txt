cmake_minimum_required (VERSION 3.10)

project (vhttp)

find_package( Boost COMPONENTS program_options REQUIRED )
include_directories( ${Boost_INCLUDE_DIR} )

include_directories(include)

file(GLOB_RECURSE vhttp_sources src/**.cpp)

add_library(vhttp SHARED ${vhttp_sources})

target_link_libraries(vhttp LINK_PUBLIC ${Boost_LIBRARIES})
target_compile_features(vhttp PUBLIC cxx_std_20)