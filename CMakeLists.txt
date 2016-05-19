cmake_minimum_required(VERSION 2.8.3)
project(meuhmeuh)

add_definitions(-std=c++11)

find_package(dlib REQUIRED)
include_directories(${dlib_INCLUDE_DIRS})

add_executable(meuhmeuh_train 
            train_shape_predictor.cpp 
            )

add_executable(meuhmeuh_find
            meuhmeuh_finder.cpp 
            )

add_executable(meuhmeuh_train_detector
            train_meuhmeuh_detector.cpp 
            )


target_link_libraries(meuhmeuh_train ${dlib_LIBRARIES})
target_link_libraries(meuhmeuh_train_detector ${dlib_LIBRARIES})
target_link_libraries(meuhmeuh_find ${dlib_LIBRARIES})

