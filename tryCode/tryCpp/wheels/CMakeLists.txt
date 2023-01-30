set(MODULE_NAME wheels)

set(${MODULE_NAME}_SRC
    
    )

set(${MODULE_NAME}_HEADER_FILES
    include/a.h
    )

set(${MODULE_NAME}_SRC_FILES
    src/a.cpp
    )
        
add_library(${MODULE_NAME}
    ${${MODULE_NAME}_SRC_FILES}
    ${${MODULE_NAME}_HEADER_FILES}
    )

add_library(${PROJECT_NAME}::${MODULE_NAME} ALIAS ${MODULE_NAME})

target_include_directories(${MODULE_NAME}
    PRIVATE
    src
    PUBLIC
    include
    )

set_target_properties(${MODULE_NAME} PROPERTIES PUBLIC_HEADER "${${MODULE_NAME}_HEADER_FILES}")
