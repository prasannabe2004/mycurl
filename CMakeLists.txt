

# Almost all CMake files should start with this
# You should always specify a range with the newest
# and oldest tested versions of CMake. This will ensure
# you pick up the best policies.
cmake_minimum_required(VERSION 3.15...3.31)

# This is your project statement. You should always list languages;
# Listing the version is nice here since it sets lots of useful variables
project(
  mycurl
  VERSION 1.0
  LANGUAGES CXX)

# If you set any CMAKE_ variables, that can go here.
# (But usually don't do this, except maybe for C++ standard)

# Find packages go here.
find_package(CURL REQUIRED)

# You should usually split this into folders, but this is a simple example

# This is a "default" library, and will match the *** variable setting.
# Other common choices are STATIC, SHARED, and MODULE
# Including header files here helps IDEs but is not required.
# Output libname matches target name, with the usual extensions on your system
#add_library(mylibcurl indicators.hpp)

add_executable(mycurl src/curl_example.cpp inc/indicators.hpp)

target_include_directories(mycurl PRIVATE inc)
target_link_libraries(mycurl PRIVATE curl)

