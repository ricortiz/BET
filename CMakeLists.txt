cmake_minimum_required(VERSION 2.8)

project(bet)

set(SOURCE_FILES
  main.cpp
  newimage/generalio.cc
  newimage/newimagefns.cc
  newimage/newimage.cc
  newimage/costfns.cc
  newimage/imfft.cc
  newimage/complexvolume.cc
  newimage/lazy.cc
  meshclass/profile.cpp
  meshclass/triangle.cpp
  meshclass/mesh.cpp
  meshclass/mpoint.cpp
  meshclass/pt_special.cpp
  meshclass/point.cpp
)

add_definitions(-DEXPOSE_TREACHEROUS)

include_directories(${PROJECT_SOURCE_DIR})
include_directories(include)
include_directories(newmat)
include_directories(libprob)

add_executable(bet ${SOURCE_FILES})
target_link_libraries(bet utils miscmaths newmat niftiio fslio znz)

add_subdirectory(utils)
add_subdirectory(fslio)
add_subdirectory(niftiio)
add_subdirectory(znzlib)
add_subdirectory(miscmaths)
add_subdirectory(newmat)
add_subdirectory(libprob)
