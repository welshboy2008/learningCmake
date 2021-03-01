#Set the minimum version needed to build the project
cmake_minimum_required(VERSION 2.0)

# This isn't mentioned in the cmake tutorial, but we need it to allow
# project version numbers in the project statement that follows.
cmake_policy(SET CMP0048 NEW)

# What are we going to call the project?
project(tutorial VERSION 1.0)

# Specify which C++ standard we're gonna use.
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED true)

# Now we configure a header file to pass the version number
# to the source code/
configure_file(TutorialConfig.h.in tutorialConfig.h)


# What's the executable artefact we're going to produce?
add_executable(tutorial tutorial.cxx)

target_include_directories(tutorial PUBLIC "${PROJECT_BINARY_DIR}")
