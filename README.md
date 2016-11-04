# ufw-kcm
KCM module for UFW

Installation
------------
    mkdir build  
    cd build  
    cmake -DCMAKE_INSTALL_PREFIX=\`kf5-config --prefix\` ..  
    make  
    make install

Execution
---------
ufw-kcm can be accessed through System Settings, or by issuing the command:
`kcmshell5 kcm_ufw`
