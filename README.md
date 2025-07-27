# Vibrantize 


<img width="3045" height="1979" alt="eter" src="https://github.com/user-attachments/assets/76d81f0a-f353-42ce-a785-cbcc076ff16b" />

<img width="1749" height="1379" alt="fdg" src="https://github.com/user-attachments/assets/fe6e4181-bc71-4e9f-9827-1a9af8c72687" />

<img width="3060" height="2003" alt="fgg" src="https://github.com/user-attachments/assets/3b60e248-65e7-4ee5-94fd-04f39fd55415" />

<img width="1749" height="1379" alt="gf" src="https://github.com/user-attachments/assets/1867c621-b093-4875-af68-8eba0e7a7e6f" />


Transparency of context menu is edited on the breeze style and also works for vibrantize 

Modern look with less sperator lines and a vibrant blue 





##Install

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




##Uninstall

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





