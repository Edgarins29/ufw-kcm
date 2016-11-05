# ufw-kcm
KCM module for UFW

Installation
------------
    mkdir build  
    cd build  
    cmake -DCMAKE_INSTALL_PREFIX=\`kf5-config --prefix\` ..  
    make  
    make install

Dependencies
------------
*   Qt >= 5.2
*   KF5Auth
*   KF5ConfigWidgets
*   KF5CoreAddons
*   KF5Crash
*   KF5I18n
*   KF5KIO
*   KF5WidgetsAddons
*   ufw
*   python-ufw

Execution
---------
ufw-kcm can be accessed through System Settings, or by issuing the command:
`kcmshell5 kcm_ufw`
