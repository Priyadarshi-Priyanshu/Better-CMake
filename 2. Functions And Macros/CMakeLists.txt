cmake_minimum_required(VERSION 3.1.1)

project(LearningFAndM CXX)

set(Project1 "first project") # It sets variables
set(Project2 "second project")

# Writing function having a specified variable name.
# function(display text)
#     message("${text} : ${${text}}")
# endfunction()


# Below is the example code for function
function(display)
    message("Hey This is calling the function")
    message(${ARGN}) # It prints all the variables.
    message(${ARGC}) # It tells you how many variables.
    #message("${ARGV0} : ${${ARGV0}}")
    # message("${ARGV0} : ${ARGV1}")
    # message("${ARGV0} : ${ARGV2}")
    foreach(var ${ARGN})
        message("${var} : ${${var}}")
    endforeach()
endfunction()

# Below is the example code for Macro.
# Macro basically works like having writen the code inline in that place unlike fucntion which works in a different way altogether.
macro(display)
    message("Hey This is calling the macro")
    message(${ARGN}) # It prints all the variables.
    message(${ARGC}) # It tells you how many variables.
    #message("${ARGV0} : ${${ARGV0}}")
    # message("${ARGV0} : ${ARGV1}")
    # message("${ARGV0} : ${ARGV2}")
    foreach(var ${ARGN})
        message("${var} : ${${var}}")
    endforeach()
    set(Project1 "Close Project1")
endmacro()

display(PROJECT_NAME Project1 Project2)
display(PROJECT_NAME Project1 Project2)

add_executable(${PROJECT_NAME} main.cpp)

# message("So I just wanted to log the name of the project : ${PROJECT_NAME}")  
# This helps us log to our command line better.


