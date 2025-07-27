add_library(vibrantizecommon${QT_MAJOR_VERSION} OBJECT breezeboxshadowrenderer.cpp)

set_target_properties(vibrantizecommon${QT_MAJOR_VERSION} PROPERTIES POSITION_INDEPENDENT_CODE TRUE)

target_link_libraries(vibrantizecommon${QT_MAJOR_VERSION}
    PUBLIC
        Qt${QT_MAJOR_VERSION}::Core
        Qt${QT_MAJOR_VERSION}::Gui)
