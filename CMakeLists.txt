
cmake_minimum_required(VERSION 3.10)

# Project name
project(CyclonePhysics)

# Set C++ standard
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# Include directories
include_directories(${PROJECT_SOURCE_DIR}/include)

# Source files
set(CYCLONEFILES
    src/body.cpp
    src/collide_coarse.cpp
    src/collide_fine.cpp
    src/contacts.cpp
    src/core.cpp
    src/fgen.cpp
    src/joints.cpp
    src/particle.cpp
    src/pcontacts.cpp
    src/pfgen.cpp
    src/plinks.cpp
    src/pworld.cpp
    src/random.cpp
    src/world.cpp
)

# Demo core files
set(DEMOCOREFILES
    src/demos/main.cpp
    src/demos/app.cpp
    src/demos/timing.cpp
)

# List of demos
set(DEMOLIST
    ballistic
    bigballistic
    blob
    bridge
    explosion
    fireworks
    flightsim
    fracture
    platform
    ragdoll
    sailboat
)

# Linker flags for Linux
if(UNIX AND NOT APPLE)
    set(LDFLAGS -lGL -lGLU -lglut)
else()
    message(FATAL_ERROR "This OS is not Ubuntu Linux. Aborting")
endif()

# Create executables for each demo
foreach(DEMO ${DEMOLIST})
    add_executable(${DEMO} ${DEMOCOREFILES} ${CYCLONEFILES} src/demos/${DEMO}/${DEMO}.cpp)
    target_link_libraries(${DEMO} ${LDFLAGS})
endforeach()

# Clean up build files
add_custom_target(clean-all
    COMMAND ${CMAKE_COMMAND} --build . --target clean
)
