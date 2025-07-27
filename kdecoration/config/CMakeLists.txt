set(breezedecoration_config_SRCS
    ../breezeexceptionlist.cpp
    breezeconfigwidget.cpp
    breezedetectwidget.cpp
    breezeexceptiondialog.cpp
    breezeexceptionlistwidget.cpp
    breezeexceptionmodel.cpp
    breezeitemmodel.cpp
)

# Wrap UI .ui files to generate headers
ki18n_wrap_ui(breezedecoration_config_SRCS
   ui/breezeconfigurationui.ui
   ui/breezeexceptiondialog.ui
   ui/breezeexceptionlistwidget.ui
)

#  Generate settings class from KCFG
kconfig_add_kcfg_files(KCFG_SRCS ../breezesettings.kcfgc)

#  Add generated breezesettings.h/cpp to the source list
list(APPEND breezedecoration_config_SRCS ${KCFG_SRCS})

# Build the plugin
kcoreaddons_add_plugin(kcm_vibrantizedecoration
    SOURCES kcm_breezedecoration.cpp ${breezedecoration_config_SRCS}
    INSTALL_NAMESPACE "${KDECORATION_KCM_PLUGIN_DIR}"
)

# Include dirs  required for finding breezesettings.h
target_include_directories(kcm_vibrantizedecoration PRIVATE
    ${CMAKE_CURRENT_BINARY_DIR}
    ${CMAKE_SOURCE_DIR}/kdecoration
    ${CMAKE_BINARY_DIR}/kdecoration
)

# Link required libraries
target_link_libraries(kcm_vibrantizedecoration
    PUBLIC
        Qt6::Core
        Qt6::Gui
        Qt6::DBus
    PRIVATE
        KF6::ConfigCore
        KF6::CoreAddons
        KF6::GuiAddons
        KF6::I18n
        KF6::IconThemes
        KF6::KCMUtils
)

# Generate .desktop file for the KCM
kcmutils_generate_desktop_file(kcm_vibrantizedecoration)



