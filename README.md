# Vibrantize 

Modern style with vibrant blue 


<img width="3045" height="1979" alt="eter" src="https://github.com/user-attachments/assets/76d81f0a-f353-42ce-a785-cbcc076ff16b" />

<img width="1749" height="1379" alt="fdg" src="https://github.com/user-attachments/assets/fe6e4181-bc71-4e9f-9827-1a9af8c72687" />

<img width="3060" height="2003" alt="fgg" src="https://github.com/user-attachments/assets/3b60e248-65e7-4ee5-94fd-04f39fd55415" />

<img width="1749" height="1379" alt="gf" src="https://github.com/user-attachments/assets/1867c621-b093-4875-af68-8eba0e7a7e6f" />



Transparency of context menu is edited on the breeze style and also works for vibrantize 

theme for the panel icons and panel applets that follows this application style - https://github.com/orqvvcn/kde-panel-tasks



## 1st install dependencies for your distro and then go to the install part


## Arch/ Manjaro 

```bash
sudo pacman -S --noconfirm cmake extra-cmake-modules kdecoration qt6-declarative kcoreaddons \
      kcmutils kcolorscheme kconfig kguiaddons kiconthemes kwindowsystem git \
      qt5-declarative qt5-x11extras gcc make kcmutils5 \
      frameworkintegration5 kconfigwidgets5 kiconthemes5 \
      kirigami2 kwindowsystem5
```


## openSUSE Tumbleweed

```bash
sudo zypper in --no-recommends git ninja cmake kf6-extra-cmake-modules kf6-kconfig-devel \
      kf6-frameworkintegration-devel gmp-ecm-devel kf6-kconfigwidgets-devel \
      kf6-kguiaddons-devel kf6-ki18n-devel kf6-kiconthemes-devel kf6-kwindowsystem-devel \
      kf6-kcolorscheme-devel kf6-kcoreaddons-devel kf6-kcmutils-devel \
      qt6-quick-devel kf6-kirigami-devel qt6-base-devel kdecoration6-devel \
      qt6-tools qt6-widgets-devel gcc-c++ extra-cmake-modules libQt5Gui-devel \
      libQt5DBus-devel libqt5-qttools-devel libqt5-qtx11extras-devel \
      libQt5OpenGL-devel libQt5Network-devel libepoxy-devel kconfig-devel \
      kconfigwidgets-devel kcrash-devel kglobalaccel-devel ki18n-devel kio-devel \
      kservice-devel kinit-devel knotifications-devel kwindowsystem-devel kguiaddons-devel \
      kiconthemes-devel kpackage-devel kwin5-devel xcb-util-devel xcb-util-cursor-devel \
      xcb-util-wm-devel xcb-util-keysyms-devel kcmutils-devel \
      libqt5-qtquick3d-devel kirigami2-devel libKF5I18n5
```


## Fedora

```bash
sudo dnf install -y git cmake extra-cmake-modules "cmake(KDecoration3)" kwin-devel \
      kf6-kcolorscheme-devel kf6-kguiaddons-devel kf6-ki18n-devel kf6-kiconthemes-devel \
      kf6-kirigami-devel kf6-kcmutils-devel kf6-frameworkintegration-devel \
      libepoxy-devel "cmake(Qt5Core)" "cmake(Qt5Gui)" "cmake(Qt5DBus)" "cmake(KF5GuiAddons)" \
      "cmake(KF5WindowSystem)" "cmake(KF5I18n)" "cmake(KF5CoreAddons)" "cmake(KF5ConfigWidgets)" \
      "cmake(Qt5UiTools)" "cmake(KF5GlobalAccel)" "cmake(KF5IconThemes)" "cmake(KF5Init)" \
      "cmake(KF5KIO)" kf5-kpackage-devel kf5-kcmutils-devel qt5-qtquickcontrols2-devel \
      kf5-kirigami2-devel "cmake(KF5FrameworkIntegration)"
```


## KDE neon

```bash
sudo apt install -y git build-essential cmake kf6-extra-cmake-modules \
      kf6-extra-cmake-modules kf6-frameworkintegration-dev \
      kf6-kcmutils-dev kf6-kcolorscheme-dev kf6-kconfig-dev kf6-kconfigwidgets-dev \
      kf6-kcoreaddons-dev kf6-kguiaddons-dev kf6-ki18n-dev kf6-kiconthemes-dev \
      kf6-kirigami2-dev kf6-kpackage-dev kf6-kservice-dev kf6-kwindowsystem-dev \
      kirigami2-dev kwayland-dev libx11-dev libkdecorations2-dev libkf5config-dev \
      libkf5configwidgets-dev libkf5coreaddons-dev libkf5guiaddons-dev libkf5i18n-dev \
      libkf5iconthemes-dev libkf5kcmutils-dev libkf5package-dev libkf5service-dev \
      libkf5style-dev libkf5wayland-dev libkf5windowsystem-dev libplasma-dev \
      libqt5x11extras5-dev qt6-base-dev qt6-declarative-dev qtbase5-dev \
      qtdeclarative5-dev gettext qt6-svg-dev extra-cmake-modules qt3d5-dev
```


