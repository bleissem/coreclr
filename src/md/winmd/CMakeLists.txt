add_definitions(-DNO_CRT)

set(MDWINMD_SOURCES
  adapter.cpp
  winmdimport.cpp
  winmdinternalimportro.cpp
)

convert_to_absolute_path(MDWINMD_SOURCES ${MDWINMD_SOURCES})

if(CLR_CMAKE_PLATFORM_UNIX)
    add_compile_options(-fPIC)
endif(CLR_CMAKE_PLATFORM_UNIX)

add_subdirectory(dac)
add_subdirectory(wks)
if(WIN32)
  add_subdirectory(dbi)
endif(WIN32)