### configuration plugin
add_definitions(-DTRANSLATION_DOMAIN=\"vibrantize_style_config\")
set(kstyle_breeze_config_PART_SRCS breezestyleconfig.cpp)

set(kstyle_breeze_config_PART_SRCS ${kstyle_breeze_config_PART_SRCS} breezestyleconfigmodule.cpp)

kconfig_add_kcfg_files(kstyle_breeze_config_PART_SRCS ../breezestyleconfigdata.kcfgc)
set(kstyle_breeze_config_PART_FORMS ui/breezestyleconfig.ui)
ki18n_wrap_ui(kstyle_breeze_config_PART_FORMS_HEADERS ${kstyle_breeze_config_PART_FORMS})

kcoreaddons_add_plugin(vibrantizestyleconfig SOURCES
    ${kstyle_breeze_config_PART_SRCS}
    ${kstyle_breeze_config_PART_FORMS_HEADERS}
    INSTALL_NAMESPACE "kstyle_config"
)

target_link_libraries(vibrantizestyleconfig
    PUBLIC
        Qt6::Core
        Qt6::Gui
        Qt6::Widgets
)

if(HAVE_QTDBUS)
    target_link_libraries(vibrantizestyleconfig
        PUBLIC
            Qt6::DBus
    )
endif()

target_link_libraries(vibrantizestyleconfig
    PUBLIC
        KF6::CoreAddons
        KF6::ConfigCore
        KF6::ConfigWidgets
        KF6::I18n
)
if(QT_MAJOR_VERSION STREQUAL "6")
    target_link_libraries(vibrantizestyleconfig
        PUBLIC
    KF6::KCMUtils
)
endif()
kcmutils_generate_desktop_file(vibrantizestyleconfig)

set(breeze_settings_SOURCES main.cpp)
add_executable(vibrantize-settings ${breeze_settings_SOURCES} )
target_link_libraries(vibrantize-settings Qt6::Core Qt6::Gui Qt6::Widgets )
target_link_libraries(vibrantize-settings KF6::I18n KF6::KCMUtils KF6::CoreAddons)

set_target_properties(vibrantize-settings PROPERTIES OUTPUT_NAME vibrantize-settings6)

install(TARGETS vibrantize-settings ${KDE_INSTALL_TARGETS_DEFAULT_ARGS})

# icon
ecm_install_icons(ICONS sc-apps-vibrantize-settings.svgz
    DESTINATION ${KDE_INSTALL_ICONDIR}
    THEME hicolor )

