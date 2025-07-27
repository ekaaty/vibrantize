################# includes #################
include_directories(
  animations
  debug
)

include_directories(${CMAKE_SOURCE_DIR}/libbreezecommon)
include_directories(${CMAKE_BINARY_DIR}/libbreezecommon)

################# configuration #################
configure_file(config-breeze.h.cmake ${CMAKE_CURRENT_BINARY_DIR}/config-breeze.h )

########### next target ###############
set(breeze_PART_SRCS
    animations/breezeanimation.cpp
    animations/breezeanimations.cpp
    animations/breezeanimationdata.cpp
    animations/breezebaseengine.cpp
    animations/breezebusyindicatordata.cpp
    animations/breezebusyindicatorengine.cpp
    animations/breezedialdata.cpp
    animations/breezedialengine.cpp
    animations/breezeenabledata.cpp
    animations/breezegenericdata.cpp
    animations/breezeheaderviewdata.cpp
    animations/breezeheaderviewengine.cpp
    animations/breezescrollbardata.cpp
    animations/breezescrollbarengine.cpp
    animations/breezespinboxengine.cpp
    animations/breezespinboxdata.cpp
    animations/breezestackedwidgetdata.cpp
    animations/breezestackedwidgetengine.cpp
    animations/breezetabbarengine.cpp
    animations/breezetabbardata.cpp
    animations/breezetoolboxengine.cpp
    animations/breezetransitiondata.cpp
    animations/breezetransitionwidget.cpp
    animations/breezewidgetstateengine.cpp
    animations/breezewidgetstatedata.cpp
    debug/breezewidgetexplorer.cpp
    breezeaddeventfilter.cpp
    breezeblurhelper.cpp
    breezeframeshadow.cpp
    breezehelper.cpp
    breezemdiwindowshadow.cpp
    breezemnemonics.cpp
    breezepropertynames.cpp
    breezeshadowhelper.cpp
    breezesplitterproxy.cpp
    breezestyle.cpp
    breezestyleplugin.cpp
    breezetileset.cpp
    breezewindowmanager.cpp
    breezetoolsareamanager.cpp
)


kconfig_add_kcfg_files(breeze_PART_SRCS ../kdecoration/breezesettings.kcfgc)
kconfig_add_kcfg_files(breeze_PART_SRCS breezestyleconfigdata.kcfgc)

add_library(vibrantize${QT_MAJOR_VERSION} MODULE ${breeze_PART_SRCS})

ecm_qt_declare_logging_category(vibrantize${QT_MAJOR_VERSION}
    HEADER
        breeze_logging.h
    IDENTIFIER
        VIBRANTIZE
    CATEGORY_NAME
        vibrantize${QT_MAJOR_VERSION}
    DEFAULT_SEVERITY
        Warning
)

target_link_libraries(vibrantize${QT_MAJOR_VERSION}
    Qt${QT_MAJOR_VERSION}::Core
    Qt${QT_MAJOR_VERSION}::Gui
    Qt${QT_MAJOR_VERSION}::Widgets
)

if(HAVE_QTDBUS)
    target_link_libraries(vibrantize${QT_MAJOR_VERSION}
        Qt${QT_MAJOR_VERSION}::DBus
    )
endif()

if(BREEZE_HAVE_QTQUICK)
    target_link_libraries(vibrantize${QT_MAJOR_VERSION}
        Qt${QT_MAJOR_VERSION}::Quick
        KF${QT_MAJOR_VERSION}::CoreAddons
    )
endif()

target_link_libraries(vibrantize${QT_MAJOR_VERSION}
    KF${QT_MAJOR_VERSION}::CoreAddons
    KF${QT_MAJOR_VERSION}::ConfigCore
    KF${QT_MAJOR_VERSION}::ConfigGui
    KF${QT_MAJOR_VERSION}::GuiAddons
    KF${QT_MAJOR_VERSION}::IconThemes
    KF${QT_MAJOR_VERSION}::WindowSystem
)

if(QT_MAJOR_VERSION STREQUAL "5")
    target_link_libraries(vibrantize5 KF5::ConfigWidgets)
    if(BREEZE_HAVE_QTQUICK)
        target_link_libraries(vibrantize5 KF5::Kirigami2)
    endif()
else()
    target_link_libraries(vibrantize6 KF6::ColorScheme)
    if(BREEZE_HAVE_QTQUICK)
        target_link_libraries(vibrantize6 KF6::KirigamiPlatform)
    endif()
endif()

target_link_libraries(vibrantize${QT_MAJOR_VERSION} vibrantizecommon${QT_MAJOR_VERSION})

if(KF${QT_MAJOR_VERSION}FrameworkIntegration_FOUND)
    target_link_libraries(vibrantize${QT_MAJOR_VERSION} KF${QT_MAJOR_VERSION}::Style)
endif()

if(WIN32)
    target_compile_definitions(vibrantize${QT_MAJOR_VERSION} PRIVATE _USE_MATH_DEFINES _BSD_SOURCE)
endif()

########### install files ###############

# Fallback if KDE_INSTALL_QTPLUGINDIR not defined
if(NOT KDE_INSTALL_QTPLUGINDIR)
    set(KDE_INSTALL_QTPLUGINDIR "/usr/lib/qt6/plugins")
endif()

# Install plugin
install(TARGETS vibrantize${QT_MAJOR_VERSION}
    DESTINATION ${KDE_INSTALL_QTPLUGINDIR}/styles/
)

# Install theme config
install(FILES vibrantize.themerc
    DESTINATION ${KDE_INSTALL_DATADIR}/kstyle/themes/
)

# Install .desktop file to kservices6 (so System Settings can find it)
install(FILES vibrantize.desktop
    DESTINATION ${KDE_INSTALL_DATAROOTDIR}/kservices6/
    RENAME vibrantize6.desktop
)


########### subdirectories ###############
if(QT_MAJOR_VERSION EQUAL "6" AND TARGET "KF6::KCMUtils")
    add_subdirectory(config)
endif()
