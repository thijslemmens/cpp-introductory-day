set(LIB_NAME solutions-session2)
set(LIB_SOURCES
    smartBall.cpp
    bat.cpp
)

add_library(${LIB_NAME} ${LIB_SOURCES})
target_link_libraries(${LIB_NAME} PUBLIC utils)

set(BIN_SOURCES
    exercise-2.1.cpp
    exercise-2.2.cpp
    exercise-2.3.cpp
    exercise-2.4.cpp
)

set(DEPS
    solutions-session2
    sfml
)

foreach(SOURCE IN ITEMS ${BIN_SOURCES})
    string (REPLACE ".cpp" "" TARGET "${SOURCE}")
    add_executable(${TARGET} ${SOURCE})
    target_include_directories(${TARGET} PRIVATE ${DEPS})
    target_link_libraries(${TARGET} PRIVATE ${DEPS})

    install(TARGETS ${TARGET} DESTINATION ${BIN_DIRECTORY})
endforeach(SOURCE)
