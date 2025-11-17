 # QGIS warning about wayland session
 System Info:
 - Distro: Fedora Linux 42 (KDE Plasma Desktop Edition)
 - Kernel: 6.17.7

Fix: 
1. COPY the normal QGIS Desktop .desktop file onto your desktop
2. Edit the ```Exec=qgis %F``` into ```Exec=env QT_QPA_PLATFORM=xcb qgis %F```
3. Use your new .desktop file to launch QGIS
4. Profit