## Kubuntu (25.04)

```bash
sudo apt-get install -y -qq cmake build-essential libkf5config-dev libkdecorations3-dev \
      libqt5x11extras5-dev qtdeclarative5-dev extra-cmake-modules \
      libkf5guiaddons-dev libkf5configwidgets-dev libkf5windowsystem-dev kirigami2-dev \
      libkf5coreaddons-dev libkf5iconthemes-dev gettext qt3d5-dev libkf5kcmutils-dev \
      qt6-base-dev libkf6coreaddons-dev libkf6colorscheme-dev \
      libkf6config-dev libkf6guiaddons-dev libkf6i18n-dev libkf6iconthemes-dev \
      libkf6windowsystem-dev libkf6kcmutils-dev libkirigami-dev libkf6style-dev
```





-----------------------------------------------------------------------------------------

## Install

```bash
git clone https://github.com/orqvvcn/vibrantize.git
cd vibrantize 
rm -rf build/                                                 
mkdir build
cd build
cmake .. -DCMAKE_INSTALL_PREFIX=/usr -DCMAKE_BUILD_TYPE=Release -DBUILD_TESTING=OFF -DKDE_INSTALL_USE_QT_SYS_PATHS=ON
make -j$(nproc)
sudo make install
```




## Uninstall

```bash
sudo rm -f "/usr/lib/qt5/plugins/styles/vibrantize5.so"
sudo rm -f "/usr/lib64/qt5/plugins/styles/vibrantize5.so"
sudo rm -f "/usr/lib/qt/plugins/styles/vibrantize5.so"
sudo rm -f "/usr/lib/qt6/plugins/styles/vibrantize6.so"
sudo rm -f "/usr/lib64/qt6/plugins/styles/vibrantize6.so"
sudo rm -f "/usr/lib/libvibrantizecommon5.so*"
sudo rm -f "/usr/lib64/libvibrantizecommon5.so*"
sudo rm -f "/usr/lib/libvibrantizecommon6.so*"
sudo rm -f "/usr/lib64/libvibrantizecommon6.so*"
sudo rm -f "/usr/share/color-schemes/vibrantize.colors"
sudo rm -f "/usr/share/color-schemes/VibrantizeClassic.colors"
sudo rm -f "/usr/share/color-schemes/VibrantizeDark.colors"
sudo rm -f "/usr/share/color-schemes/VibrantizeLight.colors"
sudo rm -f "/usr/share/kstyle/themes/vibrantize.themerc"
sudo rm -f "/usr/share/applications/vibrantizestyleconfig.desktop"
sudo rm -f "/usr/share/applications/kcm_vibrantizedecoration.desktop"
sudo rm -f "/usr/share/icons/hicolor/scalable/apps/vibrantize-settings.svgz"
sudo rm -f "/usr/share/kstyle/vibrantize.desktop"
sudo rm -f "/usr/lib/qt6/plugins/org.kde.kdecoration3/org.kde.vibrantize.so*"
sudo rm -f "/usr/lib64/qt6/plugins/org.kde.kdecoration3/org.kde.vibrantize.so*"
sudo rm -f "/usr/share/kservices6/vibrantizedecorationconfig.desktop"
sudo rm -f "/usr/share/kservices6/vibrantize.desktop"
sudo rm -f "/usr/share/kservices6/vibrantize6.desktop"
sudo rm -f "/usr/lib/qt6/plugins/org.kde.kdecoration3.kcm/kcm_vibrantizedecoration.so*"
sudo rm -f "/usr/lib64/qt6/plugins/org.kde.kdecoration3.kcm/kcm_vibrantizedecoration.so*"
sudo rm -f "/usr/bin/vibrantize-settings6"
sudo rm -f "/usr/lib/qt6/plugins/kstyle_config/vibrantizestyleconfig.so"
sudo rm -f "/usr/lib/cmake/vibrantize/vibrantizeConfig.cmake"
sudo rm -f "/usr/lib64/cmake/vibrantize/vibrantizeConfig.cmake"
sudo rm -rf "/usr/lib/cmake/vibrantize"
sudo rm -rf "/usr/lib64/cmake/vibrantize"
```





