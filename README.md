# rpi-motion-camera2-noire-
Raswpberry Pi with Camera Module Noir v2 and Motion setup

Just saving my notes from getting Motion running with the Raspberry Pi Camera Module. My specific Raspberry Pi is a 2B.

Setup on Rasbian OS Bullseye
Installed Motion 4.7 using Apt
I've included the motion.conf file and the motion.system file.
motion.conf is mostly preferences, but most importnatly is that the daemon flag is set to off
For the raspberry pi camera, you need to add

    Environment="LIBCAMERA_RPI_TUNING_FILE=/usr/share/libcamera/ipa/rpi/vc4/imx219_noir.json"
    ExecStart=/usr/bin/libcamerify /usr/bin/motion

The tuning file should point to the camera you have. 
licamerify needs to be run before motion so that motion has access to the camera. 
