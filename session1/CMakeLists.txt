if(${ENABLE_SOLUTIONS})
    add_subdirectory(solutions)
else()
    set(TARGET
        exercise1
    )

    set(SOURCE
        ### Add your cpp files here, relative to this file. Only one of these files is allowed to contain a main() function ###
        ###   e.g. exercise-1.1.cpp
    )

    set(DEPS
        utils
        sfml
    )

    if(SOURCE)
        add_executable(${TARGET} ${SOURCE})
        target_include_directories(${TARGET} PRIVATE ${DEPS})
        target_link_libraries(${TARGET} PRIVATE ${DEPS})

        install(TARGETS ${TARGET} DESTINATION ${BIN_DIRECTORY})
    endif()
endif()
