find_package (OpenCV REQUIRED)

message("opencv lib directory")
message(${OpenCV_LIBS})

include_directories(
    ${Boost_INCLUDE_DIRS}
    ${OpenCV_INCLUDE_DIRS}
    ${TBB_INCLUDE_DIRS}
    ${pupiltracker_SOURCE_DIR}/lib
)

link_directories(
    ${OpenCV_LIB_DIR}
)
add_executable (
    pupiltrackercmd

    PupilTrackerCmd.cpp
)

target_link_libraries(
    pupiltrackercmd

    pupiltracker
    ${OpenCV_LIBS}
    ${TBB_LIBRARIES}
)



